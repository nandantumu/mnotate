FROM openjdk:8-jre-buster

COPY . /janusgraph

WORKDIR /janusgraph

EXPOSE 8182

RUN wget https://raw.githubusercontent.com/vishnubob/wait-for-it/master/wait-for-it.sh

RUN chmod +x ./wait-for-it.sh

CMD ./wait-for-it.sh elasticsearch:9200 -- ./wait-for-it.sh cassandra:9042 -- sleep 45 && ./bin/gremlin-server.sh conf/gremlin-server/gremlin-server-cql-es.yaml