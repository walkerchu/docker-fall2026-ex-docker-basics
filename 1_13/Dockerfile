# DevOps with Docker, Fall 2026
# offer by The University of Helsinki
# Chapter 2/utilizing-tools-from-the-registry
# url: https://courses.mooc.fi/org/uh-cs/courses/devops-with-docker-fall-2026/chapter-2/utilizing-tools-from-the-registry
# Exercise 1.13. Hello backend
# created at Oct 17, 2026 22:24 HKT

FROM golang:1.27

WORKDIR /app

# pre-copy/cache go.mod for pre-downloading dependencies and only redownloading them in subsequent builds if they change
COPY go.mod go.sum ./
RUN go mod download

COPY . .

RUN go build -o server .

RUN go test ./...

# CMD ["app"]
CMD ["./server"]
