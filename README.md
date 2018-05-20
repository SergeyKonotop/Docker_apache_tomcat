# Docker_apache_tomcat

## Run Apache docker container
    docker build -t "apache_image:1.0" .
    docker run -d --name apache -p 8085:8080 apache_image:1.0
    navigate in browser to localhost:8085

## Run Tomcat docker container
    docker build -t "centom:1.0" .
    docker run -d --name centom -p 8081:8080 centom:1.0 ./catalina.sh run
    navigate in browser to localhost:8081