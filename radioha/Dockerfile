FROM node:18-alpine

# 시놀로지 네트워크(IPv6) 무한 대기 방지
RUN npm config set registry http://registry.npmjs.org/

# 오디오 처리 프로그램 설치
RUN apk add --no-cache ffmpeg

WORKDIR /app
COPY . /app/

# 메모리 사용량을 최소화하여 패키지 설치
RUN npm install --no-audit --no-fund --omit=dev

ENTRYPOINT [ "/bin/sh", "/app/run.sh" ]
