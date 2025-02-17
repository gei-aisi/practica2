FROM XXX as builder

WORKDIR /tmp
ADD XXX redis.tar.gz
RUN apt-get update \
	&& mkdir redis \
	&& tar XXX \
	&& apt-get install -y XXX \
	&& make	-C redis \
	&& make	-C redis install

FROM XXX

ENV REDIS_DATA=/data
WORKDIR	$REDIS_DATA 
RUN addgroup XXX \
	&& adduser XXX \
	&& chown redis:redis $REDIS_DATA
USER XXX
EXPOSE XXX
COPY XXX
COPY XXX
ENTRYPOINT [XXX]
