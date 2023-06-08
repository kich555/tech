---
transition: my-transition
---
# CSR

<div style='margin-top:24px'>Publishing</div>

<br>
<br>

```mermaid
flowchart LR
  github --> jenkins --> id1[(S3 Bucket)] --> CloudFront --> Browser
```

<br>
<br>

<!-- CSR 프로젝트의 배포는 비교적 간단하게 이루어 질 수 있습니다. 
컴퓨팅 리소스를 오로지 브라우저에서만 담당하기 때문에 serverless로도 충분히 프로젝트를 생성하고,
배포할 수 있습니다. 

또한 정적자산들이 CDN을 이용하기 때문에 global한 서비스에서도 장점을 발휘합니다.
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
