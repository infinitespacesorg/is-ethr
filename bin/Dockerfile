FROM ubuntu:oracular-20241120

RUN apt update && apt -y upgrade

COPY ethr-linux /usr/local/bin/ethr

CMD ["ethr -s"]
#CMD ["bash"]
ENTRYPOINT ["/bin/sh", "-c"]