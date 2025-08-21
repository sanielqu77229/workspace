FROM mcr.microsoft.com/devcontainers/java:17

# Install Coursier (cs launcher)
RUN curl curl -fL https://github.com/coursier/coursier/releases/latest/download/cs-x86_64-pc-linux.gz \
    | gzip -d > /usr/local/bin/cs \
    && chmod +x /usr/local/bin/cs \
    && cs setup -y

# Add coursier-installed tools (scala, sbt, etc.) to PATH
ENV PATH="/root/.local/share/coursier/bin:${PATH}"
