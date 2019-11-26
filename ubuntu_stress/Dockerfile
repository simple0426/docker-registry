FROM ubuntu:xenial
COPY sources.list /etc/apt/sources.list 
RUN apt update && apt install -y stress
ENTRYPOINT ["/usr/bin/stress"]
CMD []
