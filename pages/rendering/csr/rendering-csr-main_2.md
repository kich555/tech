---
transition: slide-up
---
# CSR

<div style='margin-top:24px'>Client Side Rendering Process</div>


<span style='margin-top:24px'>main.tsx</span>

```ts {all|8-12}
import React from 'react';
import './styles/globals.css';
import './styles/reset.css';
import '@stackflow/plugin-basic-ui/index.css';
import ReactDOM from 'react-dom/client';
import App from './App';

ReactDOM.createRoot(document.getElementById('root') as HTMLElement).render(
  <React.StrictMode>
    <App />,
  </React.StrictMode>,
);
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
