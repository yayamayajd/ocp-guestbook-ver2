FROM registry.access.redhat.com/ubi10/go-toolset:10.0 AS builder

WORKDIR /opt/app-root/src

ENV GOTOOLCHAIN=go1.25.5

COPY go.mod go.sum ./

RUN go mod download

COPY . .

RUN CGO_ENABLED=0 go build -o guestbook-api .




FROM registry.access.redhat.com/ubi10-minimal:10.0

WORKDIR /usr/local/bin

COPY --from=builder /opt/app-root/src/guestbook-api .

USER 1001

EXPOSE 8080

CMD ["/usr/local/bin/guestbook-api"]


