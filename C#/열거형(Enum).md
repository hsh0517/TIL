# 열거형(Enum)

Unity C# 공부 3

- **열거형** : 정수형 상수에 이름을 붙임 (기본 형식 = int)
```csharp
// 열거형 데이터 형식 정의
// enum 열거형이름 { 열거자1 = 초기값, 열거자2.... };

// 초기값 생략 가능 (0으로 자동 초기화)
// 초기값이 할당되고 다음 값을 지정하지않았다면
// 앞에 값 + 1 의 값이 할당됨 (ex. 1, 2, 3, ......)
// 열거자는 앞에있는 열거자 값보다 커야함
enum EnumTest { e1, e2, e3 }

// 열거형 변수 선언
// 열거형이름 열거형변수이름 = 열거형이름.열거자;
EnumTest EEE = EnumTest.e1;

// 다른 정수 형식은 이름 옆에 콜론을 붙여 선언
enum Day:Byte { Sat, Sun, Mon, Tue, Wed, Thu, Fri };

// 열거형 형 변환
// int 정수형변수이름 = (int) 열거형변수이름;
//열거형데이터형식 열거형변수이름 = (열거형데이터형식)정수형변수이름;

// enum 열거자들은 Tostring 과 Format 메서드를 통해 문자열 변환이 가능
```
---
- 활용예제
```csharp
using UnityEngine; 

public class EnumExample : MonoBehaviour 
{ 
    enum Day { Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday };
    enum Month : byte { Jan = 1, Feb, Mar, Apr, May, Jun, Jul, Aug, Sep, Oct, Nov, Dec };

    void Start() 
    { 
        Day today = Day.Monday;
        int dayNumber = (int)today;
        Debug.LogFormat("{0} is day number {1}.", today, dayNumber); 
        // 출력
        // Monday is day number 1  

        Month thisMonth = Month.Dec;
        byte monthNumber = (byte)thisMonth;
        Debug.LogFormat("{0} is month number #{1}.", thisMonth, monthNumber); 
        // 출력
        // Dec is month number 12  
    } 
}
```
- 플래그(Flags) enum : 열거자를 비트값에 할당, enum .... 위에 [Flags] 작성하면 됨, 비트연산이 가능