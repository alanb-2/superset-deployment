FROM apache/superset:2.1.3

USER root

RUN apt update && \
    apt install --no-install-recommends -y firefox-esr wget

ENV GECKODRIVER_VERSION=0.33.0
ENV ARCHIVE_FILENAME=geckodriver-v${GECKODRIVER_VERSION}-linux64.tar.gz

RUN wget -q https://github.com/mozilla/geckodriver/releases/download/v${GECKODRIVER_VERSION}/${ARCHIVE_FILENAME} && \
    tar -xzf ${ARCHIVE_FILENAME} -O > /usr/bin/geckodriver && \
    chmod 755 /usr/bin/geckodriver && \
    rm ${ARCHIVE_FILENAME}

RUN python -m pip install --upgrade --proxy=http://127.0.0.1:3128 pip
RUN pip install --no-cache gevent psycopg2 redis

USER superset
