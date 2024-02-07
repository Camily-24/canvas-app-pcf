# Use an official Node.js runtime as a parent image
FROM node:18

# Set the working directory
WORKDIR /app

# Install .NET Core SDK and apt-transport-https (needed for Microsoft's packages)
RUN apt-get update && \
    apt-get install -y apt-transport-https && \
    curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin -Channel LTS

# Add Microsoft's GPG key
RUN curl -sSL https://packages.microsoft.com/keys/microsoft.asc | apt-key add -

# Add the repository for MSBuild
RUN sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/debian/10/prod buster main" > /etc/apt/sources.list.d/microsoft.list'

# Install MSBuild
RUN apt-get update && \
    apt-get install -y --no-install-recommends msbuild

# Install Power Apps CLI
RUN npm install -g @microsoft/powerapps-cli

# Add .NET Core and MSBuild to the PATH
ENV PATH="${PATH}:/root/.dotnet:/usr/bin/msbuild"