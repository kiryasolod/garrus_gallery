# Builder
FROM rust:1.81.0-alpine as builder
WORKDIR /usr/src/garrus_gallery_server
RUN apk add --no-cache musl-dev gcc
COPY . .
RUN cargo install --path .

# Runtime
FROM alpine:latest
RUN apk add --no-cache libgcc libstdc++
COPY --from=builder /usr/local/cargo/bin/server /usr/bin/server
CMD ["server"]
