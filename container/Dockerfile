FROM openjdk:8

WORKDIR /
RUN mkdir mc
WORKDIR /mc
COPY . /mc

ENTRYPOINT ["sh", "/mc/run.sh"]
