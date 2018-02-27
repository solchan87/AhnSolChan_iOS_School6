# Swift 문법
> 2018.02.26 업데이트    

## Enumeration (열거형)
* 그룹에 대한 연관된 값을 정의하고 사용가능한 타입.    
* 다른 언어와 달리 항목 그자체가 고유의 값으로 해당 항목에 값을 매칭 시킬 필요가 없다.(C계열 언어는 Int타입의  값이 매칭됨.   
* 원시값(rawValue)이라는 형태로 실제 값(정수, 실수, 문자등)을 부여 할수 있다.   
* 열거형의 이니셜라이즈를 정의 할수 있으며, 프로토콜 준수, 연산프로퍼티, 메소드등을 만들수 있습니다.

### Enumeration 문법
```swift
enum enumName {
    case enumItem1
    case enumItem2
    case enumItem3
}
```

#### 예제)
```swift
// CompassPoint 자체가 타입
enum CompassPoint {
    case north
    case south
    case east
    case west
}

var directionToHead = CompassPoint.west
directionToHead = .north
```
> 열거형의 대표적인 예로 switch문이 있다.   

