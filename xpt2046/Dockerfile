ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

RUN apk add --no-cache \
    git \
    cmake \
    make \
    g++ \
    linux-headers

RUN git clone https://github.com/tasanakorn/rpi-fbcp && \
    cd rpi-fbcp && \
    mkdir build && \
    cd build && \
    cmake .. && \
    make && \
    install fbcp /usr/local/bin/fbcp

COPY run.sh /run.sh
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
