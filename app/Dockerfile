FROM golang:1.16 as builder
COPY ./app/main.go ./main.go
RUN go build -o /gitops-go-app ./main.go

FROM gcr.io/distroless/base
EXPOSE 8080
COPY --from=builder /gitops-go-app ./
ENTRYPOINT ["./gitops-go-app"]
