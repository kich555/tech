---
transition: slide-up
---
# CSR

<div style='margin-top:24px'>Client Side Rendering Process</div>


<span style='margin-top:24px'>main.tsx</span>

```tsx {all|1|3-9|6|5,7}
const BenefitTabScreen = React.lazy(() => import('~components/Benefit/AppScreen/BenefitTabScreen'));

const AsyncBenefitTabScreen: ActivityComponentType<BenefitParams> = ({params}) => {
  return (
    <React.Suspense fallback={<GlobalLoader />}>
      <BenefitTabScreen benefit={params.benefit} />
    </React.Suspense>
  );
};
```


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
</style>


<!-- React.Suspense는 어떤 컴포넌트가 읽어야 하는 데이터가 아직 준비가 되지 않았다고 리액트에게 알려주며, 
해당 컴포넌트 준비가 완료될 때까지 Fallback prop의 컴포넌트를 랜더링합니다. 
이런 다양한 기법으로 초기 번들 사이즈를 줄여 CSR의 단점 중 하나인 LCP (Largest Contentful Paint) 시간을 단축시킵니다. 
 -->