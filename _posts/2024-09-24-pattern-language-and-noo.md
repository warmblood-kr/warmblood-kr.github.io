---
layout: post
title: "디자인 패턴, 패턴 언어, 질서의 본질"
date: 2024-09-
categories: dev-practice
author: jeongsoo.park
description: 
image: 
---

[기술부채]({{ site.baseurl }}{% link _posts/2024-09-23-technical-debt.md %})에 대해 썼던 지난 글에서 크리스토퍼 알렉산더와, 그가 주장한 패턴 언어(pattern languages)에 대해 말했습니다. 그리고 소프트웨어 업계 사람들이 패턴 언어를 적극적으로 받아들였고, 그 결과물 중에 디자인 패턴이 있다는 것도 이야기했습니다.

이 글에서는, 패턴 언어, 그리고 그걸 처음 제안한 크리스토퍼 알렉산더, 그리고 패턴 언어 이후에 발전한 연구 성과에 대해 소개하여, 알렉산더의 아이디어를 디자인 패턴을 넘어서서 보다 더 깊이있고 폭넓게 소프트웨어 개발에 적용하고자 하는 분들이 늘어나면 좋겠습니다.


## 디자인 패턴의 탄생과 패턴 커뮤니티

연대기적 순서대로 살펴보기보다는, 소프트웨어 개발자들이 익숙한, 디자인 패턴에서부터 시작해봅시다. 프로그래밍 분야에서 널리 알려진 '디자인 패턴'은, Gangs of Four라고 불리우기도 하는, Erich Gamma, Richard Helm, Ralph Johnson, John Vlissides 이렇게 네 명의 저자가 쓴 _Design Patterns: Elements of Reusable Object-Oriented Softward_ 라는 책에 정리된 23가지의 설계 패턴을 지칭한다고 볼 수 있습니다.

이 네 명의 저자는 어떤 배경으로 이 책을 쓰게 되었을까요? 이들은 어떻게 만나게 되었을까요?

이 GOF Design Pattern 책은 1995년에 출간되었습니다. 

https://c2.com/doc/oopsla87.html

https://wiki.c2.com/?HistoryOfPatterns

워드와 켄트가 OOPSLA 87에서 [패턴을 발표](https://c2.com/doc/oopsla87.html)함.

ErichGamma는 박사 논문으로 ET++에 대해서 쓰고 있었음. BruceAnderson은 TOOLS 90에서 강연을 했고, 거기에 ErichGamma가 참석해서 들었음. 그때 Bruce는 OOPSLA 90을 소개했고, 그 행사에서 BOF 소그룹 모임 하나를 진행했음. 그게 _Toward an Architecture Handbook_였음. 거기서 ErichGamma와 RichardHelm이 서로 처음 만나게 되었음. 나중에 OOPSLA 91에서 Ralph Johnson, JohnVlissides가 [합류](https://wiki.c2.com/?KentAndRalphAtTheArchitectureWorkshop)했음.

CA의 TWOB은 79년, PL은 77년에 출간되었음.

워드의 인터뷰, [The Starting Point of Software Patterns](https://www.youtube.com/watch?v=_V0kVOLOCrY)

[Hillside Group](https://hillside.net/home/history), PLoP

디자인 패턴은 설계 패턴임. 아키텍처 패턴, 구현 패턴, 리엔지니어링 패턴 등, 여러 종류, 여러 분야, 여러 층위의 패턴들이 있다. PLoP는 매년 열리고 있고, 지금도 패턴이 발굴되고 있다. 


## 패턴 언어, 크리스토퍼 알렉산더

디자인 패턴. 패턴 언어. 크리스토퍼 알렉산더.

디자인 패턴을 열심히 외우는 분들이 있는데, 디자인 패턴이 등장한 맥락과 역사를 보면, 디자인 패턴이 중요한 것이 아니다.

재미있는 것은, 워드 커닝햄이 여기도 등장한다는 것.

패턴 언어란. 영원의 건축. 패턴 언어. 이 사람의 화두는 무엇이었을까.

왜 그냥 '패턴'이라고 안하고 패턴 '언어'라고 했을까? 각 패턴 요소들의 조합이 단순 나열이 아니라 어떠한 의미 구조를 가지기 때문. 서로 관계가 있기 때문.

CA의 ACM OOPSLA 96 기조연설.




## 패턴 언어 그 이후, 질서의 본질에 대한 탐구.

그리고 The Nature of Order.

이 인터뷰 영상이 6분 정도로 짧은데 흥미롭다. 알렉산더가 패턴 랭귀지를 만들게 된 단초가 무엇이었는지, 또 Nature of Order는 왜 쓰게 되었는지에 대해 간략히 소개해준다.

[Jenny Quillen: History from A Pattern Language to the Nature of Order](https://www.youtube.com/watch?v=ad5XAPgKJoM)

미국 정부에서 연구용역을 발주했고, 그 연구를 알렉산더의 팀이 맡았다.

그 연구 주제는, '공간과 환경이 사람들의 행복과 정신건강에 미치는 영향'을 알아내려는 것이었다.

알렉산더의 팀은 그 연구를 맡을 때만 해도 그걸 어떻게 연구할지 전혀 아이디어가 없었다. 패턴언어는, 그 연구의 결과로 나온 것이다. 그 전에 그런 아이디어가 있었고 그 연구에 그 관점을 적용한 것이 아니다.

그렇게 패턴언어가 나왔다. 그런데 패턴언어가 세상에 나와서 사람들이 활용하는 것을 보고 알렉산더는 매우 실망했다. 사람들이 만들어내는 패턴언어 안에는 아름다움이 없고 뭔가 중요한게 빠져있는 것 같았다.

그래서 패턴언어와 Nature of Order 사이의 30년 동안, 알렉산더는 다시 처음으로 돌아가서, 패턴언어가 충분한 해답이 아니라면, 뭐가 해답일까를 처음부터 다시 생각했다.

패턴언어는 여러 레벨로 되어 있다. 각 패턴은 센터의 역할을 한다. 어느 패턴은 그 하위의 패턴들이 있다. 패턴들은 서로 연관을 가진다. 진짜 좋은 패턴 언어는 어떠한 meta-quality를 가지고 있다. Nature of Order는 이 meta qualities를 살펴보는 것으로 시작한다. 알렉산더는, 각 패턴들이 맺고 있는 그 연관, 이음새 부분을 주목하는 것에서 시작했다.
