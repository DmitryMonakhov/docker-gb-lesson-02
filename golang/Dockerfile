##
## Build
##

FROM golang:1.16.7-alpine AS build

WORKDIR /app

COPY go.mod go.sum ./

RUN go mod download

COPY *.go .

RUN go build -o main .

##
## Deploy
##

FROM alpine:latest  

RUN apk --no-cache add ca-certificates

WORKDIR /app

COPY --from=build /app/main . 

EXPOSE 8080

ENTRYPOINT ["./main"]
