# hostnamectl set-hostname rabbit-1
# docker network create rabbits
# docker run -d --rm --net rabbits --hostname rabbit-1 -p 8080:15672 --name rabbit-1 rabbitmq:3-management         
# docker exec -it rabbit-1 bash
# rabbitmq-plugins enable rabbitmq_management
# Goto Publisher Application and build the image
# docker build . -t page/rabbitmq-publisher:v1.0.0
# docker run -it --rm --net rabbits -e RABBIT_HOST=rabbit-1 -e RABBIT_PORT=5672 -e RABBIT_USERNAME=guest -e RABBIT_PASSWORD=guest -p 80:80 page/rabbitmq-publisher:v1.0.0
# Goto Consumer Application and build the image
# docker build . -t page/rabbitmq-consumer:v1.0.0
# RUN the Publisher Container 
