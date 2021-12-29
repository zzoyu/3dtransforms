---

title: 소개
layout: doc
is_homepage: true
slug: intro
redirect_from:
  - "/docs/introduction"

---

CSS 변형의 소개로, 엘레먼트는 이동하고, 회전하고, 기울어지고, 찌그러지거나 늘어날 수 있게 되었습니다. 웹 디자이너는 드디어 인쇄 디자이너들을 따라잡을 수 있게 된 것입니다. CSS 3D 변형과 함께라면, 웹디자이너는 인쇄물을 넘어 그래픽 디자인의 새로운 영역으로 탐험할 수 있습니다.

3D 그래픽을 웹 상에서 렌더링 하는 것은 꽤 오래 전부터 있었습니다. 먼저 플래시가 있었죠. 그리고 `<canvas>`와 WebGL로 [Three.js](https://threejs.org/)가 나타났습니다. WebVR과 증강현실은 바로 눈앞에 다가왔습니다. 이런 솔루션들이 돌아다닐 수 있는 3D 환경을 생성하는 것에 탁월하지만, 웹의 메인 요소인 인터페이스에는 과잉일 수 있습니다. CSS 3D 변형과 함께, 프론트엔드 개발자들은 전통적인 웹 사이트에 한 차원을 추가하는 것으로 기존의 디자인을 향상시킬 수 있습니다.

## Rationale

우리가 삼차원으로 뛰어들기 전에, 우리는 유저들에게 이 기능이 주는 이점이 있는지 물어볼 필요가 있습니다.

솔직해지자구요. CSS는 문서를 꾸미기 위해 만들어졌습니다. 그 이후에 애플리케이션을 다루기 위해 성장하였습니다. 하지만 아놔, CSS는 3D 모델링을 위한 개념이 아닙니다. 대신 3D 변형은 미디어 쿼리, 그라디언트, 트랜지션과 같은 그냥 여타 최신 기능들처럼 **애드온**으로써 다뤄져야 합니다. 웹사이트를 위한 3D는 인터페이스에 추가될 때 가장 효과를 발휘하지, 대체해서는 안 됩니다. 인터페이스 _중간중간에_ 트랜지션을 거치며 3D 변형을 사용할 기회가 충분히 많이 있습니다.

예전 iOS의 날씨 앱을 예로 들어봅시다. 이 앱은 두 화면을 사용하였습니다: 세부 내용 화면과 옵션 설정 화면이요. 두 화면을 전환하는 것은 3D 뒤집기 트랜지션을 통해 이루어집니다. 이는 유저에게 인터페이스가 패널의 한쪽 면에 하나씩, 단 두개의 화면만 제공한다는 것을 알립니다.

![아이폰 날씨 앱의 3D 뒤집기 전환](../img/weather-app-transition.jpg)

또한 캐러셀(carousel) 순환 플러그인도 생각해봅시다. 슬라이드가 되풀이되는 것을 어떻게 전달할 수 있을까요? With 3D, slides are placed side by side one another in a circle in 3D space. In that arrangement, the cyclic pattern of the carousel is self-evident.

3D transforms can be more than just eye candy. We can use them to solve actual interface challenges and make our applications more intuitive.

## Current Support Environment

[The CSS 3D transforms module](https://www.w3.org/TR/css-transforms-1/) was first [introduced in 2009](https://www.w3.org/TR/2009/WD-css3-3d-transforms-20090320/). It was authored by members at Apple and was first supported by Safari. Since then, all modern browsers including Chrome, Firefox, Internet Explorer and Edge have added support. View the chart on [caniuse.com/#feat=transforms3d](https://caniuse.com/#feat=transforms3d) to check the latest support environment across the browser landscape.

As of 2018, un-prefixed `transform` CSS properties are supported by 98% of browsers in use. Adding `-webkit-transform` will capture older browsers to get to 99%.

There is one caveat. [Internet Explorer 11 does not support `transform-style: preserve-3d`](http://msdn.microsoft.com/en-us/library/ie/hh673529%28v=vs.85%29.aspx#the_ms_transform_style_property) (we'll cover this property later). This means IE11 can still use 3D transforms with individual elements, but cannot handle nested elements to build the objects covered in this essay.

Let's get coding.

* * *

[**Next: Perspective &rarr;**](perspective)
