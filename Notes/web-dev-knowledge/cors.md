# CORS (Cross-Origin Resource Sharing)

교차 출처 리소스 공유 정책으로, 웹 애플리케이션은 리소스가 자신의 출처(도메인, 프로토콜, 포트)와 다른 출처의 리소스와 상호 작용할 수 있도록 허용하는 정책입니다.

<br>

## 출처

출처의 기준은 `{Protocol}{Host}{Port}` 를 합친 URL입니다.

<br>

## 필요한 이유

CORS가 없이 모든 출처의 데이터를 요청할 수 있고, 허용할 수 있게 되면 악의적인 사용자가 `CSRF` 나 `XSS` 등의 방법을 통해 개인 정보를 가로챌 수 있습니다.

<br>

## 구현 예시

1. **클라이언트에서 HTTP Headers에 'Origin' 을 담아 전달합니다.**
2. **서버는 응답 헤더에 'Access-Control-Allow-Origin' 을 담아 클라이언트로 전달합니다.**
3. **클라이언트에서 'Origin' 과 서버에서 보내준 'Access-Control-Allow-Origin' 을 비교합니다.**
  - `'Access-Control-Request-Method'` 헤더에 실제 요청에 사용할 메소드를 설정합니다.
  - `'Access-Control-Request-Headers'` 헤더에 실제 요청에 사용할 헤더를 설정합니다.
4. **유효하다면, 리소스를 사용합니다. 유효하지 않다면, 응답을 사용하지 않습니다.**

<br>

## 예비 요청 (Preflight)

1. **'Access-Control-Max-Age' 헤더에 예비 요청이 브라우저에 캐시될 수 있는 시간을 설정합니다.**
2. **HTTP 메소드를 `OPTIONS` 로 서버와의 통신을 확인합니다.**
3. **이후, 본 요청을 전송합니다.**

<Br>

## 동일 출처 정책 (Same-Origin Policy)

동일 출처 정책은 웹 애플리케이션의 보안을 위해 브라우저가 적용하는 정책입니다. 동일 출처 정책은 웹 애플리케이션의 리소스가 자신의 출처(도메인, 프로토콜, 포트)와 다른 출처의 리소스와 상호 작용할 수 없도록 제한합니다.