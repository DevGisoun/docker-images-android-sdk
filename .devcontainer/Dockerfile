# 베이스 이미지 : Alpine Linux 3.20
FROM mcr.microsoft.com/devcontainers/base:alpine-3.20

# 실행될 명령어를'root' 사용자로 실행.
USER root

# Alpine 패키지 저장소 업데이트 및 필요 패키지들 설치. (패키지 캐시 저장 X)
RUN apk update && apk add --no-cache \
    docker \
    git \
    curl \
    zip \
    unzip \
    lsb-release \
    ca-certificates \
    gnupg \
    sudo \
    util-linux-login \
    && rm -rf /var/cache/apk/*

# 'vscode' 그룹을 생성하고 'docker' 그룹에 추가.
# 이는 'vscode' 사용자가 docker 명령어를 사용할 수 있는 권한을 부여.
RUN addgroup vscode docker

# 'vscode' 사용자가 비밀번호 없이 sudo 명령을 실행할 수 있도록 sudoers 파일에 설정 추가.
# 이는 컨테이너 내부에서 특정 작업을 관리자 권한으로 수행해야 할 때 편리하게 사용할 수 있도록 하기 위함.
RUN echo "vscode ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

USER vscode