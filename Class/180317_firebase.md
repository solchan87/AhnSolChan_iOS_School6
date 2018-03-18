# Framework 정리
> 2018.03.17 업데이트

## Firebass
* 클라우드 서비스 제공자이며, 동시에 BackEnd 기능을 가지고 있다.   
    - 다양한 플랫폼과 기기에서 어플리케이션 데이타를 실시간 동기화를 지원.  
> iOS에서 작성해도 안드로이드에서 바로 볼 수 있음

1. Authentication
2. RealtimeDatabase
3. Storage 
4. Crash Report-Analytics

### Analytics
* Firebase Analytics는 Google이 모바일앱을 위해 선보이는 완전히 새롭고 무제한 사용할 수 있는 무료 분석 솔루션입니다. 이 솔루션은 크게 두가지 차이점이 있습니다.

1. Firebase Analytics는 사용자 및 이벤트 중심적으로 설계되었습니다. 전통적인 페이지뷰, 화면뷰, 그리고 세션에 중점을 두는 대신 사용자들이 여러분의 앱에서 무엇을 하는지 파악할 수 있게 해줍니다. 또한, 사용자들이 어디서 오는지 알 수 있는 교차 네트워크 특성을 통해 여러분의 유료 광고 캠페인이 어떤 성과를 거두고 있는지도 확인할 수 있습니다. 이 모든것들을 하나의 대시보드에서 볼 수 있습니다.

2. Firebase Analytics는 Firebase는 다양한 기능을 통합할 수 있는 잠재고객 기능을 통해 공통의 특성을 지닌 사용자 그룹을 정의할 수 있습니다. 사용자 그룹이 정의되면 다른 Firebase 기능을 활용할 때 특정 그룹을 기반으로 기능을 적용할 수 있습니다.

### 코드 예제

#### AppDelegate.swift
```swift
import UIKit
import Firebase

@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {

    var window: UIWindow?

    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
        FirebaseApp.configure()
        return true
    }
}
```

#### ViewController.swift
```swift
class ViewController: UIViewController {
    
    var ref: DatabaseReference!

    @IBOutlet weak var addedLb: UILabel!
    @IBOutlet weak var insertNameTf: UITextField!
    @IBOutlet weak var insertValueTf: UITextField!
    
    @IBOutlet weak var deleteNameTf: UITextField!
    
    @IBOutlet weak var selectNameTf: UITextField!
    @IBOutlet weak var selectValueTf: UITextField!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        ref = Database.database().reference()
        
        ref.child("JSON").observeSingleEvent(of: .value, with: { DataSnapshot in
            
            let value = DataSnapshot.value as? NSDictionary
            let name = value?["Name"] as? String ?? ""
            
            print("Name : " + name)
        })
        
        ref.observe(.childAdded, with: { DataSnapshot in
            self.addedLb.text = DataSnapshot.value as? String
        })
    }
    
    @IBAction func insertBtn(_ sender: Any) {
        let itemRef = ref.child((insertNameTf.text?.lowercased())!)
        itemRef.setValue(insertValueTf.text)
        
        insertNameTf.text = ""
        insertValueTf.text = ""
    }
    
    @IBAction func deleteBtn(_ sender: Any) {
        ref.child(deleteNameTf.text!).removeValue(completionBlock: { (error, ref) in
            if error != nil{
                print("error \(String(describing: error))")
            }
            self.deleteNameTf.text = ""
        })
    }
    
    @IBAction func selectBtn(_ sender: Any) {
        ref.child(selectNameTf.text!).observeSingleEvent(of: .value, with: { DataSnapshot in
            
            let value = DataSnapshot.value as? String
            
            self.selectValueTf.text = value
        })
    }
}
```