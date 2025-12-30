# Desafio RDS + SQL Server na AWS

Este projeto documenta a criação de uma instância EC2 com SQL Server 2022 via Docker, utilizando práticas seguras de acesso com AWS Systems Manager e SSH, além da restauração do banco AdventureWorks2022.

## 📄 Documentação
[📥 Clique aqui para abrir o PDF com os prints e etapas do desafio](Desafio2_RDS_SQLServer.pdf)

## ⚙️ Tecnologias utilizadas
- Amazon EC2
- Amazon Linux / Ubuntu
- Docker
- SQL Server 2022
- AWS Systems Manager
- DBeaver
- AdventureWorks2022

## 🔐 Segurança
- Acesso via Session Manager (sem expor porta 1433)
- Chave SSH (.pem) com permissões restritas
- Port forwarding seguro para conexão local

## 📦 Banco restaurado
- AdventureWorks2022.bak importado com sucesso
- Ambiente pronto para consultas e testes

---

**Autor:** Ana Paula Duarte  
**Contato:** apduartte@gmail.com
