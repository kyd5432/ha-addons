FROM ubuntu:24.04

# 빌드 중 대화형 창이 뜨며 무한 대기에 빠지는 현상 방지
ENV DEBIAN_FRONTEND=noninteractive

# 외부 다운로드 주소 대신 Ubuntu 공식 저장소에서 안정적으로 설치
RUN apt-get update -y && \
    apt-get install -y nodejs npm ffmpeg curl && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# 앱 작동을 위한 기존 설정 유지
WORKDIR /app
COPY index.js /app/
COPY package.json /app/
COPY radio-list.json /app/
COPY run.sh /app/

# 실행 권한 부여 및 노드 패키지 설치
RUN chmod a+x /app/run.sh
RUN npm install

ENTRYPOINT [ "/app/run.sh" ]
