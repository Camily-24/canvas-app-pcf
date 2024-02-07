# Establecer la imagen base
FROM mcr.microsoft.com/dotnet/sdk:5.0

# Instalar Node.js
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash -
RUN apt-get install -y nodejs

# Verificar la instalación
RUN dotnet --version
RUN node --version
RUN npm --version