FROM jenkins

ENV SOAPUI_VERSION 5.3.0
ENV SOAPUI_PATH /opt/soapui

USER root

RUN /bin/bash -c "set -o pipefail && \
    mkdir -p $SOAPUI_PATH && \
    curl -SL http://cdn01.downloads.smartbear.com/soapui/$SOAPUI_VERSION/SoapUI-$SOAPUI_VERSION-linux-bin.tar.gz | \
    tar -zxC $SOAPUI_PATH --strip-components=1"

FROM jenkins

RUN /usr/local/bin/install-plugins.sh \
      copyartifact \
      htmlpublisher \
      junit \
      xunit \
      mailer \
      ant \
      git 