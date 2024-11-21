# 들어가기에 앞서
--------------
Flutter로 앱을 만들고 싶다면 가장 먼저 배워야 하는 언어가 바로 Dart.
이 강의를 통해 Dart와 친숙해지는 것이 목표이다.

# Dart
--------------
## Dart란?

- 객체 지향 언어
- 구글에서 만듦
- User interface에 최적화 되어 있음
- 다른 주류 프로그래밍 언어와 유사

## 왜 flutter에서는 Dart를 사용하는가

- UI에 최적화
- 생산적인 개발 환경
- 모든 곳에서 작동하도록 컴파일 할 수 있음
- Dart 가상 머신에서 JIT 컴파일러 사용 
    - 네가 쓴 코드의 결과를 바로 볼 수 있다
- null safety

<aside>
💡
flutter, Dart 모두 구글이 만들었기 때문에 flutter에 맞춰서 Dart 언어를 수정하여 최적화할 수 있다
</aside>

## 어떻게 공부하나요?

- dart 에디터 사용
[DartPad](https://dartpad.dev/)

# VARIABLES
--------------
## Hello World

- 메인 함수는 반드시 필요
    - 무언가를 수행하는 코드는 반드시 main 내부에 작성해야 한다

```dart
void main() {
  print("hello world");
}
```

- js 나 ts의 경우에는 formatter가 문장의 끝에 자동으로 세미콜론을 붙여주지만 dart는 그렇지 않다
    - 세미콜론을 쓰지 않는 `cascade operator`의 경우가 존재한다

## The Var Keyword

변수 정의 방법은 두가지가 있다
1. 변수 타입에 대한 지정 없이 var로 정의
    
    ```dart
    var name = “name”;
    ```
    
    - 변수 업데이트 시 기존 타입과 동일해야 함
    - 관습적으로 함수나 메소드 내부에 지역 변수를 선언할 때는 var를 사용

2. 변수의 타입으로 정의
    
    ```dart
    String name = "name";
    ```
    
    - class에서 변수나 property를 선언할 때에는 타입을 지정하여 사용

## Dynamic Type

- 여러가지 타입을 가질 수 있는 변수에 쓰는 키워드
    - var로 변수 선언 시 변수 값을 초기화하지 않을 경우 해당 변수는 dynamic type으로 지정됨
    
    ```dart
    void main() {
      var name;
      name = "name";
      name = 12;
      name = true;
    }
    ```
    
- 어떨 때 이 타입을 사용할까?
    - dynamic 으로 변수를 선언하고 해당 변수의 타입을 체크하면 그에 맞는 다양한 속성들을 사용할 수 있다
    - 단, dynamic의 사용은 일반적으로 지양되며 꼭 필요할 때에만 사용하도록 한다
    
    ```dart
    void main() {
      dynamic name;
      if(name is String) {
    	  // 다양한 String 관련 속성들 사용 가능
      }
      if(name is int) {
        // 다양한 int 관련 속성들 사용 가능
      }
    }
    ```


## Nullable Variables

- null safety : 개발자가 null 값을 참조할 수 없도록 한다
    - 컴파일 전에 null과 관련한 다양한 에러를 잡아내는 데 유용
- 사용 방법
    - 기본적으로 모든 변수는 non-nullable 이다
    
    ```dart
    void main() {
      String name = "hello";
      name = null;
    }
    // 이럴 경우 name 은 non-nullable 이므로 에러 발생
    ```
    
    - 타입 뒤에 “?”를 붙여줌으로서 name이 해당 타입 또는 null이 될 수 있다고 명시해주는 것이다
    
    ```dart
    void main() {
      String? name = "hello";
      name = null;
    }
    ```


## Final Variables

- 한 번 정의된 변수를 수정할 수 없게 만드려면 final로 정의하면 된다
- javascript에서의 const 와 동일한 개념이다

```dart
void main() {
  final name = "name";
  final String nickname = "js";
  name = "jungsun"; // 수정 불가
}
```


## **Late Variables**

- 변수 선언 맨 앞에 붙여주는 키워드로, 데이터 없이 변수를 만들어준다
    - 따라서 값을 넣기 전까지는 접근할 수 없다
- data fecthing 시 유용하게 쓰인다
    - api에서 얻어온 값을 저장해야할 때 late 키워드를 통해 변수 선언을 먼저 하고, 나중에 값을 넣는다

```dart
void main() {
  late final String name;
  print(name); // name 변수에 접근 불가
}
```

## Constant Variables

- const 키워드
    - compile time constant 를 만들어준다
    - 컴파일 때 알고 있는 값

<aside>
💡
javascript에서 사용하는 const는 final과 유사한 개념

</aside>

- final vs const
    ```dart
    void main() {
      const name = "tom"; // 컴파일 시점에 바뀌지 않는 값
      final username = fetchAPI(); // 컴파일 시점에 바뀌는 값
    }
    ```
    
    - const: 컴파일 시점에 바뀌지 않는 값 (상수)
    - final: 컴파일 시점에 바뀌는 값 (API에서 받아온 값, 사용자 입력값)
