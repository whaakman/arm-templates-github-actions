FROM mcr.microsoft.com/powershell:latest

LABEL "com.github.actions.name"="ARM TTK"
LABEL "com.github.actions.description"="Checks template with the ARM TTK"

LABEL version="0.0.1"
LABEL maintainer="Wesley Haakman" 

# Install Git
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y git

# Clone ARM-TTK Repo
RUN git clone https://github.com/Azure/arm-ttk.git
RUN git clone --single-branch --branch dev1 https://github.com/whaakman/arm-templates-github-actions.git /temp

# Copy the Entrypoint file from the current directory (the one the Dockerfile is located in)
COPY entrypoint.ps1 /entrypoint.ps1

# Start using the Entrypoint file.
ENTRYPOINT [ "pwsh", "/entrypoint.ps1" ]