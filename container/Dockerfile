FROM openjdk:8 as builder

WORKDIR /
COPY mc /mc

WORKDIR /mc
RUN ls -la

FROM builder as runner
COPY run.sh /mc

ENTRYPOINT ["sh", "/mc/run.sh"]
