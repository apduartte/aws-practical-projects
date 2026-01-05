# Desafio 03 — SQL Server 2022 na AWS (EC2 + Docker + SSM)

![AWS](https://img.shields.io/badge/AWS-Cloud-orange?logo=amazonaws&logoColor=white)
![EC2](https://img.shields.io/badge/EC2-Instance-blue?logo=amazonec2&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Container-2496ED?logo=docker&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-2022-red?logo=microsoftsqlserver&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-24.04-brown?logo=ubuntu&logoColor=white)
![DBeaver](https://img.shields.io/badge/DBeaver-Client-green?logo=dbeaver&logoColor=white)

Projeto prático da **Formação AWS 5.0** que implementa um ambiente de **SQL Server 2022** em **container Docker** dentro de uma **instância EC2 (Ubuntu)**, com **acesso seguro via AWS Systems Manager (SSM)** (e SSH quando necessário) e **restauração do banco AdventureWorks2022**.

---

## 🎯 Objetivo
Demonstrar a criação e operação de um ambiente de banco de dados na AWS, aplicando:
- **Provisionamento e operação em Cloud (EC2)**
- **Containerização (Docker)**
- **Segurança de acesso (SSM / IAM / Security Groups)**
- **Administração de banco (backup/restore, validações)**
- **Troubleshooting e observabilidade básica (logs)**

---

## 🏗️ Arquitetura (visão geral)
**Cliente (DBeaver / sqlcmd)**  
⬇ (conexão segura)  
**EC2 (Ubuntu)**  
⬇  
**Docker**  
⬇  
**SQL Server 2022**  
⬇  
**AdventureWorks2022**

> Arquitetura simples, porém representativa de cenários corporativos em nuvem.

---

## ⚙️ Tecnologias utilizadas
- AWS: **EC2**, **IAM**, **Systems Manager (SSM)**, **Security Groups**
- **Ubuntu 24.04**
- **Docker**
- **SQL Server 2022**
- **DBeaver**
- Base: **AdventureWorks2022**

---

## 🔒 Segurança (pontos valorizados por recrutadores)
- Acesso preferencial via **SSM Session Manager** (reduz exposição de SSH)
- **Security Group restritivo** (evitar expor a porta 1433 publicamente)
- **Senha forte** para usuário `sa` e segredos fora do repositório
- Prática de operação com checklist de **desligamento** para evitar custos

---

## 🚀 Execução (resumo)
1. Criar EC2 (Ubuntu) e configurar SG
2. Associar Role IAM e habilitar SSM
3. Instalar Docker na EC2
4. Subir SQL Server 2022 em container
5. Restaurar o **AdventureWorks2022**
6. Conectar via DBeaver e validar

---

## 🖥️ Comandos principais (exemplo)

### Subir SQL Server 2
