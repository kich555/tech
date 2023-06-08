---
transition: slide-up
---

# ISR
<br/>

```tsx {all|8-17|15|19-27|20|22-24|26} {maxHeight:'300px'}

function Blog({ posts }) {
  return (
    <ul>
      {posts.map((post) => (<li key={post.id}>{post.title}</li>))}
    </ul>
  );
}
 
export async function getStaticProps() {
  const res = await fetch('https://.../posts');
  const posts = await res.json()

  return {
    props: {posts}, 
    revalidate: 10
    };
}

export async function getStaticPaths() {
  const posts = await getPosts('https://.../posts').then(res=>res.json());

  const paths = posts.map((post) => ({
    params: { id: post.id },
  }));
 
  return { paths, fallback: 'blocking' };
}
 
export default Blog;

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

[코드설명]

1. 이 함수는 서버 측에서 빌드 시 호출됩니다.
재검증이 활성화되고 새 요청이 들어오면 서버리스 함수에서 다시 호출될 수 있습니다

2. revalidate 10초에 따라 해당 정적 html파일은 요청이 들어올 때, 혹은 요청이 들어오지 않아도,
최대 10초마다 한 번씩 새롭게 생성됩니다.

3. getStaticPaths 는 다이나믹 라우트 중에 정적으로 생성될 페이지를 결정합니다. 

4. posts 목록을 api로부터 불러온 후 

5. posts의 id만큼의 path parameter를 설정합니다. 

6. posts의 id 만큼의 정적파일을 미리 랜더링해둡니다. 이때 요청이 들어온 post.id가 서버에 존재하지 않는다면,
그 순간 정적 파일을 생성한 뒤 캐싱해둡니다. 

ISR은 SSG와 SSR의 장점을 혼합한 새로운 방식의 랜더링 프로세스인데요 

인터렉티브한 웹 페이지를 최대한 정적자산으로 만들어두어, cdn을 통해 빠르게 유저하게 제공하는 것과 정적 자산이더라도 최대한 fresh한 상태를 유지하고자 하는 
프론트 엔드 개발자들의 염원을 담고 있습니다. 

하지만 SSR보다 stale하고, SSG보다는 느릴 수 있다는, 자칫 잘못 사용하면 어중간한 포지션의 랜더링 방식이 될 수도 있습니다. 

 -->