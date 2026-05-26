FROM node:18-alpine

# 오디오 처리를 위한 ffmpeg 초고속 설치
RUN apk add --no-cache ffmpeg

WORKDIR /app
COPY index.js /app/
COPY package.json /app/
COPY radio-list.json /app/
COPY run.sh /app/

RUN chmod a+x /app/run.sh
RUN npm install

ENTRYPOINT [ "/app/run.sh" ]
