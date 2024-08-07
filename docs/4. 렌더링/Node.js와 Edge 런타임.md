# Next.js에서 런타임의 의미

- 실행중에 코드에서 사용 가능한 라이브러리, API 및 일반 기능의 집합을 뜻함
- 서버에서는 코드의 일부를 렌더링 할 수 있는 2개의 런타임이 있음
  - Node.js(기본값)
  - Edge

<br/>

# 2개의 런타임의

- 어떤 런타임을 사용할지 정할때는 고려해야할게 많음

| 상황                     | Node.js | Serverless | Edge        |
| ------------------------ | ------- | ---------- | ----------- |
| 빠른시작                 | /       | 보통       | 느림        |
| HTTP 스트리밍            | 가능    | 가능       | 가능        |
| Input/Output             | 가능    | 가능       | fetch만     |
| 확장성                   | /       | 높음       | 매우높음    |
| 보안                     | 평균    | 높음       | 높음        |
| 지연율                   | 평균    | 느림       | 매우느림    |
| npm 패키지들             | 가능    | 가능       | 일부만 가능 |
| 정적 렌더링              | 가능    | 가능       | 불가능      |
| 동적 렌더링              | 가능    | 가능       | 가능        |
| fetch를 통한 데이터 갱신 | 가능    | 가능       | 가능        |

<br/>

# Edge 런타임

- Next.js에서 Edge 런타임은 경량화된 Node.js API의 하위 집합임
- 작고 간단한 기능으로 짧은 지연 시간으로 동적이고 개인화된 콘텐츠를 제공할때 좋음
- 리소스 사용을 최소화 하기때문에 속도는 빠르지만 기능이 한정적임
- vercel의 Edge 런타임에서 실행되는 코드는 1mb ~ 4mb만 지원함
- 해당 제한에는 패키지나 글꼴, 파일 등이 포함되고 배포하는 인프라에 따라 달라질수 있음
- 또한 모든 Node.js API를 지원하지 않으므로 일부 npm 패키지가 먹통될수도 있음

<br/>

# Node.js 런타임

- Node.js 런타임을 사용하면 모든 Node.js API와 npm 패키지 사용이 가능함
- 하지만 Edge에 비해서 속도는 느림
- 또한 Next.js를 Node.js에 배포할려면 인프라를 관리해줘야함
- 귀찮으면 Vercel 처럼 서버리스 플랫폼에 Next.js를 배포할 수도 있음

<br/>

# Serverless Node.js

- 서버리스는 Edge보다 더 복잡한 연산 부하를 처리해야할때 좋음
- Vercel Serverless의 경우 최대 50mb 까지 지원해줌
- 단점은 Edge에 비해서 빠른 시작이 불가능함
- 사이트가 처리하는 트래픽 양에 따라서 함수가 warmup이 안되기 때문에 자주 발생함

<br/>

# 예시

### 런타임 옵션

- 개별 라우터에 런타임 지정이 가능함
- `runtime` 변수를 선언하고 내보내면됨
- 변수는 문자열 이여야 하며 `nodejs` 또는 `edge` 값을 가져야함

```tsx
export const runtime = "edge"; // 'nodejs' (default) | 'edge'
```

또한 레이아웃 레벨에서도 사용이 가능함  
해당 레이아웃 하위에 있는 모든 부분에 동일한 런타임이 적용됨
