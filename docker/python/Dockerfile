# Last modified: Wed, 27 Feb 2019 09:44:36 +0000
FROM python:2.7.15-alpine3.9

COPY requirements.txt .

RUN apk --update add --no-cache --virtual .build-dependencies python-dev build-base wget \  
  && pip install --no-cache-dir -r requirements.txt \
  && apk del .build-dependencies

RUN addgroup -g 4000 demisto \
  && adduser -u 4000 -G demisto -D demisto -s /bin/sh 
