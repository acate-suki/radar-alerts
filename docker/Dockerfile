FROM golang:1.22-alpine

WORKDIR /app
COPY src/api/go.mod ./
RUN go mod download

COPY src/api ./
RUN go build -o /radar-api .

CMD ["/radar-api"]
