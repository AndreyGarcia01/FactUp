FROM golang:1-alpine AS build

WORKDIR /source

COPY . .

RUN go build .

FROM alpine:3 AS run

WORKDIR /app

COPY --from=build /source/migrator .

RUN chmod +x ./migrator

CMD [ "./migrator" ]

