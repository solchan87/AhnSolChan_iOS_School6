# Swift 기초 문법
> 2018.01.10 업데이트

### 변수와 함수
* 변수 : 프로그램에서 데이터의 저장 공간을 담당
> 키워드 + 변수명(Name): + 변수 타입(Type) = 값(Value) / 문법 예)
```swift
var vName: Any = 3
```
* 함수 : 프로그램이 실행되는 행동을 담당
> 키워드 + 함수명(Name) + 입력값(Input Value) + 함수 내용(Action) + 결과 타입
```swift
func fName(Parameter: Any) -> Any
{
    //함수 내용
}
```


#### 연습
나만의 person Class를 만들어 보시오.
```swift
import Foundation

class Person {
    var name: String = ""
    var age: Int = 0
    var eye: Double = 0
    var tall: Double = 0
    
    func eat(money: Int) {
        print("\(name)이 \(money)원의 점심을 먹습니다.")
    }
    
    func run(distance: Int, speed: Int) {
        print("\(name)이 \(speed)의 속도로 \(distance)m를 달렸습니다.")
    }
    
    func checkBody() {
        print("\(name)의 나이는 \(age)살이고 키는 \(tall)cm, 시력은 \(eye)입니다.")
    }
    
}
```

### 주석 처리
* 주석 앞에 `//`를 사용해서 한줄씩 주석처리를 할 수 있다.
> `command` + `/` 단축키로 주석을 설정/해제할 수 있다.
```swift
//주석을 작성할 수 있다.
//라인별로 주석을 작성해야 된다.
```
* `/*` 시작 기호와 `*/` 끝기호를 사용하여 여러 라인의 줄을 모두 주석 처리할 수 있다.
```swift
/*
    이안의
    모든 내용은
    주석으로 처리가
    가능하다.
*/
```

