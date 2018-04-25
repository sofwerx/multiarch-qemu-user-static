FROM ubuntu:18.04 as builder

RUN apt-get update
RUN apt-get install -y qemu-user-static curl jq file

ADD publish.sh /publish.sh

CMD /publish.sh
