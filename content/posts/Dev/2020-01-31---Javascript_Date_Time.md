---
title: 자바스크립트 날짜, 시간 구하기
date: "2020-01-31T15:46:37.121Z"
template: "post"
draft: false
slug: "Javascript_Date_Time"
category: "Javascript"
tags:
  - "Javascript"

description: "자바스크립트에서 날짜와 시간을 다루는 법을 정리해 보았다."
---## 날짜와 시간

우리는 어떻게 날짜와 시간을 다룰 수 있을까? 친절하게도 우리에게는 날짜 객체가 있다.
날짜 객체를 호출하면 시간과 날짜를 얻을 수 있다.

```js
var rightNow = new Date();
console.log(rightNow);
```

콘솔 로그
`Fri Jan 31 2020 10:28:58 GMT+0900 (한국 표준시)`

브라우저마자 시간을 표현하는 방식은 모두 다르다.
하지만 보통 이 데이터 그대로 사용하기 보다는 가공을 해서 사용한다,

**GMT**
Greenwich Mean Time

![스크린샷 2020-01-30 오후 8.21.32.png](https://images.velog.io/post-images/carminchameleon/92a5d350-43c9-11ea-beda-1b627b9f2b39/-2020-01-30-8.21.32.png)

이 사진을 보면 GMT 라고 나오는 부분이 있는데 이것은 GMT를 기준으로 얼마나 시간이 빠른지를 표현해주는 것이다.

이렇게 new Date() 로 얻어온 값을 Date 객체가 가지고 있는 다른 함수로각 날짜, 시간 등의 값을 가져올 수 있다.

```js
let rightNow = new Date();
let year = rightNow.getFullYear();
let month = rightNow.getMonth() + 1;
let date = rightNow.getDate();
let day = rightNow.getDay();
let currentHour = rightNow.getHours();
let currentMin = rightNow.getMinutes();
```

각 값들을 콘솔로그에 쳐보면

```2020-01-31T01:39:41.071Z
2020
1
31
5
38
10
```

여기서 주의할 점은

1. getMonth() + 1
   만약, 지금이 1월이라면 getMonth() 자체의 값은 0이다.
   왜냐하면 첫번째 달이고 index 상으로는 첫번째는 0이기 때문이다.
   따라서 +1을 해주어야 한다.

우리는 이미 rightNow를 정의했기 때문에 이 값은 정의한 그 시간 자체를 가지고 있다. 즉, 매 초 시간마다 흐르는 시간을 담고 있는 것이 아니다.

**getTime**

```js
let rightNow = new Date();
let time = rightNow.getTime();
```

getTime 메소드는 날짜의 밀리 초를 반환한다.

위의 것을 실행해보면,
`1580435042650`
이러한 숫자가 반환되는데, 이것은 지금의 시간이 밀리초로 표현된 것이다.
이 밀리초의 기준이 되는 것은 1970년 1월 1일이다.
그래서 저 밀리초의 의미는 저 1970년 1월 1일부터 1580435042650 초가 지났다는 의미이다.

초는 계속 흐르기 때문에, 만약 지금 다시 저 함수를 실행해서 값을 받아보면 위의 값보다 더 큰 값이 나온다.

즉 현재의 값 > 과거의 값

**특정 날짜의 Date**
우리가 현재 시간을 받을 때 `new Date()`를 하였다. 이때 매개변수를 비워놓지 않고 특정한 날짜를 매개변수로 넣으면, 해당 날짜의 Date를 반환 받을 수 있습니다.

```js
let date1 = new Date('December 17, 2019 03:24:00');
let date2 = new Date('2019-12-17T03:24:00');
let date3 = new Date(2019, 5, 1);
//결과값
2019-12-16T18:24:00.000Z
2019-12-16T18:24:00.000Z
2019-05-31T15:00:00.000Z
```

#### Quiz

만나이 계산하기

```js
function getWesternAge(birthday) {
  let birthDay = new Date(birthday); // 생일 날의 Date 얻기
  let birthYear = birthDay.getFullYear();
  let birthMonth = birthDay.getMonth() + 1;
  let birthDate = birthDay.getDate();

  let birthMonthDate = birthMonth + "" + (birthDate + "");

  let today = new Date();
  let todayYear = today.getFullYear();
  let todayMonth = today.getMonth() + 1;
  let todayDate = today.getDate();

  let todayMonthDate = todayMonth + "" + (todayDate + "");

  if (Number(birthMonthDate) > Number(todayMonthDate)) {
    return todayYear - birthYear - 1;
  } else {
    return todayYear - birthYear;
  }
}
```
