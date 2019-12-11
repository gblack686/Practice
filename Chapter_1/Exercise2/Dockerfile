FROM golang:alpine AS builder
ADD . .
RUN go build *.go

FROM alpine
COPY --from=builder /go/function ./function
RUN chmod +x ./function
ENTRYPOINT ["./function"]
