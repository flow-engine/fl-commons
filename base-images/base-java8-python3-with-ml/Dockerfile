FROM docker.4pd.io/meteor/base-java8-python3:alpine-0.1
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories
#RUN apk add --no-cache gcc musl-dev libc-dev libc6-compat linux-headers libffi-dev openssl-dev llvm8-dev g++
RUN apk --no-cache add \
    build-base \
    python3 \
    python3-dev \
    python3-tkinter \
    # wget dependency
    openssl \
    # dev dependencies
    bash \
    git \
    meson \
    py3-pip \
    sudo \
    # Pillow dependencies
    freetype-dev \
    fribidi-dev \
    harfbuzz-dev \
    jpeg-dev \
    lcms2-dev \
    openjpeg-dev \
    tcl-dev \
    tiff-dev \
    tk-dev \
    zlib-dev
RUN apk --no-cache add --virtual .builddeps gcc gfortran musl-dev lapack libstdc++ g++ gcc lapack-dev libffi-dev libc-dev libc6-compat

RUN python3 -m ensurepip \
&& pip3 install --upgrade pip setuptools -i http://mirrors.aliyun.com/pypi/simple/ --trusted-host mirrors.aliyun.com  --user \
&& rm -r /usr/lib/python*/ensurepip && \
if [ ! -e /usr/bin/pip ]; then ln -s pip3 /usr/bin/pip ; fi && \
if [[ ! -e /usr/bin/python ]]; then ln -sf /usr/bin/python3 /usr/bin/python; fi && \
rm -r /root/.cache

RUN pip3 install -U   -i http://mirrors.aliyun.com/pypi/simple/ --trusted-host mirrors.aliyun.com  --user \
    Pillow==9.4.0

RUN pip3 install  -i http://mirrors.aliyun.com/pypi/simple/ --trusted-host mirrors.aliyun.com  --user \
    scikit-learn==1.0.2 \
    mlxtend==0.21.0

WORKDIR /app

CMD ["bash"]


#cycler==0.11.0
#fonttools==4.38.0
#joblib==1.2.0
#kiwisolver==1.4.4
#matplotlib==3.5.3
#meson==0.51.0
#mlxtend==0.21.0
#numpy==1.21.6
#packaging==23.0
#pandas==1.3.5
#Pillow==9.4.0
#pyparsing==3.0.9
#python-dateutil==2.8.2
#pytz==2022.7.1
#scikit-learn==1.0.2
#scipy==1.7.3
#six==1.16.0
#threadpoolctl==3.1.0
#typing_extensions==4.4.0
