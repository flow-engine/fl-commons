FROM docker.4pd.io/meteor/base-image-common:1.0.0

RUN apk add --repository http://dl-cdn.alpinelinux.org/alpine/v3.10/main python3~=3.7 python3-dev py3-pip && ln -sf python3 /usr/bin/python

RUN pip3 install \
        requests==2.20.1 \
        future==0.17.1 \
        nose==1.3.7 \
        numpy==1.15.4
        
WORKDIR /app

CMD ["bash"]


