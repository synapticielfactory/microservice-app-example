FROM golang:1.9-alpine

EXPOSE 8081

WORKDIR /go/src/app
RUN apk --no-cache add curl git && \
    curl https://raw.githubusercontent.com/golang/dep/master/install.sh | sh

COPY . .

RUN dep ensure 
RUN dep ensure -update golang.org/x/sys

RUN go build -o auth-api

CMD /go/src/app/auth-api

