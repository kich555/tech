---
transition: slide-up
---
# SSR

<div style='margin-top:24px'>Hydrate</div>
<br/>

```tsx {all|1|5|8-13}
let shouldHydrate: boolean = true; // 첫 렌더에서는 항상 true이다

function renderReactElement(domEl: HTMLElement, fn: (cb: () => void) => JSX.Element): void {
  //...
  const reactEl = fn(shouldHydrate ? markHydrateComplete : markRenderComplete);

  // ...
  if (shouldHydrate) {
    ReactDOM.hydrate(reactEl, domEl);
    shouldHydrate = false;
  } else {
    ReactDOM.render(reactEl, domEl);
  }
}
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

<!-- renderReactElement 함수는 Nextjs 내부 소스코드 중에서 최종적으로 요소 랜더링을 담당하는 함수입니다. 
보시는 것처럼 shouldHydrate 값을 통해 요소를 hydrate할지, render할지 결정합니다. 

  -->