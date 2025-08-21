FROM mcr.microsoft.com/devcontainers/java:17

# Temporarily switch to root to install coursier globally
USER root

# Install Coursier (cs launcher) for x86-64 and make it globally available
RUN curl -fL https://github.com/coursier/coursier/releases/latest/download/cs-x86_64-pc-linux.gz \
    | gzip -d > /usr/local/bin/cs \
    && chmod +x /usr/local/bin/cs

# Switch back to the vscode user
USER vscode

# The 'cs setup' command and 'cs install' should now be run as the vscode user.
# This ensures that user-specific files are written to the correct home directory.
RUN cs setup -y && cs install scala sbt

# Explicitly add the Coursier bin directory to the PATH for the vscode user.
ENV PATH="/home/vscode/.local/share/coursier/bin:${PATH}"