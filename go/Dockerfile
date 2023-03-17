FROM golang:1.19-alpine AS builder
WORKDIR /app

COPY /go.mod /main.go ./
RUN go build


FROM scratch
# Copy our static executable.
COPY --from=builder /app/hello /app/

# Run the app binary when we run the container
ENTRYPOINT ["/app/hello"]