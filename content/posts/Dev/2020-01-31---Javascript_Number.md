---
title: 자바스크립트 숫자
date: "2020-01-31T15:46:37.121Z"
template: "post"
draft: false
slug: "Javascript_Number"
category: "Javascript"
tags:
  - "Javascript"
description: "자바스크립트에서 숫자 다루는 법을 정리해 보았다."
---## Number

Number 숫자 메소드
여러가지 수학 계산에 대한 메소드
https://www.w3schools.com/js/js_math.asp

절대값 구하기, sin, cos, 제곱근 등등 Math 객체에는 수학 계산에 대한 메소드가 많이 있습니다. 그 중에서 몇가지만 살펴봅시다

Round 반올림 함수
`Math.round()`

`console.log(Math.round(2.5)) // 3`
우리가 사람들에게 숫자 데이터, 예를 들면 평점과 같은 숫자를 받고 그에 대한 평균값을 구한다면 그 결과는 소수점으로 나오게 될 것이다.
이러한 소수점 결과를 깔끔하고 보기 쉽게 만들기 위해서 우리는 반올림, 올림,내림과 같은 함수를사용하게 된다.

**Ceil 올림 함수**
`Math.ceil()`

`console.log(Math.ceil(2.3)) // 3`

ceil은 천장을 의미하므로 천장까지 올린다고 연상하면 될 것 같습니다.

**Floor 내림 함수**
`Math.floor()`

`console.log(Math.floor(2.9)) // 2`

floor은 바닥을 의미하므로, 바닥까지 끌어내린다고 연상하면 되겠죠?

### 유용한 Number 함수! 랜덤 함수

**Random**
자바스크립트에는 랜덤한 숫자를 만들어주는 랜덤 함수가 있습니다.

```js
var randomNumber = Math.random();
console.log(randomNumber);

// 0.7399028302061925
```

이때 나오는 결과는 0.0000000000000000에서 0.9999999999999999 의 값
즉 0에서 1미만의 값을 보여줍니다.
이러한 결과에 내가 원하는 범위로 곱하면 우리가 생각하는 랜덤한 숫자를 얻을 수 있습니다.

만약 한자리 숫자를 얻고 싶다면?

```js
var randomNumber = Math.random();
console.log(Math.floor(randomNumber * 10));
// ex) 9.697009826327621
```

이렇게 나온 랜덤한 값에서 내가 얻고 싶은 9만 취하고 나머지는 내림함수로 버리고, 9만 남기는 것입니다. 이런 방식을 통해서 우리는 로또를 추첨하거나 이벤트 당첨자를 구하는 등의 랜덤한 결과를 얻을 수 있습니다. 참 유용하죠?

**Quiz**

최소(min), 최대값(max)을 받아 그 사이의 랜덤수를 return하는 함수를 구현해봅시다.

```js
function getRandom(min, max) {
  return Math.floor(Math.random() * (max - min + 1) + min);
}
```

1. 왜 max - min + 1 인가?
   우리가 만약 3부터 10까지의 랜덤한 숫자를 얻고 싶다면?
   여기서 질문, 3부터 10까지는 숫자가 몇 개 있을까?
   3, 4, 5, 6, 7, 8, 9, 10 총 8개의 숫자가 있다.
   이걸 다 써보지 않아도 구할 수 있는 방법이 없을까요?
   10 - 3 = 7
   7 + 1 = 8 ( 찾았네요! )
   최대값에서 최소값을 빼고, + 1 을 더하면 몇 개인지 구할 수 있는 것입니다.
   그래서 max - min + 1을 해줍니다.

2. Math.random() _ (max - min + 1)
   0.0000000000000000에서 0.9999999999999999 의 값에, 8을 곱한다고 하면? 0.****\_**** ~ 7.****\_**** 의 랜덤한 값이 나오게 됩니다.
   1 _ 8은 8이지만, Math.random()으로 나오게 될 값은 1을 절대 넘지 않을 것입니다.
   그런데 우리가 구하고 싶은 값은 0부터 7까지의 값이 아니죠, 3부터 10까지의 값입니다.
   감이 오시나요? 맞습니다. 0 ~ 7 그리고 3 ~ 10.
   뭔가 더하고 싶은 마음이 들죠?

3. Math.random() \* (max - min + 1) + min
   우리는 3에서 10까지의 값을 구하고 싶은 것이므로 0.****\_**** ~ 7.****\_**** + 3을 해주면, 3.**\_\_\_** ~ 10.**\_\_\_** 의 값이 나오게 되는 것이죠.

4. Math.floor((Math.random() \* (max - min + 1)) + min);
   깔끔한 정수를 얻기 위해서 나머지 소수점을 버려야 합니다.
   그래서 Math.floor로 이 결과를 감싸줍니다.