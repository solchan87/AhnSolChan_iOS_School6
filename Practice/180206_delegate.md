# Swift 문법
> 2018.02.06 업데이트    

## Delegate Pattern
* 내용

### 프로토콜(Protocol)
* 프로토콜은 원하는 작업이나 기능을 구현되도록 메서드, 프로퍼티등으로 요구사항의 청사진을 정의합니다.  
* 클래스, 구조체, 열거형은 프로토콜을 채택하면, 프로토콜에서 요구한사항에 대해 구현해야 됩니다.   
* 프로토콜을 통해 공통적인 작업을 강제할 수 있으며, 해당 프로토콜을 채택한 사람이 구현한 메소드에 대한 정보도 알수 있다

#### Protocol 문법
```swift
protocol Runable { 
    var regCount: Int { get set }
    func run()
}

class Animal: Runable {
    var regCount: Int = 0
    func run() {

    }
}
```

#### Protocol 채택
* 프로토콜 간 채택한 모든 것들을 클래스에서 선언해줘야 된다.

```swift
protocol Runable { 
    var regCount: Int { get set }
    func run()
}

protocol Flying: Runable {
    var wingCount: Int { get set }
}

class Animal: Runable {
    var regCount: Int = 0
    var wingCount: Int = 0
    func run() {

    }
}
```

#### 추상 클래스로의 Protocol