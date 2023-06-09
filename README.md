# Projeto Semana Partiunuvem

Aplicação utilizada durante a construção do nosso projeto na Semana Partiunuvem.
Aplicação TFTEC Cloud sendo executada em .Net Core e conectada a um banco SQL Server.

![TFTEC Cloud](https://github.com/iblayr/tftec-partiunuvem/blob/main/EstruturaApp_IaaS.png "Semana Partikunuvem")

# Primeira Etapa - Implantando uma aplicação em Cloud IaaS

## Passos para realizar o deploy da aplicação:
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
# Segunda Etapa - Modernizando a aplicação em Cloud com PaaS

Modernizando a estrutura de aplicação e banco de dados utilizando serviços Cloud Azure PaaS.

![TFTEC Cloud](https://github.com/iblayr/tftec-partiunuvem/blob/main/EstruturaApp_PaaS.png "Semana Partiunuvem")

## Etapa de Modernização do Banco de dados
1 - Download e instalação do Net .Framework 4.8 na VM-DB:

https://dotnet.microsoft.com/en-us/download/dotnet-framework/thank-you/net48-offline-installer

2 - Download e instalaçao do DMA (Data Migration Assistant) na VM-DB:

https://www.microsoft.com/en-us/download/confirmation.aspx?id=53595

3 - Atividades executadas para migrar o banco de dados de IaaS para PaaS:
- Criar um uma instância de Server SQL para hospedar o Azure SQL Database
- Criar uma instância de Azure SQL Database
- Utilizar o DMA para rodar um Assessment de compatilbilidade do banco antes da migração
- Parar a aplicação (iisreset /stop)
- Utilizar o DMA para rodar a migração do Schema do banco
- Utilizar o DMA para rodar a migração dos dados para o Azure SQL Database
- Conferir os dados migrados
- Desabilitar o serviço do SQL no servidor de oriem (IaaS)
- Alterar o endereço na string de conexão do servidor de aplicação
- Desligar a VM-DB

## Etapa de Modernização da Aplicação
1 - Download e instalação do App Service migration assistant na VM-APP:

https://azure.microsoft.com/en-au/products/app-service/migration-tools/

2 - Atividades executadas para migrar a aplicação de IaaS para PaaS:
- Criar um App Service Plan
- Fazer Upgrade do App Service Plan para uma instância S2 (Somente quem estiver com conta trial)
- Criar um Projeto no Azure Migrate
- Utilizar o App Service migration assistant para migração do site
- Ajustar a string de conexão no seu Web APP
- Desligar a VM-APP