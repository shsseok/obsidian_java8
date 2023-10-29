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
>String str="abc"
  Optional<String> optVal = Optional.of(str);
str 0x100 -> "abc"
optVal 0x200 -> 0x100 
-
