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

#### 예제1)
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
> 열거형의 대표적인 예로 Optional이 있다.  

#### 예제2)
```swift
enum Barcode {
    case upc(Int, Int, Int, Int)
    case qrCode(String)
}

// 연관 열거형 값 지정
var productBarcode = Barcode.upc(8, 85909, 51226, 3)
productBarcode = .qrCode("ABCDEFGHIJKLMNOP")

// 연관 열거형 값 불러오기
switch productBarcode {
    case .upc(let numberSystem, let manufacturer, let product, let check) :
        print("UPC: \(numberSystem), \(manufacturer), \(product), \(check).”)
    case .qrCode(let productCode) : 
        print("QR code: \(productCode).")
}

// Pattern Matching - 값이 매칭할 경우 정상 바코드 구문 실행   
let productBarcode = Barcode.upc(8, 85909, 51226, 3)

if case let Barcode.upc(8, companyCode, productCode, 3) = productBarcode {
    // 정상바코드
    print(companyCode) 
    print(productCode) 
}
```
> 항목에 값을 지정해서 사용하며, 스위치문을 통해서 값을 가지고 와 사용할 수 있다.

### Row Value
```swift
enum ASCIIControlCharacter: Character {
    case tab = "\t"
    case lineFeed = "\n"
    case carriageReturn = "\r"
}
// 첫번째 값에 rowValue를 지정해주면, 지정한 수부터 하나씩 번호가 지정된다
enum Planet: Int{ 
    case mercury = 1, venus, earth, mars, jupiter, saturn, uranus, neptune
}
let earthsOrder = Planet.earth.rawValue
    // earthsOrder is 3 
// Initializing from a Raw Value
let possiblePlanet:Planet? = Planet(rawValue: 1)
    // possiblePlanet is mercury

// rowValue를 지정하지 않을경우 자동으로 값이 들어간다.
enum CompassPoint: String { 
    case north, south, east, west 
}
let sunsetDirection = CompassPoint.west.rawValue
    // sunsetDirection is "west"
```
> .rawValue 프로퍼티를 통해 원시값을 가져올수 있다.

#### Initializing from a Raw Value
* 원시값 열거형에서는 초기화 함수를 통해 instance를 만들수 있다. (rawValue:값 지정으로 인해 생성) 
* 초기화를 통해 만든 인스턴스는 옵션널 변수로 만들어 진다.
