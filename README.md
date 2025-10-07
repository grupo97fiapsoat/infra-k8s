# 🚀 Infraestrutura Kubernetes (EKS) – TechChallenge

Este repositório contém o código Terraform responsável por provisionar o cluster Kubernetes (EKS) na AWS para o projeto TechChallenge.

---

## 🧱 Estrutura

- `main.tf`: recursos principais do EKS (cluster, node group, roles, VPC)
- `variables.tf`: variáveis reutilizáveis (nome, região, tipo de instância, etc.)
- `outputs.tf`: exporta dados úteis como nome do cluster e endpoint
- `.github/workflows/deploy.yml`: pipeline CI/CD para aplicar o Terraform automaticamente

---

## 🚀 Provisionamento

O cluster é criado automaticamente via GitHub Actions sempre que há um merge na branch protegida (`main` ou `techchallenge_fase3`).

### Recursos criados:

- Cluster EKS
- Node Group com instâncias EC2
- Roles e policies necessárias
- VPC e subnets (se aplicável)
- Outputs com nome e endpoint do cluster

---

## 🔐 Segurança

Este repositório utiliza **GitHub Secrets** para armazenar credenciais sensíveis:

- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_REGION`

As credenciais são usadas apenas pelo workflow para autenticar na AWS e aplicar o Terraform.

---
## 🔄 CI/CD

O deploy automatizado é feito via GitHub Actions:

- Proteção de branch ativa
- Merge via Pull Request obrigatório
- Workflow executa `terraform apply` automaticamente

---

## ✅ Requisitos atendidos

- [x] Infra separada em repositório dedicado
- [x] Provisionamento via Terraform
- [x] Deploy automatizado com GitHub Actions
- [x] Uso de Secrets para segurança
- [x] Branch protegida com PR obrigatório

---

## 📎 Referência

Este repositório faz parte da arquitetura do projeto TechChallenge.

---

## 📄 Como aplicar manualmente (opcional)

```bash
terraform init
terraform apply
