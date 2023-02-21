# Base layer image
FROM srs-base:1.0

# Install zlib-dvel needed for setup TLS communication
RUN tdnf install zlib-devel -y

# Copy SRS setup application
ADD /app/service/ /app/service/

WORKDIR /app/service

# Start setup cli
CMD ["/bin/bash", "-c", "if [-z ${SRS_LOG} ]; then; /app/service/setup; else; /app/service/setup 2>&1 | tee \"${SRS_LOG}\"; fi"]
