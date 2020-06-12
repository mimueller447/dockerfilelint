# syntax = docker/dockerfile:1.0-experimental

FROM alpine:3.9

LABEL maintainer="Zabielski, Kamil <kamilzabielski@lintops.tech>"

ENV APPLICATION__NAME "beanstalk"
ENV APPLICATION__GID 3000
ENV APPLICATION__UID 3000
ENV APPLICATION__DIRECTORY "/var/lib/beanstalkd"

ENV APPLICATION__PORT 11300
ENV APPLICATION__FSYNC 0

WORKDIR "${APPLICATION__DIRECTORY}"
EXPOSE "${APPLICATION__PORT}"


RUN apk add --update --no-cache shadow beanstalkd

RUN usermod -d "${APPLICATION__DIRECTORY}" "${APPLICATION__NAME}"
RUN usermod -u "${APPLICATION__UID}" "${APPLICATION__NAME}"
RUN chown -Rv "${APPLICATION__NAME}" "${APPLICATION__DIRECTORY}"
RUN mkdir -pv "${APPLICATION__DIRECTORY}"


CMD "beanstalkd" "-p" "${APPLICATION__PORT}" "-V" "-u" "${APPLICATION__NAME}" "-f${APPLICATION__FSYNC}" "-b" "${APPLICATION__DIRECTORY}"