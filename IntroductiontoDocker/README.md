# Introduction to Docker

Qwiklabs url: https://www.qwiklabs.com/focuses/1029?parent=catalog 

## Hello World

Cloud Shell을 열고 명령어를 입력하여 hello world 컨테이너를 시작하세요

```
docker run hello-world
```

(ouput)
```
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
1b930d010525: Pull complete
Digest: sha256:92c7f9c92844bbbb5d0a101b22f7c2a7949e40f8ea90c8b3bc396879d95e899a
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.
```

도커에서 컨테이너가 어떤 단계로 실행되는지 보여줍니다

## Build

Node.js 서버 프로그램를 실행하는 Docker 이미지를 만들어봅니다. <br>
``test`` 폴더에 소스가 있습니다. 

Dockerfile

```
# Node.js 이미지입니다 
FROM node:6

# 기본 디렉토리 경로를 /app 로 설정합니다
WORKDIR /app

# 로컬 컴퓨터에서 . 위치에 있는 파일을 도커 컨테이너의 /app으로 복사합니다
ADD . /app

# 컨테이너의 80번 포트를 엽니다
EXPOSE 80

# node로 app.js 파일을 실행시킵니다
CMD ["node", "app.js"]
```

## 도전과제 추천
1. C 파일 만들어서 도커에서 컴파일해서 실행하기
