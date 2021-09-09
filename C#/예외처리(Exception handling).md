# 예외처리(Exception handling)

Unity C# 공부 4

- **try, catch** : 실행문, 예외 실행문
```csharp
try
{
    // 실행문
}
catch (object) // 예외객체
{
    // 예외 발생 시 실행문
}
```
예제
```csharp
using UnityEngine; 
using System; 

public class TryCatch : MonoBehaviour 
{ 
    GameObject obj; 

    void Start() 
    { 
        //obj = new GameObject();  

        try 
        { 
            Debug.Log(obj.name); // obj를 할당하지 않아서 예외발생
        } 

        catch (Exception ex) 
        { 
            Debug.Log(ex); // 출력 : System.NullReferenceException: Object reference not set to an instance of an object  
        } 

        Debug.Log("이부분도 출력됨"); // 출력 : 이부분도 출력됨 
    } 
}
```
---
- **try, finally** : 실행문, 예외 발생 유무에 관계없이 반드시 실행되는 문
```csharp
try
{
    // 실행문
}
finally
{
    // 예외 발생 유무에 관계없이 반드시 실행되는 문
}
```
예제
```csharp
using UnityEngine; 
using System; 

public class TryCatchFinally : MonoBehaviour 
{ 
    GameObject obj; 

    void Start() 
    { 
        //obj = new GameObject();  

        try 
        { 
            Debug.Log(obj.name); 
        } 
        catch (Exception ex) 
        { 
            Debug.Log(ex); // 출력 : System.NullReferenceException: Object reference not set to an instance of an object  
        } 
        finally 
        { 
            Debug.Log("이부분도 출력됨"); // 출력 : 이부분도 출력됨
        } 

        Debug.Log("이부분도 출력됨"); // 출력 : 이부분도 출력됨
    } 
}
```
---
- **throw** : 예외를 임의로 발생시킴
```csharp
using UnityEngine; 
using System; 

public class Throw : MonoBehaviour 
{ 
    void Start() 
    { 
        throw new Exception("임의의 예외"); // 에러 발생. 출력 : Exception: 임의의 예외
    } 
}
```