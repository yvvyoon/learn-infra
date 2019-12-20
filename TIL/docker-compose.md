## Docker Compose

`Compose`는 다중 컨테이너 애플리케이션을 구성하고 실행하는 도구이다. `yaml` 파일로 서비스들을 설정하고, `yaml` 파일을 통해 커맨드 단 한 줄로 모든 서비스들을 연결하여 구동할 수 있다. 뒤에서 `yaml` 파일의 코드를 보면 알겠지만 각 컨테이너의 구동 순서에 따라 종속성을 나타낸다.

Compose는 총 세 단계로 진행된다.

<br>

> 1. 어디서든 재사용이 가능한 `Dockerfile` 파일을 작성하여 애플리케이션의 환경을 설정한다.
> 2. 각 독립적인 컨테이너 환경에서 실행할 수 있도록 `docker-compose.yml`에 애플리케이션을 구성할 서비스들을 정의한다.
> 3. `docker-compose up` 커맨드 한 줄로 전체 애플리케이션을 실행한다.

<br>

docker-compose.yml 파일은 아래 코드와 같이 구성된다.

```yaml
version: '3'
services:
  web:
    build: .
    ports:
    - "5000:5000"
    volumes:
    - .:/code
    - logvolume01:/var/log
    links:
    - redis
  redis:
    image: redis
volumes:
  logvolume01: {}
```

<br>

### docker-compose.yml 작성

먼저 Docker Compose를 설치하자.

```
$ brew install docker-compose
```

<br>

프로젝트 루트 디렉토리에 docker-compose.yml 파일을 작성한다.

```yaml

```

