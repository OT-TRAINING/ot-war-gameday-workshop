FROM golang:latest as builder
MAINTAINER OpsTree Solutions
COPY . /go/src/attendance
WORKDIR /go/src/attendance
RUN go get -v -t -d ./... \
    && go build -o attendance
ENV CONFIG_FILE "config.yaml"
EXPOSE 8081
ENTRYPOINT ["./attendance"]
