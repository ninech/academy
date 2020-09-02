# build stage
FROM golang:alpine AS builder
ADD . /src/
RUN cd /src && go build -o goapp

# final stage
FROM gcr.io/distroless/static
WORKDIR /app
COPY --from=builder /src/goapp /app/
ENTRYPOINT ["/goapp"]


# BUILD:    docker build --tag test:1.0 .
# INSPECT:  docker images
# RUN:      docker run -p 80:80 test:1.0