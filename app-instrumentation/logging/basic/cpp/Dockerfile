FROM ubuntu:24.04

# Install build dependencies
RUN apt-get update && apt-get install -y \
    cmake \
    g++ \
    make \
    git \
    pkg-config \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app

COPY . .

# Build the application
RUN cmake -B build -S . && \
    cmake --build build --config Release

# Run the application
CMD ["./build/logging_example"] 