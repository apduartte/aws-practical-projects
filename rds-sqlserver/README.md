# Desafio RDS + SQL Server na AWS

![AWS](https://img.shields.io/badge/AWS-Cloud-orange?logo=amazonaws&logoColor=white)
![EC2](https://img.shields.io/badge/EC2-Instance-blue?logo=amazonec2&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Container-2496ED?logo=docker&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-2022-red?logo=microsoftsqlserver&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-24.04-brown?logo=ubuntu&logoColor=white)
![DBeaver](https://img.shields.io/badge/DBeaver-Client-green?logo=dbeaver&logoColor=white)

Este projeto documenta a criação de uma instância EC2 com SQL Server 2022 via Docker, utilizando práticas seguras de acesso com AWS Systems Manager e SSH, além da restauração do banco AdventureWorks2022.

## 📄 Documentação
[📥 Clique aqui para abrir o PDF com os prints e etapas do desafio](Desafio2_RDS_SQLServer.pdf)

---

## ⚙️ Tecnologias utilizadas
- Amazon EC2
- Amazon Linux / Ubuntu
- Docker
- SQL Server 2022
- AWS Systems Manager
- DBeaver
- AdventureWorks2022

---

## 🔐 Segurança
- Acesso via Session Manager (sem expor porta 1433)
- Chave SSH (.pem) com permissões restritas
- Port forwarding seguro para conexão local

---

## 📦 Banco restaurado
- AdventureWorks2022.bak importado com sucesso
- Ambiente pronto para consultas e testes

---

## 🖥️ Principais comandos utilizados

### 🔑 Conexão SSH
```bash
ssh -i ~/.ssh/bia-conectividade-linux.pem ec2-user@ec2-44-222-255-252.compute-1.amazonaws.com

## 🐳 Verificação do Docker
```bash
docker --version
docker ps

## 📥 Download do AdventureWorks2022
```bash
wget https://github.com/.../AdventureWorks2022.bak
ls AdventureWorks2022.bak

## 🗄️ Subir container do SQL Server 2022
```bash
docker run -e "ACCEPT_EULA=Y" \
  -e "MSSQL_SA_PASSWORD=SenhaSegura123!" \
  -p 1433:1433 --name sql1 --hostname sql1 \
  -d mcr.microsoft.com/mssql/server:2022-latest

## 🛠️ Conexão via sqlcmd
```bash
docker exec -it sql1 /opt/mssql-tools/bin/sqlcmd -S localhost -U sa -P 'SenhaSegura123!'

## 📂 Restaurar banco AdventureWorks
```bash
RESTORE DATABASE AdventureWorks2022
FROM DISK = '/var/opt/mssql/data/AdventureWorks2022.bak'
WITH MOVE 'AdventureWorks2022' TO '/var/opt/mssql/data/AdventureWorks2022.mdf',
     MOVE 'AdventureWorks2022_log' TO '/var/opt/mssql/data/AdventureWorks2022.ldf';
	 
	 Autor: Ana Paula Duarte
Contato: apduartte@gmail.com

