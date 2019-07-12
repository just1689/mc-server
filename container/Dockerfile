FROM adoptopenjdk/openjdk12:x86_64-debian-jre-12.0.1_12 as builder

WORKDIR /
COPY mc /mc

WORKDIR /mc
RUN ls -la

FROM builder as runner
COPY run.sh /mc

ENTRYPOINT ["sh", "/mc/run.sh"]
