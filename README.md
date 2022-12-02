# Service start
$> docker-compose -f cluster01.yml -p cluster01 up -d
$> docker-compose -f cluster02.yml -p cluster02 up -d
$> docker-compose -f logstash.yml -p logstash up -d

# Service stop
$> docker-compose -f cluster02.yml -p cluster02 down
$> docker-compose -f logstash.yml -p logstash down
$> docker-compose -f cluster01.yml -p cluster01 down