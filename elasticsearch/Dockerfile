# NAME: jie123108/elasticsearch-analysis-ik

FROM elasticsearch:6.6.2

MAINTAINER jie123108 'jie123108@163.com'

ENV VERSION=6.6.2

ADD "https://github.com/medcl/elasticsearch-analysis-ik/releases/download/v${VERSION}/elasticsearch-analysis-ik-$VERSION.zip" /tmp/
RUN /usr/share/elasticsearch/bin/elasticsearch-plugin install --batch file:///tmp/elasticsearch-analysis-ik-$VERSION.zip

RUN rm -rf /tmp/*
