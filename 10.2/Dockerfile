FROM mariadb:10.2.28

COPY galera-entrypoint.sh / && \
     wsrep-notify.sh /usr/bin
     
RUN apt-get update && apt-get install -y galera-arbitrator-3 && \
    rm -rf /var/lib/apt/lists/* && chown mysql:mysql /usr/bin/wsrep-notify.sh && \
    chmod 700 /usr/bin/wsrep-notify.sh

EXPOSE 3306 4444 4567 4567/udp 4568

ENTRYPOINT ["/galera-entrypoint.sh"]
CMD ["mysqld"]
