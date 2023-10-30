---
sticker: emoji//1f600
---
[[래퍼 클래스]]

## Optional이란?

T타입 객체의 래퍼클래스

---

## 왜 쓰는가? 
1. null을 직접 다루는 것은 위험하다 (NullpointEx) 발생 방지
2. 간접적으로 null을 다루기 위해서
3. null을 다루게 된다면 null 체크를 한다 --> 이느 if 문 남발 코드 지저분 -> 방지

---
>[!example]
>str 0x100 -> "abc"
optVal 0x200 -> 0x100
>String str="abc"
  Optional<String> optVal = Optional.of(str);

## Optional 객체 생성 하는 법

```java
String str="abc";  
Optional<String> optional1 = Optional.of(str);  
Optional<String> optional2 = Optional.of("abc");  
//Optional<String> optional3=Optional.of(null);  
Optional<String> optional4=Optional.ofNullable(null);  
  
Optional<String> optional5=Optional.empty();
```  
Optional을 초기화 할때는 빈 옵셔널로 초기화 하자
---


```java 
String str1=optional4.orElse("dddd"); //Null일 때는 무엇을 가지고 올래? (파라미터 값)  
System.out.println(str1);  
String str2=optional1.orElseGet(()->new String()); //--Suplier 람다식 사용가능  
System.out.println(str2);

```

