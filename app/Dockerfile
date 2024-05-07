FROM golang:1.19 AS builder
WORKDIR /go/src/hello
COPY . .
RUN CGO_ENABLED=0 go build -o /go/bin/hello

FROM gcr.io/distroless/static-debian11
COPY --from=builder /go/bin/hello /
CMD ["/hello"]