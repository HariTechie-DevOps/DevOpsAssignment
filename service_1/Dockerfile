# Stage 1: Build the Go app
FROM golang:1.21-alpine AS builder

WORKDIR /app
COPY . .

# Build the app
RUN go build -o service1

# Stage 2: Create a minimal runtime image
FROM alpine:latest

WORKDIR /app
COPY --from=builder /app/service1 .

# Run the binary
CMD ["./service1"]

