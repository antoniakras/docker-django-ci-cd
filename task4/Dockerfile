# Use the Nginx image as the base image
FROM nginx:1.23.3

# Install dependencies
RUN apt-get update && \
    apt-get install -y make && \
    apt-get install -y curl && \
    apt-get install -y git && \
    curl  https://github.com/gohugoio/hugo/releases/download/v0.123.8/hugo_extended_0.123.8_linux-arm64.deb -o hugo.deb && \
    apt-get install -y ./hugo.deb && \
    git clone https://github.com/chazapis/hy548.git && \
    cd hy548 && \
    git submodule init && \
    git submodule update && \
    make && \
    cp -a html/public/. /usr/share/nginx/html/

# Expose to port localhost 8080
EXPOSE 8080

