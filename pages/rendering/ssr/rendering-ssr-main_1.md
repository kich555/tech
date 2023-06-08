---
transition: slide-up
---
# SSR

<div style='margin-top:24px'>API Route</div>
<br/>

```tsx {all|8-10|12-14}
import type {NextApiRequest, NextApiResponse} from 'next';
import {getToken} from 'next-auth/jwt';
import httpProxyMiddleware from 'next-http-proxy-middleware';

export default async function handler(req: NextApiRequest, res: NextApiResponse) {
  const token = await getToken({req});
  req.url = req.url?.replace(/^\/api/, '');
  if (token?.apiAccessToken) {
    req.headers.authorization = `Bearer ${token.apiAccessToken}`;
  }

  httpProxyMiddleware(req, res, {
    target: `${process.env.NEXT_API_SERVER}`,
  });
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


<!-- API Route 는 대표적인 SSR 프레임워크인 NextJS에서 프록시 미들웨어로 사용할 수 있습니다. 

위 예시코드 처럼 기본적으로는 request header의 auth token을 클라이언트 사이드로부터 숨긴다던지, 자체적인 auth 서버를 구성한다던지, 좀 더 보안을 강화한 제품을 만들 용도로 주로 사용합니다.

혹은 또는 BFF로써 서버의 상태를 제가공하여 처리하는 간단한 was로의 구성도 가능합니다. -->