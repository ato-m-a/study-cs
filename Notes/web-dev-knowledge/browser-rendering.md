# 브라우저 렌더링 과정

1. **불러오기**
  - 로더가 서버로부터 전달받은 리소스 스트림을 읽습니다.

2. **DOM, CSSOM 생성 (Parsing)**
  - `HTML/XML` 파서가 문서를 파싱해 `DOM Tree` 를 형성합니다.
  - `CSS` 파서가 스타일 정보를 파싱해 `CSSOM Tree` 를 형성합니다.

3. **DOM, CSSOM으로 렌더링 트리 생성 (Style)**
  - `DOM Tree` 와 `CSSOM Tree` 를 결합해 `렌더링 트리` 를 형성합니다.

4. **렌더링 트리에서 각 노드의 위치와 크기를 계산 (Layout)**
  - `렌더링 트리` 의 각 노드의 위치와 크기를 계산합니다.

5. **계산된 값을 이용해 각 노드를 화면상의 실제 픽셀로 변환하고 레이어를 만듭니다. (Paint)**
  - `렌더링 트리` 의 각 노드를 화면상의 실제 픽셀로 변환하고, 레이어를 만듭니다.

6. **레이어를 합성해 실제 화면에 나타냅니다. (Composition)**
  - 레이어를 화면에 그립니다.