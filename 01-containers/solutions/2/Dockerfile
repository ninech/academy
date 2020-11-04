# build stage
FROM golang:alpine AS builder
COPY . /src
RUN cd /src && go build -o goapp

# final stage
FROM gcr.io/distroless/static
WORKDIR /app
COPY --from=builder /src/goapp .
CMD ["./goapp"]


# BUILD:    docker build --tag test1 .
# INSPECT:  docker images
# RUN:      docker run test1