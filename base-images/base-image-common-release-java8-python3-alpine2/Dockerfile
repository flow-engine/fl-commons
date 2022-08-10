FROM docker.4pd.io/meteor/base-java8-python3:alpine-0.1
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories
#RUN apk add --no-cache gcc musl-dev libc-dev libc6-compat linux-headers libffi-dev openssl-dev llvm8-dev g++
RUN apk --no-cache add --virtual .builddeps gcc gfortran musl-dev lapack libstdc++ g++  lapack-dev libffi-dev libc-dev libc6-compat linux-headers openssl-dev

RUN python3 -m ensurepip \
&& pip3 install --upgrade pip setuptools -i http://mirrors.aliyun.com/pypi/simple/ --trusted-host mirrors.aliyun.com  --user \
&& rm -r /usr/lib/python*/ensurepip && \
if [ ! -e /usr/bin/pip ]; then ln -s pip3 /usr/bin/pip ; fi && \
if [[ ! -e /usr/bin/python ]]; then ln -sf /usr/bin/python3 /usr/bin/python; fi && \
rm -r /root/.cache

WORKDIR /app

CMD ["bash"]
