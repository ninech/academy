FROM python:3-slim AS build-env
ADD . /app
WORKDIR /app



FROM gcr.io/distroless/python3
COPY --from=build-env /app /app
WORKDIR /app
CMD ["hello.py", "/etc"]

# BUILD:    docker build --tag test:1.0 .

# RUN:      docker run -p 80:80 test:1.0

# TAG:      docker tag test:1.0 gcr.io/nine-academy-854265/test:1.0$

# PUSH:     docker push gcr.io/nine-academy-854265/test:1.0

# GCR RUN:  docker run gcr.io/nine-academy-854265/test:1.0 