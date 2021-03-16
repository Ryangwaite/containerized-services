# tac_plus is unavailable on ubuntu 20.04
FROM ubuntu:18.04

# Install packages
RUN apt-get update && apt-get install -y \
    tacacs+ 

# Need to use tini so that tac_plus will terminate with ctrl-c
# This package isn't available on ubuntu18.04 though so install from
# source. Note can use "--init" to "docker run ..." to achieve same thing.
ENV TINI_VERSION v0.19.0
ADD https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini /tini
RUN chmod +x /tini
ENTRYPOINT ["/tini", "--", "/usr/sbin/tac_plus"]

CMD ["-G", "-g", "-C", "/etc/tacacs+/tac_plus.conf", "-d", "64"]