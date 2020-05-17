FROM golang:alpine as builder

WORKDIR /app

COPY rocks.go .
RUN go build rocks.go

RUN rm -f rocks.go

FROM scratch

COPY --from=builder ./app .

ENTRYPOINT [ "./rocks" ]