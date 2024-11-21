# DATA TYPES
------------
## Lists

- List 키워드를 적고 선언하거나, 요소의 자료형으로 list를 표현할 수 있다

```dart
void main(){
  int case1 = [1,2,3,4,5];
  List case2 = [1,2,3,4,5];
  List<int> case2 = [1,2,3,4,5];
}
```

- collection if 와 collection for 지원 → 이게 정말 좋은 기능!
- 존재할 수도 있고 안할 수도 있는 요소를 가질 수 있다
    - collection if 예시
        
        ```dart
        void main(){
          var giveMeSix = true;
          int case1 = [
            1,
            2,
            3,
            4,
            5
            if(giveMeSix) 6,
          ];
        }
        ```
        
    - collection for → 아래에서 설명 예정

## String Interpolation

- 문자열에 변수를 추가하는 방법
    - 단순 변수값을 담는 경우에는 $변수명
    - 무언가를 계산하고 싶다면 ${계산식}
    - String 내부에서 따옴표를 사용할 경우 \’, \” 사용 → escape 문자

```dart
void main(){
  var name = "tom";
  var age = 10;
  var greeting = "hello $name, I\'m ${age + 5}";
}
```

## Collection For

- for문을 사용하여 list를 구성할 수 있다

```dart
void main() {
  var oldFriends = ["nico", "lynn"];
  var newFriends = [
    "tom",
    "jon",
    for (var friend in oldFriends) "❤️ $friend",
  ];
  print(newFriends); // [tom, jon, ❤️ nico, ❤️ lynn]
}
```

→ Lists 내부에 다음과 같은 String Interpolation를 사용할 수 있다

## Map

- key와 value를 연결하는 객체
    - var 로 선언하거나, Map 키워드를 통해 직접 선언 가능하다

```dart
void main() {
  var player = {
    'name': 'jungsun',
    'xp': '19.99',
    'superpower': 'false'
  };
  
  Map<int, bool> some = {
    1: true,
    2: false,
    3: true
  };
}
```

## Sets

- Set은 중괄호, List는 대괄호로 표현한다
    - Set은 모든 요소들이 unique 해야할 때 사용한다
    - unique 해야할 필요가 없다면 List를 사용한다

```dart
void main() {
  var numbers = {1, 2, 3, 4, 5};
  Set<int> numberSet = {1, 2, 3, 4, 5};
}
```
