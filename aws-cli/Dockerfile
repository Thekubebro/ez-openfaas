FROM python:2.7.14-alpine3.7
ADD https://github.com/openfaas/faas/releases/download/0.7.0/fwatchdog /usr/bin
RUN chmod +x /usr/bin/fwatchdog
RUN pip install awscli --upgrade --user
RUN apk add --no-cache less groff
ENV PATH=$PATH:/root/.local/bin/
ENV fprocess="xargs aws"
HEALTHCHECK --interval=5s CMD [ -e /tmp/.lock ] || exit 1
CMD ["fwatchdog"]
