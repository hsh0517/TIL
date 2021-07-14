# C++ 기초 문법
이미 C 언어를 잘 알고, C#(Unity)를 통해 객체지향을 알고있는 상태에서 작성함
### 1. 입출력, 표준 네임스페이스

- C 언어와 다른 기본 입출력, 헤더
- 범위 지정자 :: 으로 네임스페이스에 따라 구분 ex) std::cout
- 위에 using namespace std; 를 적음으로써 std:: 삭제 가능

| C언어 | C++ |
|:--:|:--:|
| stdio.h | iostream |
| printf() | cout |
| scanf() | cin |
```cpp
#include <iostream>                 // C 언어의 <stdio.h>

int main(void){
    int num;
    std::cout << "숫자 입력 :";      // C 언어의 printf
    std::cin >> num;                // C 언어의 scanf
    std::cout << num << endl;       // endl = C 언어의 \n
    return 0;
}
```
- 문자열 입력
```cpp
#include <iostream>
using namespace std;                // 네임스페이스 사용

int main(void){
    char arr[10];
    cout << "문자 입력";
    cin >> arr; 
    cout << "내용 : " << arr;
    
    cout << strlen(arr) << endl; 
    cout << arr[0] << endl;
    return 0;
}
```
- 공백 포함 문자열 한 줄 입력
- getline(문자열, 최댓값, 종결문자);
*(종결문자는 선택사항)* 예시: cin.getline(arr,10,' '); => 공백으로 종결
```cpp
#include <iostream>
using namespace std;

int main(void){
    char arr[10];
    cout << "문자 입력";
    cin.getline(arr,10);
    cout << arr;
    return 0;
}
```
___
### 2. 자료형
- C 언어에 없고 가장 간단한 자료형만 정리

|이름|구조|값|
|:--:|:--:|:--:|
|bool|자료형|true 또는 false|
|char|배열|u8 리터럴 시 UTF-8 문자열로 인코딩|
|string|문자열 컨테이너|문자열|
|auto|추론|초기화된 변수|
___
### 3. 클래스
|접근 지정자|의미|
|:--:|:--:|
|private|해당 클래스 안에서만 접근 가능|
|protected|상속받은 클래스 까지만 접근 가능|
|public|클래스 외부에서도 접근 가능|
```cpp
class MyParent {
    // 타 언어와 다르게 콜론(:) 사용
    private:
    int a = 0;

    protected:
    string text = u8"Hello World";

    public:
    void print() {
        cout << text << endl;
    }
};
```
클래스의 개념은 다른 언어에서 쉽게 알 수 있음.
___
### 4. 생성자
- 클래스 생성 시점에서 객체 초기화를 위해 실행
- 클래스 이름(매개 변수) 로 함수 작성
```cpp
class MyClass {
   public:
   MyClass(...) {
      [생성자 내용]
   }
}
```
___