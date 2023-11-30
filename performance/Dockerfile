# This is the first phase where we build with all dependencies
FROM golang as builder
WORKDIR /app
COPY . .

# This will be my production image, light and clean
FROM alpine
RUN CGO_ENABLED=0 GOOS=linux go build -o tool ./...
CMD ["./ssmx"]
