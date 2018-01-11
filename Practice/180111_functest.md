```swift
import Foundation

class human {
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