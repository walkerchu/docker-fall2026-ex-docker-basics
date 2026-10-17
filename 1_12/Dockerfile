# DevOps with Docker, Fall 2026
# offer by The University of Helsinki
# Chapter 2/utilizing-tools-from-the-registry
# url: https://courses.mooc.fi/org/uh-cs/courses/devops-with-docker-fall-2026/chapter-2/utilizing-tools-from-the-registry
# Exercise 1.12. Hello frontend
# created at Oct 17, 2026 18:24 HKT


FROM ubuntu

# 1. Install system dependencies (Cached forever unless this block changes)
RUN apt-get update && apt-get install -y --no-install-recommends \
    curl ca-certificates gnupg \
    && rm -rf /var/lib/apt/lists/*

# 2. Add Node repository and install Node.js (Cached)
RUN curl -sL https://deb.nodesource.com/setup_16.x | bash - \
    && apt-get install -y nodejs \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app

# 3. Copy ONLY package files first to cache npm dependencies
COPY package*.json ./
RUN npm install

# 4. Copy application source code
COPY . .

# Starting in production mode
# Exercise 1.12 -> to run the project
RUN <<EOF
npm run build
npm install -g serve
EOF

CMD [ "serve", "-s", "-l", "5001", "build" ]
