# Projeto Semana Partiunuvem

Aplicação utilizada durante a construção do nosso projeto na Semana Partiunuvem.
Aplicação TFTEC Cloud sendo executada em .Net Core e conectada a um banco SQL Server.

![TFTEC Cloud](https://github.com/raphasi/partiunuvem/blob/master/EstruturaApp_IaaS.png "Semana Partikunuvem")


## Passos para realizar o deploy da sua aplicação:
1 - Download ASP.Net Core 7

https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-aspnetcore-7.0.5-windows-hosting-bundle-installer

2 - Após instalar seu servidor Windows Server 2022, execute o comando abaixo para realizar a instalação do IIS:


```cmd
   Install-WindowsFeature -name Web-Server -IncludeManagementTools

```
3 - Faça download da pasta do projeto utilizando o seguinte link:


   [https://github.com/raphasi/semanapartiunuvem/archive/refs/heads/master.zip](https://github.com/raphasi/partiunuvem/archive/refs/heads/master.zip)

4 - Copie a pasta "partiunuvem" para dentro do diretório c:\inetpub\wwwroot:
```cmd
  C:\inetpub\wwwroot\partiunuvem 
  
```
