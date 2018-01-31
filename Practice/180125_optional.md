# Swift 문법
> 2018.01.31 업데이트    

## 옵셔널 (Optional)
> Swift가 가진 가장 큰 특징 중 하나가 Optional이다. 이는 값이 있을 수도 없을 수도 있음을 나타낸다.


#### nil
```swift
class Person{
    var name: String
    init(name: String) {
        self.name = name
    }
}

let person2: Person
print(person2.name)
```
> 변수 선언 후 초기화 하지 않은 상태를 nil이라 한다.

### Type Safety
* nil인 상태에서 속성을 참조하거나, 함수를 실행시 발생하는 error로 인한 코드의 불안정성 내포.  
* Swift의 중요한 특징 중 하나는 Safety이다. 
* Type Safety를 위해 컴파일러 수준의 nil 체크한다.
* 만약 nil인 변수 선언을 해야할 경우 optional을 사용한다.    
* optional은 두가지 가능성을 가질수 있는데한개는 값이 있음을 나타내고또다른 한가지는 nil일 가능성을 내포하고 있다.(?기호 사용)