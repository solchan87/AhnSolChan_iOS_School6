# Swift 문법
> 2018.01.15 업데이트

## 이론 강의
### 변수
* 변수명  
> 명명 규칙에 따라서 작성   
> 유니코드 문자를 포함하여 모든 문자가 포함될 수 있다.(한글 가능)   
> 변수안에 들어있는 데이터를 표현해 주는 이름으로 작성   
> 중복 작성 불가 (한 클래스, 함수, 구문 안에서)   

* 명명 규칙  
> 시스템 예약어는 사용할 수 없다     
> 변수명 시작에 숫자가 올 순 없지만 변수명에는 포함될 수 있다     
> 공백을 포함할 수 없다   
> 변수명은 lowerCamelCase로 작성   
> 클래스 명은 UpperCamelCase로 작성  

### 변수 타입  
1. **Int**
   - 정수형 타입 Integer  
   - Int : +/- 부호를 포함한 정수, Uint -부호를 포함하지 않는 0을 포함한 양의 정수  
   - 최대 값과 최소 값은 .max와 .min 프로퍼티를 통해 알 수 있다.  
   - Int8, Int16, Int32, Int64, UInt8, UInt16, UInt32, UInt64의 타입으로 나눠져   있는데 기본은 시스템 아키텍쳐에 따라서 달라진다.   
   - 접두어에 따라 진수를 표현할수 있다. (2진법 0b, 8진법0o, 16진법0x)  

2. **Double**  
   - 부동 소수점을 사용하는 실수형 타입  
   - 64비트의 부동소수점은 Double, 32비트 부동 소수점은 Float으로 표현한다.  
   - Double은 15자리,Float은 6자리의 숫자를 표현가능   

3. **String**
   - 문자의 나열, 문자열이라고 한다.  
   - Character와 마찬가지로 유니코드로 이뤄져 있다.  
   - 문자열을 다루기 위한 다양한 기능이 제공된다.(hasPrefix, uppercased, isEmpty등)  
   - 문자열을 Character로 분해하여 꺼낼 수 있다.  
   - String의 문자 하나를 부를때는 Character를 사용한다.  

4. **Bool** 
   - 참(true)과 거짓(false)를 나타내는 타입   

5. **튜플**
   - 정해지지 않은 데이터 타입의 묶음  
   - 소괄호 ( ) 안에 타입을 묶음으로 새로운 튜플타입을 만들수 있다. `(Int, Int)`, `(String, Int, String)`   
   - 각 타입마다 이름을 지정해 줄수도 있다. `(name:String, age:Int)`   
```swift
    var sampleTuple: (Int, sName: String, Int) = (3, "joo", 4)
    print(sampleTuple.0) // 3
    print(sampleTuple.sName) // joo
```

6. **캐스팅 변환**
   - 데이터 유형이 같지 않을 경우 데이터간 연사이 안되기 때문에 캐스팅 후 연산을 할 수 있다.
```swift
     var stringNum: String
     var doubleNum: Double

     let intNum: Int = 3

     stringNum = String(intNum) //int to String
     doubleNum = Double(intNum) //int to Double
```


