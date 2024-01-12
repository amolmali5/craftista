#build stage
FROM golang:1.20-alpine AS builder
RUN apk add --no-cache git
WORKDIR /app
COPY . .
RUN go build -o app 

#final stage
FROM alpine:latest
WORKDIR /app
RUN apk --no-cache add ca-certificates
COPY --from=builder /app /app

EXPOSE 8080
CMD [ "./app" ]