FROM python:3.7-alpine3.8

ENV PATH /root/.local/bin:"$PATH"

EXPOSE 8888

RUN set -ex \
	&& apk add --no-cache --virtual .build-deps  \
        g++ \
    && pip3 install --user cython \ 
        jupyter \
        nbconvert \
        bash

WORKDIR /notebook
COPY ./notebook .
# COPY ./docker-entrypoint.sh /docker-entrypoint.sh
# RUN chmod +x /docker-entrypoint.sh && sh /docker-entrypoint.sh

CMD [ "sh", "-c", "jupyter notebook --allow-root" ]
