---
transition: my-transition
---
<div style='display:flex; align-items: center; justify-content: center; height: 100%'>
  <div id='title'>SSR</div>
</div>






<style>
#title { 
  font-weight: 700;
  font-size: 60px;
  line-height: none !important;
  background-color: #2B90B6;
  background-image: linear-gradient(52deg, #34dae7 3%, #0daeff 97%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
h1,h2 {
  line-height: none !important;
  background-color: #2B90B6;
  background-image: linear-gradient(52deg, #34dae7 3%, #0daeff 97%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

.my-transition-enter-active,
.my-transition-leave-active {
  transition: opacity 0.9s ease;
}

.my-transition-enter-from,
.my-transition-leave-to {
  opacity: 0;
}
</style>


<!-- 서버사이드 랜더링은 프론트엔드 개발자에게 더 많은 선택지를 제공해 줄 수 있습니다. 프록시, 미들웨어, 인증 서버, BFF 등 서버사이드 랜더링을 통해 
프론트 엔드 개발자는 보다 프론트 친화적인 환경을 구성하고, 운영할 수 있는데요.
저희 TW 광고플랫폼도 fully serverside rendering을 통해
다양한 문제들을 해결하고 있습니다.  -->