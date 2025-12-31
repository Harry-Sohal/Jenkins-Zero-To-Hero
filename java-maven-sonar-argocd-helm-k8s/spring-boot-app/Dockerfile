# You can change this base image to anything else
# But make sure to use the correct version of Java
FROM eclipse-temurin:17-jdk-alpine

# Install required tools
RUN apk add --no-cache \
    maven \
    git \
    docker-cli \
    bash

WORKDIR /workspace

# Keep container alive for Jenkins
CMD ["sleep", "infinity"]

