---
transition: slide-up
---
# SSG


<br/>

```tsx {all|8-13|15}
import type { InferGetStaticPropsType, GetStaticProps } from 'next';
 
type Repo = {
  name: string;
  stargazers_count: number;
};
 
export const getStaticProps: GetStaticProps<{
  repo: Repo;
}> = async () => {
  const repo = await getRepo();
  return { props: { repo } };
};
 
export default function Page({repo}: InferGetStaticPropsType<typeof getStaticProps>) {
  return repo.stargazers_count;
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

<!-- NextJS에서는 Static Site Generation을 통해 
빌드 시 정적인 페이지를 미리 만들어 둘 수도 있습니다. 

getStaticProps로 생성된 정적 상태를 기반으로 html 파일을 빌드단계에서 미리 생성하는 것인데요. 

별다른 비동기 로직이 필요없이 browser의 request와 동시에 이미 만들어준 html을 반환하는 것이기 때문에 가장 빠르게 page를 로드할 수 있습니다.

또한 CSR과는 다르게 빌드 시 라우터 별의 html을 모두 생성하기 때문에 SEO에서도 강점을 가집니다. 

하지만, 빌드 단계에서 정적으로 생성된 html이기 때문에, 빌드 이후의 변경된 상태에 대응하지 못하는 이슈가 있는데요.

그래서 보통 SEO에 민감하며, 상태의 변화가 별로 없는 정적 페이지에 많이 사용하곤 합니다.  -->