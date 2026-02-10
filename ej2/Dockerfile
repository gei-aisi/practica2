FROM XXX as builder

WORKDIR /tmp
ADD XXX redis.tar.gz
RUN apk add --no-cache build-base linux-headers openssl-dev \
	&& mkdir redis \
	&& tar -xzf XXX \
	&& make -C redis MALLOC=libc \
	&& make -C redis install

FROM XXX

ENV REDIS_DATA=/data
WORKDIR	$REDIS_DATA 
RUN apk add --no-cache libstdc++ \
	&& addgroup -S redis -g 990 \
	&& adduser -S redis -G redis -u 990 \
	&& chown redis:redis $REDIS_DATA
USER redis
EXPOSE 6379/tcp
COPY XXX
COPY XXX
ENTRYPOINT [XXX, "--protected-mode", "no", "--save", "5", "1"]
