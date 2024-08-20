# Use the universal base image
FROM mcr.microsoft.com/devcontainers/universal:2-linux

# Install xz-utils, Django, and MongoDB
RUN apt-get update && \
    apt-get install -y xz-utils gnupg && \
    pip install django && \
    wget -qO - https://www.mongodb.org/static/pgp/server-6.0.asc | apt-key add - && \
    echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-6.0.list && \
    apt-get update && \
    apt-get install -y mongodb-org && \
    rm -rf /var/lib/apt/lists/*

# Start MongoDB when the container starts (optional)
CMD ["mongod"]
