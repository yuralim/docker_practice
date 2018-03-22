# docker build -t 10.1.28.199:5000/cub/cub-elasticsearch-db:2.4.1_local .
# docmer run -p 9200:9200 -p 9300:9300 --name cub-elasticsearch-db --env CLUSTER_NAME=elasticsearch --env PUBLISH_HOST=127.0.0.1 -d 10.1.28.199:5000/cub/cub-elasticsearch-db:2.4.1_local

FROM elasticsearch:2.4.1

CMD ["elasticsearch", "-Dcluster.name=${CLUSTER_NAME}", "-Dhttp.enabled=true", "-Dscript.engine.groovy.inline.mapping=true", "-Dscript.engine.groovy.inline.aggs=true", "-Dscript.engine.groovy.inline.search=true", "-Dscript.engine.groovy.inline.update=true", "-Dscript.engine.groovy.inline.plugin=true", "-Dindex.mapping.nested_fields.limit=1000", "-Dindex.max_result_window=2147483647", "-Dnetwork.publish_host=${PUBLISH_HOST}"]