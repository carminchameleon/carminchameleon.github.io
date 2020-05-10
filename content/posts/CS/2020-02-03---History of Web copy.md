---
title: Web의 역사
date: "2020-02-03T22:40:32.169Z"
template: "post"
draft: false
slug: "HistoryOfWeb"
category: "Computer Science"
description: "웹의 시작부터 현재까지의 역사를 알아보자"
socialImage: ""
tags:
  - "WEB"
  - "DNS"
  - "Domain"
  - "Hosting"
  - "Computer Science"
---

우리가 주로 사용하는 웹. 이 웹은 어떤 원리로 구동되는 것일지에 대해서 생각해본 적이 있으신가요?
브라우저의 동작 원리에 대해서 알아봅시다.

#### 브라우저의 작동 원리

자, 우리가 넷플릭스에 접근한다고 생각해봅시다.

![image.png](https://images.velog.io/post-images/carminchameleon/b4bf4b00-48d9-11ea-848c-3324378610f0/image.png)

브라우저에 검색을 하겠죠?
https://www.netflix.com/kr/ 이렇게 혹은 netflix 이라고 칠 것입니다.
이렇게 보내는 형식이 바로 **url** 이죠.

![image.png](https://images.velog.io/post-images/carminchameleon/ac5ac910-48db-11ea-affd-73cfb79b431f/image.png)

브라우저에 url로 요청을 하면 서버에서는 그 화면에서 보여야 하는 콘텐츠들을 보내줍니다.
그때 필요한 파일들은 HTML,CSS, JavaScript, 들어가는 사진들 등 다양한 자료들이 있을 것입니다.

![image.png](https://images.velog.io/post-images/carminchameleon/25b1dd80-48dc-11ea-87aa-af2b3747a1e0/image.png)

#### Hosting

사용자들은 대한민국에 있든지 미국에 있든지 호주에 있든지 아니면 새벽이든지 아침이든지 저녁이든지
그 어느 곳 어느 시간에서든 요청을 할 수 있으며, 서버는 그 언제 어디서도 그에 대한 응답을 해주어야 합니다.
이러한 응답은 인터넷을 통해서 가능합니다.

그러면 서버란 무엇일까요?
서버는 하나의 컴퓨터라고 생각해도 됩니다.
하나의 컴퓨터에 브라우저에서 필요한 모든 구성 파일들이 ( HTML, CSS, JavaScript, img 등등) **항상** 연결되고 **절대** 꺼지지 않는 호스트 컴퓨터(웹 서버) 에 저장되어 있다가 사용자의 요청이 오면 언제든지 응답해야 합니다.

예전에는 이러한 서버를 구축하기 위해서 컴퓨터를 사서 24시간 전원과 인터넷이 항상 연결되게 했습니다. 그렇게 가지고 있는 물리적인 서버 (컴퓨터)가 항상 켜져있을 수 있도록 그것이 꺼지거나 고장이 났을때 관리할 수 있게 하는 서버 관리자들이 따로 있었습니다. 서버를 가지고 있는 물리적인 물건(컴퓨터)과 관리자가 있는 것이었죠.

사실 우리의 컴퓨터에도 서버는 구축할 수 있습니다. 그런데 그럴경우에 어떤 일이 발생할까요? 365일 어디서든 그 서버를 완벽하게 구축하고 있어야 하기 때문에 계속해서 컴퓨터를 켜 놓아야하고 인터넷 환경도 관리해야 합니다. 만약 회사나 기관에서 하고 있다면 그 서버의 범위가 커지니 그에 대한 인력도 많이 들겠네요.

그렇게 우리가 자체적으로 서버를 구축하지 않고도 서버를 쓸 수 있도록 해주는 서비스가 있습니다. 바로 **호스팅 서비스**이죠. 우리가 직접 서버를 만드는 대신 호스팅 서비스에서 가지고 있는 서버 중에서 일부 서버를 우리가 쓸 수 있을 정도로만 빌리는 것이죠.

호스팅 서비스를 제공하는 대표적인 것이 CAFE24, AWS 입니다.
![image.png](https://images.velog.io/post-images/carminchameleon/12774f50-48de-11ea-9b54-71928dd8b011/image.png)

![image.png](https://images.velog.io/post-images/carminchameleon/2032c840-48de-11ea-ab15-a1fea545fd23/image.png)

자, 다시한번 넷플릭스로 돌아갑시다.

우리가 넷플릭스에 접근을 하기 위해서 www.netflix.com 을 쳤습니다.
그런데 이렇게 쓴 내용을 가지고 어떻게 그 서버에 접근해서 그 정보를 가져올 수 있을까요?
서버는 우리의 요청을 듣고 어떻게 우리의 컴퓨터로 그 자료를 줄 수 있는 걸까요?

여기서 등장하는 것이 **IP, Domainm, DNS** 입니다.

#### IP

**IP주소란 인터넷에서 통신을 하기 위해 각각의 디바이스에 부여되는 고유한 주소**입니다.

![image.png](https://images.velog.io/post-images/carminchameleon/03f8df10-48df-11ea-98d8-cd230cbb4808/image.png)

우리가 가지고 있는 노트북, 테블릿, 핸드폰 등 그 모든 디바이스는 이 IP주소를 가지고 있습니다.
이 IP를 통해서 서버는 우리의 디바이스를 찾아내고 정보를 줄 수 있는 것입니다.

#### Domain

만약 우리가 넷플릭스에 가고 싶다고 한다면 여러개의 숫자로 이루어진 IP주소를 다 써야 할까요? 아닙니다.
**우리가 기억하고 검색하기 쉽도록 문자로 연결해주는 것이 도메인**입니다. 즉 문자(string)으로 되어 있는 고유 주소이죠.

**www.naver.com**  
**www.google.com**

이런식으로 검색만 해도 우리는 그 IP주소에 접근할 수 있는 것이죠. 우리가 집을 사고 거주를 하면 그 주소로 우편물을 주고 받는 것 처럼, 도메인 또한 그 도메인을 이용하기 위해서 돈을 주고 구매해야 합니다.

그렇다면, 이러한 도메인 주소를 통해서 우리는 IP주소와 연결될 수 있는데
도메인과 IP는 어떻게 연결되어 있는 걸까요?

![image.png](https://images.velog.io/post-images/carminchameleon/e9f911f0-48e0-11ea-a378-33f4514952be/image.png)

#### DNS(Domain Name System)

DNS는 우리가 읽을 수 있는 도메인 이름을 컴퓨터가 읽을 수 있는 IP 주소로 변환해줍니다. 마치 전화번호부 같은 기능을 하는 것이죠.

#### DNS server

DNS 서버란 도메인과 서버를 연결해주는 중간 서버로, 도메인 이름을 인터넷상의 주소(IP 주소)로 변환시켜 원하는 컴퓨터를 찾아갈 수 있도록 합니다.

![image.png](https://images.velog.io/post-images/carminchameleon/58014b30-48e2-11ea-a2d9-f500a37c4541/image.png)

정리를 하면서 해리포터에 나오는 텔레포트가 생각나네요. 통신과 컴퓨터로 이루어지는 이러한 과정이 마치 마법같다는 생각이 듭니다! 사람이나 물건을 이동시키는 텔레포트 기술은 현대 과학 기술로는 불가능하지만, 그 대신에 우리에게는 웹이 있네요!
