FROM golang:1.18.1-alpine3.15 AS compiler

WORKDIR /usr/src/app

COPY ./fullcycle.go ./

RUN go mod init adrianpereira/fullcycle \
    && go build

FROM scratch

COPY --from=compiler /usr/src/app/fullcycle .

ENTRYPOINT [ "./fullcycle" ]
