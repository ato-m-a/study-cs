# 웹사이트 성능 메트릭

1. **LCP (Largest Contentful Paint)**
  - 가장 용량이 큰 컨텐츠가 표시되는 시점으로, 이 시기가 주요 컨텐츠가 로드되는 시기로 판단하는 것을 권장합니다.
  - 개선법
    - 느린 서버 응답 시간을 해결합니다. (서버 최적화, 가까운 CDN으로 라우팅, asset 캐싱...)
    - 렌더링을 `block` 하는 자바스크립트 및 CSS를 해결합니다.
      - CSS Minify, 중요하지 않은 CSS는 defer, 중요 CSS는 inline load...
    - 느린 리소스 (img, svg, video...) 로드 시간 해결
    - CSR의 경우, 사용하지 않는 자바스크립트 defer 로드, 사용하지 않는 polyfill 최소화 및 SSR 사용, pre-rendering

2. **FCP (First Contentful Paint)**
  - 페이지가 로드되기 시작하고 컨텐츠의 일부가 화면에 렌더링될 때 까지의 시간.
  - 개선법
    - 렌더링 blocking CSS, JS 최소화
    - 요청할 리소스에 preconnect
      ```HTML
      <link rel="preconnect">
      ```
    - 여러 페이지 리다이렉트 줄이기
    - 지나치게 큰 네트워크 payload 피하기, 서버 응답 시간(TTFB) 줄이기
    - 효율적인 캐시 정책으로 정적 리소스 제공 (가까운 CDN 서버 사용)
    - 과도한 DOM size 피하고, 중요한 요청의 depth를 최소화
    - 웹 폰트 로드 중에 텍스트가 계속 보이게 하기
    