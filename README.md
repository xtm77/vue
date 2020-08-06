# vue

## Vue 실행모드별 환경변수 설정
### 실행모드
> 기본실행모드는 development  
> 실행모드를 설정하여 로컬, 개발, 운영등 각 환경별로 환경변수를 설정할 수 있다.

#### 로컬모드 추가하기
> package.json 파일의 scripts에 "local": "vue-cli-service serve --mode local"을 추가한다.  
```
"scripts": {
    "local": "vue-cli-service serve --mode local",
    "serve": "vue-cli-service serve",
    "build": "vue-cli-service build",
    ...
  },
```

> 프로젝트 root 에 .env.local 파일 새로 생성(파일이 없을 경우) 한 후 아래 내용을 저장한다.  
```
NODE_ENV = "local"
BASE_URL = "/"
VUE_APP_API_V1_URL=http://localhost:18080/api/v1
VUE_APP_PORT = 8082
```

> 로컬 모드로 실행하기
```
npm run local
```

#### 사용자 정의 환경변수 추가하기
> 환경변수 파일(.env, .env.local, .env.development, .env.production)에 추가할수 있다.  
> VUE&#95;APP&#95; 접두어를 반드시 붙여야한다.

```
VUE_APP_PROT = 8088
VUE_APP_TEST_VARIABLE = "1234"
```

> .env 파일에 공통으로 사용하는 환경변수를 설정할 수 있다.  
> 같은 환경변수명이 실행모드별 환경변수 설정 파일(.env.local, .env.development, .env.production 등)에 있을 경우 .env에 있는 환경변수는 덮어쓰기가 되어 실행모드별 환경변수 값이 설정된다.  
