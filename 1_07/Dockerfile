# DevOps with Docker, Fall 2026
# offer by The University of Helsinki
# Exercise 1.7. Image for script
# url: https://courses.mooc.fi/org/uh-cs/courses/devops-with-docker-fall-2026/chapter-2/in-depth-dive-into-images
# created at Oct 15, 2026 02:51 HKT

FROM ubuntu:24.04

WORKDIR /usr/scr/app

COPY script.sh .

RUN apt update && \
    apt install -y curl && \
    chmod +x script.sh

CMD ["./script.sh"]