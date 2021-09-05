# 문자열(String)

Unity C# 공부 2

- **문자열** : 문자들의 배열. 유니티에서 로그, UI 에 자주 사용됨.
```csharp
// string 변수이름 = "값";
string name = "Hong";

string message1 = "message1"; // 일반적인 초기화.
string messaeg2 = null; // null로 초기화. 값 없음.
string message3 = ""; // null과 달리 빈칸으로 초기화.
string message4 = string.Empty; // message3과 동일.

// 문자는 char 키워드와 ''(작은따옴표)를 사용하고,
// 문자열은 string 키워드와 ""(큰 따음표)를 사용함.

// 문자열도 배열처럼 인덱스로 접근 가능
char a1 = name[0]; // a = 'H'

// ToCharArray : 문자열을 문자 배열로 변환
char[] charArray1 = name.ToCharArray();

// 문자열 연결 + 연산자, += 연산자
string array_a = "Hello";
string array_b = "World";
string array_c = array_a + array_b; // array_c = HelloWorld
array_b += array_a; // array_b = HelloWorld
```

- **이스케이프(Escape) 시퀀스**
백 슬래시( \\ ) + 특정 문자 형태로 문자열 안에서 특수 문자, 기능 수행
대표적인 것들만 정리

|이스케이프 시퀀스|문자 이름|
|:--:|--|
|\\'|작은 따옴표|
|\\"|큰 따옴표|
|\\\|백 슬래시|
|\\0|Null|
|\\b|백 스페이스|
|\\n|줄 바꿈|
|\\t|탭(tap)|