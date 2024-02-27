FROM golang:1.22-alpine AS build
WORKDIR /app
COPY . .
RUN go mod download
RUN go build -o /main

FROM alpine:3.19.1
COPY --from=build /main /main

ENTRYPOINT ["./main"]

