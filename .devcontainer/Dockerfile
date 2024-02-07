# Establecer la imagen base
FROM mcr.microsoft.com/dotnet/framework/sdk:4.8

# Instalar Node.js
RUN powershell -Command \
        wget https://nodejs.org/dist/v14.17.1/node-v14.17.1-x64.msi -OutFile nodejs.msi ; \
        Start-Process msiexec.exe -ArgumentList '/i', 'nodejs.msi', '/quiet', '/norestart' -NoNewWindow -Wait ; \
        Remove-Item .\nodejs.msi

# Verificar la instalación
RUN node --version
RUN npm --version