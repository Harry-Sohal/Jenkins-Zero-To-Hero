# You can change this base image to anything else
# But make sure to use the correct version of Java
# Use Java 17 as base
FROM eclipse-temurin:17-jdk-alpine

# Install required tools
RUN apk add --no-cache \
    maven \
    git \
    docker-cli \
    bash \
    tini \
    shadow

# Create a non-root Jenkins user (UID/GID 111 to match your Jenkins host)
RUN groupadd -g 113 jenkins \
    && useradd -u 111 -g 113 -m -s /bin/bash jenkins \
    && mkdir -p /workspace \
    && chown -R jenkins:jenkins /workspace

WORKDIR /workspace

# Switch to Jenkins user by default
USER jenkins

# Use tini to handle signals correctly (optional but good practice)
ENTRYPOINT ["/sbin/tini", "--"]

# Keep container alive for Jenkins agents
CMD ["sleep", "infinity"]


