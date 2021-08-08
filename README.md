## RealCoding_Final

NCloud서버에서 도커 컨테이너를 통해 앱을 구동하는 모습

![증빙](https://user-images.githubusercontent.com/28242121/127746123-21cf69ad-7351-438f-b522-078049fc6937.png)



### Install

git clone Front and Server repository. That's all

```sh
git clone # your front repo addr
git clone # your Serve repo addr
```



### Tutorial

**Step 1.** npm install dependency

```sh
# ./term_project_front
npm install
# ./term_project_back
npm install
```



**Step 2.** Start server using docker

```sh
# ./term_project_back
docker build -t app . # 이미지 이름 app으로 설정
docker images # 이미지 존재 확인
docker run -p 3000:3000 app # docker container를 실행한다.
```



`DockerFile` 와 `.dockerignore`는 다음과 같이 작성되어있다.

```dockerfile
#DockerFile
FROM node:14 --> dockerhub에 있는 node 이미지 사용
WORKDIR /app --> 이미지 안에 애플리케이션 코드를 넣기위한 디렉터리 생성
COPY package*.json /app/ --> npm바이너리로 앱 의존성 설치
RUN npm install --> npm 설치
COPY . /app/ --> 도커 이미지 안에 앱의 소스코드를 넣기 위함
EXPOSE 3000 --> 3000번포트로 실행
CMD [ "node", "app.js"] --> 도커가 실행될 때 실행되는 명령어
```

```dockerfile
#.dockerignore
node_modules
npm-debug.log
```



**Step 3.** Start app

```sh
# ./term_project_front
node app.js
```



### Environment

- React : *write your version*
- Nodejs : *write your version*
- Firebase : *write your version*

![image](https://user-images.githubusercontent.com/31476895/127762999-4724ceee-ea73-4901-983b-794a8833507c.png)

