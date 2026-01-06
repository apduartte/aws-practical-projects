# Desafio 01 — AI Agent + MCP Server na AWS (Docker + ECR/ECS)

![AWS](https://img.shields.io/badge/AWS-Cloud-orange?logo=amazonaws&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Container-2496ED?logo=docker&logoColor=white)
![ECS](https://img.shields.io/badge/ECS-Containers-blue?logo=amazonecs&logoColor=white)
![ECR](https://img.shields.io/badge/ECR-Registry-blue?logo=amazonaws&logoColor=white)
![IAM](https://img.shields.io/badge/IAM-Security-black?logo=amazonaws&logoColor=white)
![CloudWatch](https://img.shields.io/badge/CloudWatch-Logs%2FMetrics-orange?logo=amazoncloudwatch&logoColor=white)

Projeto prático da **Formação AWS 5.0** para construir um **Agente de IA** integrado a um **MCP Server (Model Context Protocol)**, com ferramentas expostas via API, **containerização com Docker** e preparação para **deploy na AWS (ECR/ECS)** com observabilidade e segurança.

---

## 🎯 Objetivo
- Criar um **AI Agent** capaz de chamar ferramentas via **MCP Server**
- Containerizar com **Docker** e versionar no GitHub
- Preparar pipeline de deploy com **ECR/ECS**
- Implementar base de **segurança (IAM)** e **observabilidade (CloudWatch)**

---

## 🧩 Arquitetura (visão geral)
Usuário / Cliente  
⬇  
AI Agent  
⬇  
MCP Server (tools)  
⬇  
Ferramentas/Serviços (ex.: HTTP, banco, APIs internas)  
⬇  
Logs/Métricas (CloudWatch)

---

## 🛠️ Tecnologias
- AWS: **ECR**, **ECS**, **IAM**, **CloudWatch**
- **Docker**
- MCP Server (Model Context Protocol)
- (Opcional) RDS / Redis / integrações externas

---

## ✅ Entregáveis
- README didático + prints em `docs/`
- Dockerfile + comandos de execução local
- Checklist de custos e desligamento
- Roadmap de evolução (Terraform + ECS)

---

## 🚀 Como executar (local)
> Em construção — a execução local será adicionada conforme evolução do desafio.

---

## 🧠 Keywords (ATS)
**AWS • ECS • ECR • Docker • IAM • CloudWatch • AI Agent • MCP Server • Observability • Security**

---

## 🗺️ Roadmap
- [ ] Estruturar app e MCP Server
- [ ] Dockerfile + execução local
- [ ] Publicar imagem no ECR
- [ ] Deploy no ECS (Fargate)
- [ ] Logs no CloudWatch
- [ ] Infra como código (Terraform)

---

## 👩‍💻 Autora
Ana Paula Duarte  
📧 apduartte@gmail.com  
🔗 GitHub: https://github.com/apduartte
