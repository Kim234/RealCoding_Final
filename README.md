# RealCoding_Final

## 도커 이용
![증빙](https://user-images.githubusercontent.com/28242121/127746123-21cf69ad-7351-438f-b522-078049fc6937.png)

다음과 같이 ncloud에서 만든 서버에서 도커 컨테이너를 통해 실행이 됨을 확인할 수 있다.

```sh
* 도커 이용 가이드
    1. Visual Studio 확장자를 이용해 Dockerfile과 .dockerignore 파일을 다음과 같이 만든다.
    - Dockerfile
    FROM node:14 --> dockerhub에 있는 node 이미지 사용
    WORKDIR /app --> 이미지 안에 애플리케이션 코드를 넣기위한 디렉터리 생성
    COPY package*.json /app/ --> npm바이너리로 앱 의존성 설치
    RUN npm install --> npm 설치
    COPY . /app/ --> 도커 이미지 안에 앱의 소스코드를 넣기 위함
    EXPOSE 3000 --> 3000번포트로 실행
    CMD [ "node", "app.js"] --> 도커가 실행될 때 실행되는 명령어
    
    - .dockerignore (도커 올릴 시, 무시하고 올리도록 만듬)
    node_modules
    npm-debug.log
    
    2. 다음과 같은 명령어로 container image를 도커로 빌드한다.
    - docker build -t app . (이미지 이름 app으로 설정)
    - docker images (이미지 존재 확인)
    
    3. 다음과 같은 명령어로 docker container를 실행한다.
    - docker run -p 3000:3000 app
    
    4. 위의 사진에서 볼 수 있듯이, 공인서버:3000에서 도커를 통해 서비스에 접속할 수 있다는 것을 확인할 수 있다.
```

## 주요 기술 
```sh
* Frontend
    - React 
* Backend
    - Node js 
* DB
    - Firestore
```


## Install

```sh
./term_project_front 폴더와 ./term_project_back 폴더에 들어간 후, 각각 다음과 같이 실행합니다.
npm install
```

## Usage 


```sh
./term9-backend 폴더에 들어간 후, 각각 다음과 같이 실행합니다.
node app.js
```

***
_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_

