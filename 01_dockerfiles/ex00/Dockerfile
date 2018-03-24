# before : docker build -t myvim .
# after  : docker run -it --rm myvim
FROM alpine:latest
RUN apk update
RUN apk upgrade
RUN apk add vim
RUN apk upgrade
ENTRYPOINT ["/usr/bin/vim"]
