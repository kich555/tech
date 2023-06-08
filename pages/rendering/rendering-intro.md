---
transition: my-transition
---
<div style='display:flex; align-items: center; justify-content: center; height: 100%'>
<div id='title'>Rendering</div>
</div>
<!-- <div style='margin:24px 0; width: 60%'>트래블 월렛의 프론트앤드 챕터에서는 상황에 맞는 유연한 랜더링 방식을 선택하고, 관리해요</div> -->





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


<!-- 트래블월렛 프론트앤드 챕터에서는 현재 CSR/SSR 2가지 방식으로 
서비스를 만들고 있습니다.  

각각의 장단점이 있기 때문인데요. 

먼저 간략하게 CSR에 대해서 살펴보겠습니다.  -->