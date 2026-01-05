# Desafio RDS + SQL Server na AWS

![AWS](https://img.shields.io/badge/AWS-Cloud-orange?logo=amazonaws&logoColor=white)
![EC2](https://img.shields.io/badge/EC2-Instance-blue?logo=amazonec2&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Container-2496ED?logo=docker&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-2022-red?logo=microsoftsqlserver&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-24.04-brown?logo=ubuntu&logoColor=white)
![DBeaver](https://img.shields.io/badge/DBeaver-Client-green?logo=dbeaver&logoColor=white)

Projeto prático que documenta a criação de uma instância EC2 na AWS, execução do SQL Server 2022 em container Docker, adoção de práticas seguras de acesso (AWS Systems Manager e SSH) e restauração do banco AdventureWorks2022.
O projeto simula cenários corporativos reais de uso de banco de dados em nuvem.

📄 Documentação

📥 PDF com prints e passo a passo do desafio:
Desafio RDS + SQL Server na AWS (PDF)

🎯 Objetivo

Demonstrar o provisionamento, configuração e operação de um ambiente SQL Server na AWS, aplicando conceitos de:

Cloud Computing

Segurança

Persistência de dados

Integração aplicação–banco

Boas práticas de infraestrutura moderna

🏗️ Arquitetura (Visão Geral)

Usuário / Ferramenta Cliente (DBeaver)
⬇
EC2 (Ubuntu)
⬇
Docker
⬇
SQL Server 2022
⬇
Banco Relacional (AdventureWorks2022)

Arquitetura simples, porém representativa de ambientes corporativos em nuvem.

⚙️ Tecnologias Utilizadas

Amazon Web Services (AWS)

Amazon EC2

Ubuntu 24.04

Docker

SQL Server 2022

AWS Systems Manager (Session Manager)

DBeaver

AdventureWorks2022

🧠 Conceitos Demonstrados (Keywords ATS)

Cloud Computing (AWS)

Bancos de dados relacionais

Persistência de dados

Integração aplicação–banco

Infraestrutura como código (fundamentos)

Sistemas distribuídos (conceitos)

Segurança em ambientes cloud

Ambientes corporativos em nuvem

🧪 Testes Automatizados

Testes automatizados (fundamentos)
Estrutura preparada para validação de regras e integração com banco de dados, podendo ser evoluída para testes unitários e de integração conforme a aplicação.

🐳 Docker

Docker utilizado para execução do SQL Server em container

Padronização do ambiente

Facilidade de setup e testes locais

☸️ Kubernetes

Kubernetes (exemplo / conceito)
Projeto preparado para estudos de deploy e service, simulando execução em ambiente orquestrado.

🔐 Segurança

Acesso via AWS Systems Manager (Session Manager), sem exposição da porta 1433

Uso de chave SSH (.pem) com permissões restritas

Port forwarding seguro para conexão local

Boas práticas de isolamento de recursos em nuvem

📦 Banco de Dados

Banco AdventureWorks2022 restaurado com sucesso

Ambiente pronto para consultas, estudos e testes

🖥️ Principais Comandos Utilizados
🔑 Conexão SSH
ssh -i ~/.ssh/bia-conectividade-linux.pem ec2-user@<public-dns-ec2>

🐳 Verificação do Docker
docker --version
docker ps

📥 Download do AdventureWorks2022
wget https://github.com/.../AdventureWorks2022.bak
ls AdventureWorks2022.bak

🗄️ Subir container do SQL Server 2022
docker run -e "ACCEPT_EULA=Y" \
  -e "MSSQL_SA_PASSWORD=SenhaSegura123!" \
  -p 1433:1433 \
  --name sql1 \
  --hostname sql1 \
  -d mcr.microsoft.com/mssql/server:2022-latest

🛠️ Conexão via sqlcmd
docker exec -it sql1 /opt/mssql-tools/bin/sqlcmd -S localhost -U sa -P 'SenhaSegura123!'

📂 Restaurar banco AdventureWorks2022
RESTORE DATABASE AdventureWorks2022
FROM DISK = '/var/opt/mssql/data/AdventureWorks2022.bak'
WITH MOVE 'AdventureWorks2022' 
     TO '/var/opt/mssql/data/AdventureWorks2022.mdf',
     MOVE 'AdventureWorks2022_log' 
     TO '/var/opt/mssql/data/AdventureWorks2022.ldf';

🚀 Evoluções Possíveis

Integração com aplicações Java ou .NET

Criação de pipelines CI/CD

Implementação completa de testes automatizados

Automação de infraestrutura com Terraform

Evolução para RDS gerenciado e/ou Kubernetes

📚 Contexto

Projeto desenvolvido com foco em aprendizado contínuo, prática em cloud AWS e preparação para cenários reais de engenharia de software e dados.

Autora: Ana Paula Duarte
📧 Contato: apduartte@gmail.com

🔗 GitHub: https://github.com/apduartte
