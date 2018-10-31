FROM debian:stretch-slim

MAINTAINER spencer@somanydoors.ca

RUN apt-get -qq update && \
	DEBIAN_FRONTEND=noninteractive \
	apt-get -qq install \
		mariadb-server

RUN sed -i 's/^\(bind-address\s.*\)/# \1/' /etc/mysql/my.cnf && \
	echo "mysqld_safe &" > /tmp/config && \
	echo "mysqladmin --silent --wait=30 ping || exit 1" >> /tmp/config && \
	echo "mysql -e 'GRANT ALL PRIVILEGES ON *.* TO \"root\"@\"localhost\" WITH GRANT OPTION;'" >> /tmp/config && \
	bash /tmp/config && \
	rm -f /tmp/config

VOLUME ["/etc/mysql","/var/lib/mysql"]

CMD ["mysqld_safe"]