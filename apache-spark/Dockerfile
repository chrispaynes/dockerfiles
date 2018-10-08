FROM java:8-alpine

ENV SPARK_PATH /usr/local/spark
RUN mkdir -p "$SPARK_PATH"
ENV PATH $PATH:"$SPARK_PATH"/bin

RUN set -x \
    && apk add --no-cache --virtual --update \
       bash \
       tar

RUN wget http://apache.cs.utah.edu/spark/spark-2.3.2/spark-2.3.2-bin-hadoop2.7.tgz -P /tmp \
    && tar -xzf /tmp/spark-2.3.2-bin-hadoop2.7.tgz --directory "$SPARK_PATH" --strip-components 1 \
    && rm /tmp/spark-2.3.2-bin-hadoop2.7.tgz

ENTRYPOINT [ "spark-shell" ]

