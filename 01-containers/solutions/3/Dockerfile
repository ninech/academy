FROM gcr.io/distroless/python3
WORKDIR /app
COPY . /app
CMD ["hello.py", "/etc"]

# BUILD:    docker build --tag test:1.0 .

# RUN:      docker run -p 80:80 test:1.0