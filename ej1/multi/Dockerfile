FROM debian:bookworm-slim as BUILD

RUN apt-get update \
	&& apt-get install -y wget make gcc \
	&& wget -O redis.tar.gz https://download.redis.io/releases/redis-7.2.4.tar.gz \
	&& mkdir redis \
	&& tar -xzf redis.tar.gz -C redis --strip-components=1	\
	&& make	-C redis \
	&& make	-C redis install

FROM XXX

ENV REDIS_DATA=/data
WORKDIR	$REDIS_DATA 
RUN XXX \
	&& XXX \
	&& chown redis:redis $REDIS_DATA
USER XXX
EXPOSE XXX
COPY XXX
ENTRYPOINT XXX
