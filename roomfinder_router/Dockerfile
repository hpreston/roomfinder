FROM python:2-alpine

# Add current folder as /app
ADD . /app
WORKDIR /app

# Install basic utilities
RUN export http_proxy=http://proxy-wsa.esl.cisco.com:80/ \
  && export https_proxy=http://proxy-wsa.esl.cisco.com:80/ \ 
  && apk add -U ca-certificates curl tzdata \
#        openssl-dev build-base heimdal-libs \
  && rm -rf /var/cache/apk/* \
  && pip install --no-cache-dir --requirement ./requirements.txt

#ENV http_proxy=http://proxy-wsa.esl.cisco.com:80
#ENV https_proxy=http://proxy-wsa.esl.cisco.com:80
#ENV no_proxy=192.168.7.222
CMD [ "./roomfinder_router/router.sh" ]
