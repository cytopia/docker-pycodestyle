FROM alpine:3.16 as builder

RUN set -x \
	&& apk add --no-cache \
		gcc \
		libffi-dev \
		make \
		musl-dev \
		openssl-dev \
		py3-pip \
		python3 \
		python3-dev

ARG VERSION=latest
RUN set -x \
	&& if [ "${VERSION}" = "latest" ]; then \
		pip3 install --no-cache-dir --no-compile pycodestyle; \
	elif [ "${VERSION}" -lt "2" ]; then \
		pip3 install --no-cache-dir --no-compile pycodestyle~=${VERSION}.0b; \
	else \
		pip3 install --no-cache-dir --no-compile pycodestyle~=${VERSION}.0; \
	fi \
	&& find /usr/lib/ -name '__pycache__' -print0 | xargs -0 -n1 rm -rf \
	&& find /usr/lib/ -name '*.pyc' -print0 | xargs -0 -n1 rm -rf


FROM alpine:3.16 as production
LABEL \
	maintainer="cytopia <cytopia@everythingcli.org>" \
	repo="https://github.com/cytopia/docker-pycodestyle"
RUN set -x \
	&& apk add --no-cache \
		python3 \
	&& ln -sf /usr/bin/python3 /usr/bin/python \
	&& find /usr/lib/ -name '__pycache__' -print0 | xargs -0 -n1 rm -rf \
	&& find /usr/lib/ -name '*.pyc' -print0 | xargs -0 -n1 rm -rf

COPY --from=builder /usr/lib/python3.10/site-packages/ /usr/lib/python3.10/site-packages/
COPY --from=builder /usr/bin/pycodestyle /usr/bin/pycodestyle

WORKDIR /data
ENTRYPOINT ["pycodestyle"]
CMD ["--version"]
