### 전체 `README.md`
judy-community / spring, react


# Judy Community 프로젝트

Judy Community 프로젝트는 사용자들이 게시물과 댓글을 통해 상호작용할 수 있는 견고하고 확장 가능한 커뮤니티 플랫폼을 만드는 것을 목표로 하고 있습니다. 마이크로서비스 아키텍처를 채택하여 각 구성 요소가 독립적으로 확장 가능하고 유지 보수할 수 있도록 합니다.

## 프로젝트 구조

프로젝트는 백엔드 서비스와 프론트엔드 애플리케이션으로 나뉘며, 각각 플랫폼의 특정 측면에 중점을 둡니다.

```
judy-community/
├── backend-auth/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/
│   │   │   │       └── judycorp/
│   │   │   │           └── auth/
│   │   │   │               ├── config/
│   │   │   │               ├── controller/
│   │   │   │               ├── dto/
│   │   │   │               ├── entity/
│   │   │   │               ├── exception/
│   │   │   │               ├── repository/
│   │   │   │               ├── security/
│   │   │   │               ├── service/
│   │   │   │               └── ApplicationAuth.java
│   │   ├── resources/
│   │       └── application.properties
│   ├── Dockerfile
│   ├── build.gradle.kts
│   └── .github/
│       └── workflows/
│           └── ci-cd.yml
├── backend-user/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/
│   │   │   │       └── judycorp/
│   │   │   │           └── user/
│   │   │   │               ├── config/
│   │   │   │               ├── controller/
│   │   │   │               ├── dto/
│   │   │   │               ├── entity/
│   │   │   │               ├── exception/
│   │   │   │               ├── repository/
│   │   │   │               ├── service/
│   │   │   │               └── ApplicationUser.java
│   │   ├── resources/
│   │       └── application.properties
│   ├── Dockerfile
│   ├── build.gradle.kts
│   └── .github/
│       └── workflows/
│           └── ci-cd.yml
├── backend-post/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/
│   │   │   │       └── judycorp/
│   │   │   │           └── post/
│   │   │   │               ├── config/
│   │   │   │               ├── controller/
│   │   │   │               ├── dto/
│   │   │   │               ├── entity/
│   │   │   │               ├── exception/
│   │   │   │               ├── repository/
│   │   │   │               ├── service/
│   │   │   │               └── ApplicationPost.java
│   │   ├── resources/
│   │       └── application.properties
│   ├── Dockerfile
│   ├── build.gradle.kts
│   └── .github/
│       └── workflows/
│           └── ci-cd.yml
├── backend-comment/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/
│   │   │   │       └── judycorp/
│   │   │   │           └── comment/
│   │   │   │               ├── config/
│   │   │   │               ├── controller/
│   │   │   │               ├── dto/
│   │   │   │               ├── entity/
│   │   │   │               ├── exception/
│   │   │   │               ├── repository/
│   │   │   │               ├── service/
│   │   │   │               └── ApplicationComment.java
│   │   ├── resources/
│   │       └── application.properties
│   ├── Dockerfile
│   ├── build.gradle.kts
│   └── .github/
│       └── workflows/
│           └── ci-cd.yml
├── frontend-auth/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Login.js
│   │   │   ├── Register.js
│   │   │   ├── Logout.js
│   │   │   ├── RegisterDelete.js
│   │   ├── redux/
│   │   │   ├── authSlice.js
│   │   ├── services/
│   │   │   ├── api.js
│   │   ├── App.js
│   │   ├── index.js
│   │   ├── App.css
│   ├── Dockerfile
│   ├── package.json
│   └── .github/
│       └── workflows/
│           └── ci-cd.yml
├── frontend-user/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── UserDetail.js
│   │   │   ├── UserEdit.js
│   │   │   ├── UserDelete.js
│   │   ├── redux/
│   │   │   ├── userSlice.js
│   │   ├── services/
│   │   │   ├── api.js
│   │   ├── App.js
│   │   ├── index.js
│   │   ├── App.css
│   ├── Dockerfile
│   ├── package.json
│   └── .github/
│       └── workflows/
│           └── ci-cd.yml
├── frontend-post/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── PostList.js
│   │   │   ├── PostDetail.js
│   │   │   ├── PostCreate.js
│   │   │   ├── PostEdit.js
│   │   │   ├── PostDelete.js
│   │   ├── redux/
│   │   │   ├── postSlice.js
│   │   ├── services/
│   │   │   ├── api.js
│   │   ├── App.js
│   │   ├── index.js
│   │   ├── App.css
│   ├── Dockerfile
│   ├── package.json
│   └── .github/
│       └── workflows/
│           └── ci-cd.yml
├── frontend-comment/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── CommentList.js
│   │   │   ├── CommentCreate.js
│   │   │   ├── CommentEdit.js
│   │   │   ├── CommentDelete.js
│   │   ├── redux/
│   │   │   ├── commentSlice.js
│   │   ├── services/
│   │   │   ├── api.js
│   │   ├── App.js
│   │   ├── index.js
│   │   ├── App.css
│   ├── Dockerfile
│   ├── package.json
│   └── .github/
│       └── workflows/
│           └── ci-cd.yml
└── common-infrastructure/
    └── docker-compose.yml

```


