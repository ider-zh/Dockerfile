FROM python:3.6-stretch

# install phantomjs
RUN mkdir -p /opt/phantomjs \
        && cd /opt/phantomjs \
        && wget -O phantomjs.tar.bz2 https://bitbucket.org/ariya/phantomjs/downloads/phantomjs-2.1.1-linux-x86_64.tar.bz2 \
        && tar xavf phantomjs.tar.bz2 --strip-components 1 \
        && ln -s /opt/phantomjs/bin/phantomjs /usr/local/bin/phantomjs \
        && rm phantomjs.tar.bz2

# install pyspider

WORKDIR /root
COPY requirements.txt requirements.txt
RUN pip install 'https://dev.mysql.com/get/Downloads/Connector-Python/mysql-connector-python-2.1.5.zip#md5=ce4a24cb1746c1c8f6189a97087f21c1' \
	&& pip install --no-cache-dir -r requirements.txt \
	&& pip install --no-cache-dir  pyspider

VOLUME ["/root"]
ENTRYPOINT ["pyspider"]

EXPOSE 5000 23333 24444 25555
