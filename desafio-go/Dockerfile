FROM golang:alpine3.16 AS build 
WORKDIR /app
COPY ./app/ .
RUN CGO_ENABLED=0 GOARCH=386 GOOS=linux go build -a -installsuffix cgo -o main .

FROM scratch
WORKDIR /app
COPY --from=build /app/main .
CMD ["./main"] .