# RESTful API

웹 서비스의 설계 방식 중 하나로, 네트워크 상에서 Client와 Server 사이의 통신 방식을 규정한 아키텍처 스타일입니다. 

REST는 Representational State Transfer의 약자로, <U>자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 모든 것</U>을 의미합니다. 

즉, 자원(resource)의 표현(representation)에 의한 상태 전달이다.

<br>

## REST

1. **REST란?**
  - `HTTP URI (Uniform Resource Identifier)` 를 통해 `자원 (Resource)` 을 명시합니다.
  - `HTTP Method (POST, GET, PUT, DELETE, PATCH)` 를 통해 해당 자원(URI)에 대한 `CRUD Operation` 을 적용하는 것을 의미합니다.

2. **REST 구성 요소**
  - **자원 (Resource)**: HTTP URI
  - **자원에 대한 행위 (Verb)**: HTTP Method
  - **자원에 대한 행위의 내용 (Representations)**: HTTP Message Payload

3. **REST의 특징**
  - **Server-Client 구조**
  - **무상태 (Stateless)**
  - **캐시 처리 가능 (Cacheable)**
  - **계층화 (Layered System)**
  - **인터페이스 일관성 (Uniform Interface)**

4. **REST의 장단점**
  - **장점**
    - HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구축할 필요가 없습니다.
    - HTTP 프로토콜의 표준을 최대한 활용하여 여러 추가적인 장점을 함께 가져갈 수 있습니다.
    - HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용 가능합니다.
    - Hypermedia API의 기본을 충실히 지키면서 범용성을 보장합니다.
    - REST API 메시지가 의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있습니다.
    - 여러 가지 서비스 디자인에서 생길 수 있는 문제를 최소화합니다.
    - 서버와 클라이언트의 역할을 명확하게 분리합니다.
  - **단점**
    - 표준이 존재하지 않아 정의가 필요합니다.
    - HTTP Method 형태가 제한적입니다.
    - 브라우저를 통해 테스트할 일이 많은 서비스라면 쉽게 고칠 수 있는 URL보다 Headers 정보의 값을 처리해야 하므로 전문성이 요구됩니다.
    - 구형 브라우저에서 호환이 되지 않아 지원하지 못하는 동작이 많습니다.

<br>

## REST API

1. **REST API란?**
  - REST의 원리를 따르는 API를 의미합니다.
  - 올바르게 설계하기 위해서는 지켜야 하는 몇 가지 규칙이 있습니다.

2. **REST API 설계 규칙**
  - **URI는 동사보다는 명사를, 대문자보다는 소문자를 사용하여야 합니다.**
    - **Bad Example** <U>https://api.ato-m-a.me/Ping</U>
    - **Good Example** <U>https://api.ato-m-a.me/ping</U>
  - **마지막에 슬래시 (/)를 포함하지 않습니다.**
    - **Bad Example** <U>https://api.ato-m-a.me/ping/</U>
    - **Good Example** <U>https://api.ato-m-a.me/ping</U>
  - **언더바 대신 하이픈을 사용합니다.**
    - **Bad Example** <U>https://api.ato-m-a.me/ping_check</U>
    - **Good Example** <U>https://api.ato-m-a.me/ping-check</U>
  - **파일 확장자는 URI에 포함하지 않습니다.**
    - **Bad Example** <U>https://api.ato-m-a.me/static/image.png</U>
    - **Good Example** <U>https://api.ato-m-a.me/static/image</U>
  - **행위를 포함하지 않습니다.**
    - **Bad Example** DELETE <U>https://api.ato-m-a.me/delete-image/1</U>
    - **Good Example** DELETE <U>https://api.ato-m-a.me/image/1</U>

<br>

## RESTful

REST의 원리를 따르는 시스템을 의미합니다. 하지만 REST를 사용했다 하여 모두가 RESTful한 것은 아닙니다.

REST API의 설계 규칙을 올바르게 지킨 시스템을 RESTful 하다 말할 수 있으며, 모든 CRUD 기능을 POST로 처리 하는 API
혹은 URI 규칙을 올바르게 지키지 않은 API는 REST API의 설계 규칙을 올바르게 지키지 않았기 때문에 RESTful 하지 못한 시스템이라고 할 수 있습니다.

<br>

## API (Application Programming Interface)

`API (Application Programming Interface)` 는 응용 프로그램에서 사용할 수 있도록, 운영 체제나 프로그래밍 언어가 제공하는 기능을
제어할 수 있게 만든 인터페이스를 뜻합니다.

소프트웨어에서 데이터를 주고 받기 위한 방법을 의미합니다. 특정 소프트웨어의 내부 구현을 모르더라도 어떠한 방식으로 정보를 요청해야 하는지,
그리고 어떠한 데이터를 응답받을 수 있는지에 대한 규격을 의미합니다.