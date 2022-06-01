FROM registry.access.redhat.com/ubi8/ubi:8.3


RUN  curl -O -L "https://github.com/grafana/loki/releases/download/v2.2.0/loki-linux-amd64.zip"  && \
  yum install -y unzip && \
 unzip  -d  /tmp/loki  "loki-linux-amd64.zip"  && \
  rm loki-linux-amd64.zip && \
 chmod a+x /tmp/loki/loki-linux-amd64 && \
yum -y clean all

 RUN useradd  loki && \
   mkdir /tmp/rules && \
   chgrp -R 0 /tmp/rules && \
   chmod -R g=u /tmp/rules

 USER loki


 ENTRYPOINT ["/tmp/loki/loki-linux-amd64"]

 CMD ["-config.file=/etc/loki/config/loki-config.yaml","-config.expand-env=true"]





