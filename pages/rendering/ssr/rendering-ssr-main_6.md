---
transition: slide-left
---

# SSR
<div style='margin-top:24px'>Publishing</div>

<br>
<br>


```mermaid
flowchart LR
  github --> jenkins --> argoCD --> EKS --> Next_Server --> Browser
```

<br>
<br>

<!-- SSR의 배포 프로세스는 아래와 같습니다. 
서버가 존재하기 때문에 EKS를 활용하고 있으며 CSR보다는 보다 복잡한 프로세스를 가지고 있습니다.
 -->


<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(52deg, #34dae7 3%, #0daeff 97%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
#highlight {
  background-color: #2B90B6;
  background-image: linear-gradient(52deg, #34dae7 3%, #0daeff 97%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
strong {
  background-color: #2B90B6;
  background-image: linear-gradient(52deg, #34dae7 3%, #0daeff 97%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
li {
  margin-bottom: 12px
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
