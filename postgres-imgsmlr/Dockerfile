FROM postgres:12

COPY sources.list /etc/apt/sources.list
RUN apt-get update && apt-get install --no-install-recommends -y wget unzip make gcc postgresql-server-dev-12 libgd-dev ca-certificates libc6-dev 
RUN wget https://github.com/postgrespro/imgsmlr/archive/master.zip -O /opt/imgsmlr.zip && \
    cd /opt && unzip imgsmlr.zip 
COPY sed_imgsmlr.sh /opt/imgsmlr-master/sed_imgsmlr.sh
RUN cd /opt/imgsmlr-master && sh sed_imgsmlr.sh
RUN cd /opt/imgsmlr-master && make USE_PGXS=1 && make install USE_PGXS=1 
RUN apt-get remove -y unzip make gcc postgresql-server-dev-12 
RUN	rm -rf /var/lib/apt/lists/*
