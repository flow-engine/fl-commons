FROM docker.4pd.io/meteor/base-image-common:1.0.0

RUN apk add --no-cache openjdk8

ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk

RUN ln -s /usr/lib/jvm/java-1.8-openjdk/bin/javac /usr/bin/javac

COPY --from=hengyunabc/arthas:latest /opt/arthas /opt/arthas

WORKDIR /app

CMD ["bash"]
