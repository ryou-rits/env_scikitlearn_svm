FROM python:3.8-slim

RUN apt-get update && apt-get install -y \
    tzdata \
&& rm -rf /var/lib/apt/lists/*

WORKDIR /tmp/work
COPY riquirements.txt ${PWD}
RUN pip install -r requirements.txt

ENV TZ=ASIA/Tokyo
ENV USER user1

RUN useradd -m ${USER} --build 1000
RUN gpasswd -a ${USER} sudo
RUN echo "{USER}:password" | chpasswd

USER ${USER}