FROM ubuntu:16.04

RUN apt-get update && apt-get upgrade && apt-get install -y apt-transport-https ca-certificates curl software-properties-common
ADD assets build_assets
RUN cat build_assets/docker-apt-key.gpg | apt-key add - && cat build_assets/microsoft.gpg | apt-key add -
RUN add-apt-repository \
  "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) \
  stable" \
  && add-apt-repository \
  "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod \
  xenial \
  main"
RUN apt-get update && apt-get install -y docker-ce powershell