# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.222.0/containers/ubuntu/.devcontainer/base.Dockerfile

# [Choice] Ubuntu version (use hirsute or bionic on local arm64/Apple Silicon): hirsute, focal, bionic
ARG VARIANT="jammy"
FROM mcr.microsoft.com/vscode/devcontainers/base:${VARIANT}

##ENV HTTP_PROXY=http://10.16.31.215:7890
##ENV HTTPS_PROXY=http://10.16.31.215:7890


# [Optional] Uncomment this section to install additional OS packages.
RUN sudo sed -i "s@http://.*ports.ubuntu.com@https://mirrors.tuna.tsinghua.edu.cn@g" /etc/apt/sources.list
RUN sudo sed -i "s@http://.*ports.ubuntu.com@https://mirrors.tuna.tsinghua.edu.cn@g" /etc/apt/sources.list

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive 
RUN apt-get -y install --no-install-recommends texlive-full
RUN sudo wget -P /usr/share/fonts https://github.com/dolbydu/font/raw/master/unicode/FangSong.ttf https://github.com/dolbydu/font/raw/master/unicode/SimSun.ttc https://github.com/dolbydu/font/raw/master/unicode/SimHei.ttf https://github.com/dolbydu/font/raw/master/unicode/Kaiti.ttf  https://www.freebestfonts.com/yone//down/times.ttf
