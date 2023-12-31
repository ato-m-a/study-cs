# 모노레포 (Monorepo)

단일 저장소를 의미하며, 여러 프로젝트의 코드가 하나의 버전 제어 저장소에 함께 저장되는 방식을 말합니다.

이러한 방식은 대규모 코드베이스와 여러 서브 프로젝트를 가진 조직에서 주로 사용됩니다.

<br>

## 특징

1. **코드 재사용**
  - 여러 프로젝트가 같은 저장소에 있기 때문에, 코드 재사용이 용이합니다.
  - 예를 들어, 한 프로젝트에서 개발된 공통 모듈을 다른 프로젝트에서 쉽게 참조할 수 있습니다.

2. **단순화된 의존성 관리**
  - 프로젝트 간 공유되는 라이브러리가 동일한 저장소에 있기 때문에, 버전 충돌 같은 문제를 방지하고 의존성을 쉽게 관리할 수 있습니다.
  - 전체 코드베이스에서 라이브러리 업데이트를 한 번에 진행할 수 있으므로, 개별 프로젝트에서 일일히 진행할 필요가 없습니다.

3. **통합 개발 및 테스트**
  - 전체 저장소에 대한 빌드, 테스트 및 배포 프로세스를 표준화하고 자동화하기 쉽습니다.
  - 이는 프로젝트 간 일관성을 유지하고, 변경 사항이 다른 프로젝트에 미치는 영향을 빠르게 확인할 수 있도록 도와줍니다.

4. **대규모 협업 지원**
  - 대규모 팀과 프로젝트에서의 협업을 용이하게 합니다.
  - 모든 코드가 한 곳에 있기 때문에 다양한 팀이 서로의 작업을 쉽게 참조하고, 공유된 표준 및 도구를 사용하여 일관된 개발 방식을 유지할 수 있습니다.

<br>

## 도전 과제

- **저장소의 크기**
  - 저장소의 크기가 커질수록, 코드베이스를 관리하는 것이 더 복잡해질 수 있습니다.
  - 소스 코드 검색, 지속적 통합(CI), 빌드 시간, 코드 리뷰 프로세스 등에 영향을 미칠 수 있습니다.

- **접근 제어 및 보안 정책 구현의 복잡성**
  - 저장소에 여러 프로젝트가 있기 때문에, 프로젝트 간의 접근 제어 및 보안 정책을 구현하는 것이 어려울 수 있습니다.
  - 예를 들어, 특정 프로젝트에 대한 접근 권한을 부여하거나, 특정 프로젝트의 코드를 외부에 공개하지 않는 등의 작업이 어려울 수 있습니다.

- **대규모 변경에 대한 충돌 해결**
  - 여러 프로젝트가 하나의 저장소에 있기 때문에, 대규모 변경이 발생할 경우 충돌이 발생할 수 있습니다.
  - 예를 들어, 여러 프로젝트에서 동일한 라이브러리를 사용하고 있을 경우, 해당 라이브러리의 변경이 여러 프로젝트에 영향을 미칠 수 있습니다.