### 백엔드 서비스

- **judy-community-backend-auth**: 사용자 인증 및 권한 관리를 담당합니다.
- **judy-community-backend-user**: 사용자 프로필 및 관련 작업을 관리합니다.
- **judy-community-backend-post**: 게시물 관리 및 관련 작업을 처리합니다.
- **judy-community-backend-comment**: 댓글 관리 및 관련 작업을 처리합니다.

### 프론트엔드 애플리케이션

- **judy-community-frontend-auth**: 사용자 인증을 위한 프론트엔드 애플리케이션입니다.
- **judy-community-frontend-user**: 사용자 프로필을 위한 프론트엔드 애플리케이션입니다.
- **judy-community-frontend-post**: 게시물 관리를 위한 프론트엔드 애플리케이션입니다.
- **judy-community-frontend-comment**: 댓글 관리를 위한 프론트엔드 애플리케이션입니다.

### 공통 인프라

- **judy-community-common-infrastructure**: 모든 서비스 및 애플리케이션을 관리하는 Docker Compose 설정이 포함되어 있습니다.

## 설치 방법

### 사전 요구 사항

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [JDK 17](https://adoptopenjdk.net/)
- [Node.js](https://nodejs.org/) (프론트엔드 애플리케이션용)

### 레포지토리 클론

각 레포지토리를 로컬 머신에 클론합니다:

```bash
git clone https://github.com/judy-community/backend-auth.git
git clone https://github.com/judy-community/backend-user.git
git clone https://github.com/judy-community/backend-post.git
git clone https://github.com/judy-community/backend-comment.git
git clone https://github.com/judy-community/frontend-auth.git
git clone https://github.com/judy-community/frontend-user.git
git clone https://github.com/judy-community/frontend-post.git
git clone https://github.com/judy-community/frontend-comment.git
git clone https://github.com/judy-community/common-infrastructure.git
```

### 공통 인프라 설정

`judy-community-common-infrastructure` 디렉토리로 이동하여 Docker Compose 설정을 시작합니다

```bash
cd judy-community-common-infrastructure
docker-compose up -d
```

이 명령은 MySQL 데이터베이스 및 다른 공유 서비스를 시작합니다.

## 서비스 실행

### 백엔드 서비스 실행

각 백엔드 서비스 디렉토리로 이동하여 Docker 이미지를 빌드합니다

```bash
cd judy-community-backend-auth
./gradlew build
docker build -t your_dockerhub_username/judy-community-backend-auth .
docker run -p 8081:8080 your_dockerhub_username/judy-community-backend-auth
```

다른 백엔드 서비스(`judy-community-backend-user`, `judy-community-backend-post`, `judy-community-backend-comment`)도 포트를 조정하여 위와 같은 방식으로 실행합니다.

### 프론트엔드 애플리케이션 실행

각 프론트엔드 애플리케이션 디렉토리로 이동하여 개발 서버를 시작합니다

```bash
cd judy-community-frontend-auth
npm install
npm start
```

다른 프론트엔드 애플리케이션(`judy-community-frontend-user`, `judy-community-frontend-post`, `judy-community-frontend-comment`)도 포트를 조정하여 위와 같은 방식으로 실행합니다.

## CI/CD 파이프라인

각 레포지토리는 GitHub Actions를 사용하여 CI/CD가 설정되어 있습니다. 워크플로우는 각 레포지토리의 `.github/workflows` 디렉토리에 정의되어 있습니다. 이 워크플로우에는 Docker 이미지를 빌드하고 테스트하며 Docker Hub에 배포하는 단계가 포함됩니다.

GitHub 레포지토리 설정에서 다음과 같은 시크릿을 구성해야 합니다

- `DOCKER_USERNAME`: Docker Hub 사용자명
- `DOCKER_PASSWORD`: Docker Hub 비밀번호

## 기여하기

커뮤니티의 기여를 환영합니다. 기여하려면 다음 단계를 따르세요

1. 기여하려는 레포지토리를 포크합니다.
2. 새 브랜치를 만듭니다 (`git checkout -b feature/YourFeature`).
3. 변경 사항을 커밋합니다 (`git commit -m 'Add YourFeature'`).
4. 브랜치에 푸시합니다 (`git push origin feature/YourFeature`).
5. 새 Pull Request를 만듭니다.
