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

## 📄 Como aplicar manualmente (opcional)

```bash
terraform init
terraform apply
