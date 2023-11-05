---
sticker: emoji//1f600
---
담을 객체 모델 다음에 와야한다.

내부에서 파라미터 자리 정보를 사용하여 Validation을 적용할 객체를 정하기 때문

reject() -> 글로벌 오류라고 생각하자
`reject()`는 폼 전체적으로 무언가 잘못되었을 때 사용

```java
if (user.getName().isEmpty() && user.getEmail().isEmpty()) { errors.reject("formError", "이름과 이메일은 반드시 입력해야 합니다."); }
```

rejectValue() 
`rejectValue()`는 특정 필드(예: 나이 필드)에 문제가 있을 때 사용

```java
if (user.getAge() < 0) {
    errors.rejectValue("age", "negativevalue", "나이는 0보다 커야 합니다.");
}
```