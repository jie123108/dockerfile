FROM postgres:10.7

ADD sources.list /etc/apt/
# zombodb, pipelinedb
RUN export http_proxy=${PROXY}; export https_proxy=${PROXY} && apt-get update && \
apt-get install -y apt-utils libcurl3 wget curl vim && \
wget https://www.zombodb.com/releases/v10-1.0.3/zombodb_jessie_pg10-10-1.0.3_amd64.deb && \
dpkg -i zombodb_jessie_pg10-10-1.0.3_amd64.deb && \
curl -s http://download.pipelinedb.com/apt.sh | bash && \
apt-get install pipelinedb-postgresql-10

# postgis
RUN sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt xenial-pgdg main" >> /etc/apt/sources.list' && \
wget --quiet -O - http://apt.postgresql.org/pub/repos/apt/ACCC4CF8.asc | apt-key add - && \
apt-get update && \
apt-get install -y postgresql-10-postgis-2.4 postgis
