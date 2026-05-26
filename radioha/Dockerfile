FROM node:18-alpine

RUN npm config set registry http://registry.npmjs.org/

# ffmpeg과 함께 HTTPS 접근을 위한 보안 인증서(ca-certificates) 설치
RUN apk add --no-cache ffmpeg ca-certificates

WORKDIR /app
COPY . /app/

RUN npm install --no-audit --no-fund --omit=dev

ENTRYPOINT [ "/bin/sh", "/app/run.sh" ]
