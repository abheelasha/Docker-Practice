FROM ubuntu:latest

WORKDIR /app

RUN apt-get update && apt-get install -y golang-go
#ECH "${go version}"

COPY . .

RUN go build calculator.go
CMD ./calculator


