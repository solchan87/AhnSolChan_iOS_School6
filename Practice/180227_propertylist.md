# Swift 문법
> 2018.01.27 업데이트   

## Property list - plist
* 심플한 “파일” 저장 방법 중 하나
* Key,Value구조로 데이터 저장
* File 형태로 저장되다 보니 외부에서 Access가능(보안 취약)

### 파일 위치
* 파일이 저장되는곳 Bundle & Documents 폴더•Bundle은 프로젝트에 추가된 Resorce가 모인 곳 
* 프로그램이 실행되며 저장하는 파일은 Documents폴더에 저장된다.
* __즉! plist파일의 데이터만 불러오는 역할은 Bundle을 통해서, plist파일에 데이터를 쓰고 불러오는 역할은 Documents폴더에 저장된 파일로!__
> Documents는 경로를 알아야 되며, 경로에 대한 예외 처리가 필요하다.

#### Plist File In Bundle
1. bundle에 있는 파일 Path 가져오기 
2. Path를 통해 객체로 변환, 데이터 불러오기 
3. 사용

## Bundle
* 실행코드, 이미지, 사운드, nib 파일, 프레임 워크,설정파일 등 코드와 리소스가 모여있는 file system내의 Directory

### Main Bundle
```swift
// Main Bundle 가져오기 - 싱글톤
let mainBundle = Bundle.main

// 리소스 파일 주소 가져오기
let filePath:String? = mainBundle.path(forResource: "fileName", ofType: "rType")

// 데이터 불러오기
if let path = filePath {
    let image = UIImage(contentsOfFile: path)
}
```

### Plist File load for Bundle
```swift
func sample{
    let loadDataDic = loadPlist(fileName:"fileName")
}

func loadPlist(fileName:String) -> [String: String]{
    // 1. Path
    if let bundlePath = Bundle.main.path(forResource: fileName, ofType: "plist"){
        // 2. Data 로드
        do{
            let data = try Data(contentsOf: URL(fileURLWithPath: path)
            //3. Dictionary
            let dic = try PropertyListSerialization.propertyList(from: data, options: .mutableContainersAndLeaves, format: nil) as! [String: String]

            return dic
        }catch{
            print("error")
        }
    }
}
```
