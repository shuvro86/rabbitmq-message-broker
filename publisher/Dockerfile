FROM golang:1.17-alpine as build

RUN apk add --no-cache git

WORKDIR /src
RUN go mod init golang
RUN go get github.com/julienschmidt/httprouter
RUN go get github.com/sirupsen/logrus
RUN go get github.com/streadway/amqp

COPY publisher.go /src

RUN go build publisher.go

FROM alpine as runtime

COPY --from=build /src/publisher /app/publisher

CMD [ "/app/publisher"]

