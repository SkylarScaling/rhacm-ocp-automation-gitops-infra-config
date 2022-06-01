FROM registry.access.redhat.com/ubi8/ubi
RUN rpm --import https://packages.treasuredata.com/GPG-KEY-td-agent  
RUN dnf install -y  http://packages.treasuredata.com.s3.amazonaws.com/4/redhat/8/x86_64/td-agent-4.0.1-1.el8.x86_64.rpm 
RUN dnf install -y  gcc gcc-c++ make ruby*  
RUN   yum install -y td-agent  && /usr/sbin/td-agent-gem install fluentd -v 1.4.2  && \
 /usr/sbin/td-agent-gem install  fluent-plugin-concat   -v 2.3.0  && \ 
  /usr/sbin/td-agent-gem install  fluent-plugin-grok-parser   -v 2.5.1  && \
  /usr/sbin/td-agent-gem install  fluent-plugin-json-in-json-2   -v 1.0.2  && \
  /usr/sbin/td-agent-gem install  fluent-plugin-rewrite-tag-filter   -v 2.1.1  && \
  /usr/sbin/td-agent-gem install  fluent-plugin-systemd   -v 1.0.2  && \
 /usr/sbin/td-agent-gem install  fluent-plugin-kubernetes_metadata_filter  && \
 /usr/sbin/td-agent-gem install fluent-plugin-multi-format-parser  && \
 /usr/sbin/td-agent-gem install fluent-plugin-prometheus -v  1.3.0  && \
 /usr/sbin/td-agent-gem install fluent-plugin-grafana-loki-licence-fix 


#COPY fluent.conf /etc/fluent/fluent.conf

ENV FLUENT_UID=0
 RUN chmod 7777  /var/log/ && \
 chmod 777 /var/log/td-agent  
 
ENTRYPOINT /opt/td-agent/bin/fluentd

