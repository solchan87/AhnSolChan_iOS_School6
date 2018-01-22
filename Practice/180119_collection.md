# Swift 문법
> 2018.01.18 업데이트    

## Collection Type
* Swift는 값의 모음을 저장하기위한 `Array`(배열), `Set`(집합), `Dictionary`(사전)이라는 세가지 기본 형식을 제공한다.  
* `Array`(배열)는 정렬된 값의 모음이며, 배열은 Index값을 가지고 있다.   
* `Set`(집합)은 고유 한 값의 정렬되지 않은 모음이며, 두개의 집할을 비교하여 값을 얻을 수 있다.   
* `Dictionary`(사전)는 키-값의 정렬되지 않은 모음이며, 키의 매칭을 통해 값을 찾을 수 있기 때문에 키는 중복될 수 없다.   

### Mutability of Collections
* Collection을 `var`에 할당하면 추가, 제거 수정등 변경이 가능하다.   
* 하지만, `let`에 할당하면 Collection을 변경할 수 없다.   

## Array
* 배열(Array)은 번호(Index)와 번호에 대응하는 데이터(Value)들로 이루어진 자료 구조를 나타낸다.   
* 일반적으로 배열에는 같은 종류의 데이터들이 순차적으로 저장되며, 값(Value)의 번호(Index)가 곧 배열의 시작점으로부터 상대적인 위치로 저장된다.   

### Array 문법
* 기본 표현은 Array<Element>로 Array Type을 나타낸다.  
```swift
// 빈 배열은 타입을 추론할 수 없기 때문에 좌변에서 타입 선언을 해야 한다.
// 여기에서 Element는 배열에 저장할수 있는 타입이다.
var arr1 = Array<Element>()
var arr2: Array<Element> = Array()
var arr3 = [Element]()
var arr4: [Element] = []

// 배열리터럴
let arr5 = [1, 2, 3, 4, 5]
let arr6 = Array(arrayLiteral: 1, 2, 3, 4, 5)

// 시퀀스
let arr7 = Array(1...5) // CountableClosedRange<Int> : Sequence
let chars = Array("hello world".characters)
```

