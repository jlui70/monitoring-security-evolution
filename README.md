# 🔐 Monitoring Security Evolution

<p align="center">
  <img src="https://img.shields.io/badge/Security-5_Levels-red?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Docker-Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/Kubernetes-K8s-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white" />
  <img src="https://img.shields.io/badge/HashiCorp-Vault-000000?style=for-the-badge&logo=vault&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS-Secrets_Manager-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white" />
</p>

> **Jornada completa de segurança em monitoramento: do básico funcional ao enterprise-grade com Zero-Trust Architecture**

---

## 📖 Sobre o Projeto

Este projeto demonstra a **evolução progressiva de segurança** em stacks de monitoramento, começando de uma implementação básica funcional até arquiteturas enterprise com Zero-Trust. Cada nível adiciona camadas de segurança, secrets management e melhores práticas de DevSecOps.

### 🎯 Objetivo

Proporcionar um **caminho de aprendizado prático** para implementar segurança em ambientes de monitoramento, permitindo que você:

- 📚 **Aprenda gradualmente** conceitos de segurança
- 🔄 **Compare diferentes abordagens** de secrets management
- 🚀 **Migre entre níveis** conforme sua maturidade
- 💰 **Escolha o nível adequado** ao seu orçamento e necessidades

---

## 📊 Níveis de Maturidade em Segurança

<table>
<tr>
<th>Level</th>
<th>Segurança</th>
<th>Stack</th>
<th>Secrets</th>
<th>Custo/mês</th>
<th>Status</th>
</tr>
<tr>
<td>🟢 <a href="https://github.com/jlui70/monitoring-security-level1"><strong>L1</strong></a></td>
<td><strong>Base</strong></td>
<td>Docker Compose</td>
<td>Hardcoded ⚠️</td>
<td>$0</td>
<td>✅ Completo</td>
</tr>
<tr>
<td>🟡 <a href="https://github.com/jlui70/monitoring-security-level2"><strong>L2</strong></a></td>
<td><strong>Env Vars</strong></td>
<td>Docker Compose</td>
<td>.env files</td>
<td>$0</td>
<td>✅ Completo</td>
</tr>
<tr>
<td>🟠 <a href="https://github.com/jlui70/monitoring-security-level3"><strong>L3</strong></a></td>
<td><strong>Vault</strong></td>
<td>Docker + Vault</td>
<td>HashiCorp Vault</td>
<td>$0</td>
<td>✅ Completo</td>
</tr>
<tr>
<td>🔴 <a href="https://github.com/jlui70/monitoring-security-level4"><strong>L4</strong></a></td>
<td><strong>Cloud</strong></td>
<td>AWS ECS/Fargate</td>
<td>AWS Secrets Mgr</td>
<td>~$0.40</td>
<td>✅ Completo</td>
</tr>
<tr>
<td>🟣 <strong>L5</strong></td>
<td><strong>Zero-Trust</strong></td>
<td>K8s + Vault</td>
<td>External Secrets</td>
<td>~$5-10</td>
<td>🔜 Em breve</td>
</tr>
</table>

---

## 🎓 Jornada de Aprendizado

### 📍 Você Está Aqui

```
┌──────────────────────────────────────────────────────────────┐
│                  EVOLUÇÃO DE SEGURANÇA                       │
└──────────────────────────────────────────────────────────────┘

   L1           L2         L3          L4          L5
┌──────┐    ┌──────┐    ┌──────┐    ┌──────┐    ┌──────┐
│ Base │ -> │ Env  │ -> │ Vault│ -> │ AWS  │ -> │ Zero │
│      │    │ Vars │    │      │    │Cloud │    │ Trust│
└──────┘    └──────┘    └──────┘    └──────┘    └──────┘
   ↓           ↓           ↓           ↓           ↓
Docker      .env        On-Prem     Secrets      K8s +
Compose     Files       Vault       Manager      Vault

$0/mês      $0/mês      $0/mês     ~$0.40/mês   ~$5-10/mês
Dev/POC    Dev/Stage    Small Prod  Medium Prod  Enterprise
```

---

## 🚀 Quick Start por Nível

### 🟢 Level 1: Base Funcional

**Ideal para:** Aprendizado inicial, desenvolvimento local, POCs

```bash
git clone https://github.com/jlui70/monitoring-security-level1.git
cd monitoring-security-level1
docker-compose up -d
```

**Stack incluído:**
- 📊 Zabbix Server + Agent
- 📈 Grafana
- 📉 Prometheus
- 🗄️ MySQL
- ⚡ Nginx

**Características:**
- ✅ Setup rápido (< 5 minutos)
- ✅ Tudo funcional out-of-the-box
- ⚠️ Secrets em plaintext (apenas para dev)
- 💰 Custo: $0 (on-premise)

---

### 🟡 Level 2: Environment Variables

**Ideal para:** Separação de ambientes (dev/staging/prod)

```bash
git clone https://github.com/jlui70/monitoring-security-level2.git
cd monitoring-security-level2
# Siga instruções no README para configurar .env
```

**Evolução do Level 1:**
- ✅ Secrets em arquivos .env separados
- ✅ Suporte a múltiplos ambientes
- ✅ Melhor organização de configurações
- ✅ Gitignore para .env files
- 💰 Custo: $0 (on-premise)

**Uso típico:**
```bash
# Desenvolvimento
docker-compose --env-file .env.dev up -d

# Staging
docker-compose --env-file .env.staging up -d

# Produção
docker-compose --env-file .env.prod up -d
```

---

### 🟠 Level 3: HashiCorp Vault (On-Premise)

**Ideal para:** Produção on-premise, compliance, rotation automática

```bash
git clone https://github.com/jlui70/monitoring-security-level3.git
cd monitoring-security-level3
# Siga instruções para setup do Vault
```

**Evolução do Level 2:**
- ✅ **HashiCorp Vault** para secrets centralizados
- ✅ **Encryption at rest** e in transit
- ✅ **Rotation automática** de secrets
- ✅ **Audit logs** completos
- ✅ **Dynamic secrets** com TTL
- ✅ **Access policies** granulares
- 💰 Custo: $0 (on-premise, self-hosted)

**Features principais:**
- 🔐 KV Secrets Engine v2 (versionamento)
- 🔄 Database credentials rotation
- 📝 Audit logging
- 🎫 Token-based authentication
- 🛡️ Policy-based access control

---

### 🔴 Level 4: AWS Secrets Manager (Cloud Native)

**Ideal para:** Workloads na AWS, compliance cloud, managed services

```bash
git clone https://github.com/jlui70/monitoring-security-level4.git
cd monitoring-security-level4
# Requer AWS CLI configurado
```

**Evolução do Level 3:**
- ✅ **AWS Secrets Manager** totalmente gerenciado
- ✅ Integração nativa com **ECS/Fargate**
- ✅ **Rotation automática** via Lambda
- ✅ **Encryption com KMS**
- ✅ **Fine-grained IAM policies**
- ✅ **VPC Endpoints** para segurança adicional
- 💰 Custo: ~$0.40/mês ($0.40 por secret)

**Arquitetura:**
```
┌────────────────────────────────────────┐
│       AWS Cloud (us-east-1)            │
│                                        │
│  ┌────────────────────────────┐        │
│  │   AWS Secrets Manager      │        │
│  │  - Secrets versionados     │        │
│  │  - Rotation automatica     │        │
│  │  - Encryption com KMS      │        │
│  └───────────┬────────────────┘        │
│              │                         │
│  ┌───────────┴────────────────┐        │
│  │    ECS/Fargate Tasks       │        │
│  │  - Zabbix Server           │        │
│  │  - Grafana                 │        │
│  │  - Prometheus              │        │
│  └────────────────────────────┘        │
└────────────────────────────────────────┘
```

---

### 🟣 Level 5: Zero-Trust Architecture (Kubernetes)

**Ideal para:** Enterprise, multi-cloud, microservices

> 🔜 **Em desenvolvimento** - Previsão de lançamento: Q1 2026

**Planejado:**
- ✅ **Kubernetes** com RBAC avançado
- ✅ **HashiCorp Vault** em HA mode
- ✅ **External Secrets Operator** (ESO)
- ✅ **Service Mesh** (Istio/Linkerd) com mTLS
- ✅ **Policy Engine** (OPA/Kyverno)
- ✅ **Secret rotation** automática end-to-end
- 💰 Custo estimado: ~$5-10/mês (cluster pequeno)

**Arquitetura planejada:**
```
┌──────────────────────────────────────────┐
│        Kubernetes Cluster                │
│                                          │
│  ┌────────────────────────────────────┐  │
│  │ External Secrets Operator (ESO)    │  │
│  │            |                       │  │
│  │      ┌─────┼─────┐                 │  │
│  │      |           |                 │  │
│  │  ┌───┴───┐   ┌───┴────┐            │  │
│  │  │ Vault │   │  AWS   │            │  │
│  │  │Secrets│   │Secrets │            │  │
│  │  │       │   │Manager │            │  │
│  │  └───────┘   └────────┘            │  │
│  └────────────────────────────────────┘  │
│                                          │
│  ┌────────────────────────────────────┐  │
│  │   Service Mesh (mTLS)              │  │
│  │                                    │  │
│  │  ┌───────────────────────────┐     │  │
│  │  │ Zabbix <-> Grafana <->    │     │  │
│  │  │         Prometheus         │    │  │
│  │  └───────────────────────────┘     │  │
│  └────────────────────────────────────┘  │
└──────────────────────────────────────────┘
```

---

## 📊 Comparação Detalhada de Features

| Feature / Capacidade | L1 | L2 | L3 | L4 | L5 |
|---------------------|----|----|----|----|-----|
| **🔒 Segurança de Secrets** |
| Secrets em Plain Text | ❌ | ✅ | ✅ | ✅ | ✅ |
| Environment Variables | ✅ | ✅ | ✅ | ✅ | ✅ |
| Centralized Secret Store | ❌ | ❌ | ✅ | ✅ | ✅ |
| Encryption at Rest | ❌ | ❌ | ✅ | ✅ | ✅ |
| Encryption in Transit | ❌ | ❌ | ✅ | ✅ | ✅ |
| **🔄 Automation** |
| Automatic Rotation | ❌ | ❌ | ✅ | ✅ | ✅ |
| Dynamic Secrets | ❌ | ❌ | ✅ | ⚠️ | ✅ |
| Secret Versioning | ❌ | ❌ | ✅ | ✅ | ✅ |
| **👥 Access Control** |
| Role-Based Access (RBAC) | ❌ | ❌ | ✅ | ✅ | ✅ |
| Fine-Grained Policies | ❌ | ❌ | ✅ | ✅ | ✅ |
| Audit Logging | ❌ | ❌ | ✅ | ✅ | ✅ |
| **🏗️ Infraestrutura** |
| Docker Compose | ✅ | ✅ | ✅ | ❌ | ❌ |
| Cloud Native (AWS) | ❌ | ❌ | ❌ | ✅ | ⚠️ |
| Kubernetes | ❌ | ❌ | ❌ | ❌ | ✅ |
| Service Mesh (mTLS) | ❌ | ❌ | ❌ | ❌ | ✅ |
| **💰 Custos** |
| Setup Inicial | Grátis | Grátis | Grátis | ~$50 | ~$100 |
| Custo Mensal (on-prem) | $0 | $0 | $0 | - | - |
| Custo Mensal (AWS) | - | - | - | ~$0.40 | ~$5-10 |
| **📈 Escalabilidade** |
| Para quantos secrets? | ~10 | ~50 | ~500+ | ~1000+ | ~10000+ |
| Equipes simultâneas | 1-2 | 2-5 | 5-20 | 20-50 | 50+ |

---

## 🎯 Qual Nível Escolher?

### 🟢 Escolha Level 1 se você:
- Está **aprendendo** monitoramento
- Precisa de um **POC rápido**
- Trabalha apenas em **ambiente local/dev**
- Quer entender as ferramentas antes de adicionar complexidade

### 🟡 Escolha Level 2 se você:
- Precisa separar **dev/staging/prod**
- Trabalha em **equipe pequena** (2-5 pessoas)
- Quer melhorar segurança sem adicionar ferramentas extras
- Tem **requisitos básicos** de compliance

### 🟠 Escolha Level 3 se você:
- Está em **produção on-premise**
- Precisa de **compliance** (SOC2, ISO 27001)
- Requer **rotation automática** de secrets
- Tem equipe para **gerenciar Vault**
- Quer **total controle** sobre seus dados

### 🔴 Escolha Level 4 se você:
- Já está na **AWS**
- Quer **managed service** (menos overhead)
- Precisa integrar com **ECS, Lambda, RDS, etc**
- Prefere **pagar** para não gerenciar infraestrutura
- Tem workloads **cloud-native**

### 🟣 Escolha Level 5 se você:
- Está em **ambiente Kubernetes**
- Precisa de **Zero-Trust** architecture
- Trabalha com **microservices** complexos
- Requer **mTLS** entre serviços
- Tem budget para **enterprise-grade** security

---

## 🛠️ Stack de Tecnologias

### Monitoramento (Todos os Níveis)
- 📊 **Zabbix** 6.x - Monitoramento de infraestrutura
- 📈 **Grafana** - Visualização de métricas
- 📉 **Prometheus** - Coleta de métricas
- 🗄️ **MySQL/PostgreSQL** - Banco de dados

### Secrets Management (Por Nível)
- **Level 1-2:** Environment variables
- **Level 3:** HashiCorp Vault (self-hosted)
- **Level 4:** AWS Secrets Manager
- **Level 5:** Vault + External Secrets Operator

### Orquestração (Por Nível)
- **Level 1-3:** Docker Compose
- **Level 4:** AWS ECS/Fargate
- **Level 5:** Kubernetes

---

## 📚 Documentação e Recursos

### 📖 Documentação por Nível

Cada nível possui documentação completa em seu repositório:

- [📘 Level 1 - Documentation](https://github.com/jlui70/monitoring-security-level1#readme)
- [📗 Level 2 - Documentation](https://github.com/jlui70/monitoring-security-level2#readme)
- [📙 Level 3 - Documentation](https://github.com/jlui70/monitoring-security-level3#readme)
- [📕 Level 4 - Documentation](https://github.com/jlui70/monitoring-security-level4#readme)

### 🎬 Vídeos e Tutoriais

> 🎥 **Vídeos em produção!** Acompanhe no canal:

- 📹 **YouTube:** [DevOps Project](https://www.youtube.com/@devops-project)
- 💼 **Portfólio:** [devopsproject.com.br](https://devopsproject.com.br/)

**Conteúdo planejado:**
- 🎬 Walkthrough completo de cada nível
- 🎬 Migração entre níveis
- 🎬 Troubleshooting comum
- 🎬 Melhores práticas de segurança

### 📄 Artigos e Blog Posts

- 📝 Comparação: Vault vs AWS Secrets Manager
- 📝 Quando usar cada nível?
- 📝 Migração de secrets sem downtime
- 📝 Cost optimization em secrets management

---

## 🚦 Roadmap

### ✅ Concluído
- [x] Level 1: Base Funcional (Docker Compose)
- [x] Level 2: Environment Variables
- [x] Level 3: HashiCorp Vault On-Premise
- [x] Level 4: AWS Secrets Manager + Cloud Native

### 🚧 Em Desenvolvimento
- [ ] Level 5: Kubernetes + Zero-Trust
  - [ ] External Secrets Operator
  - [ ] Service Mesh (Istio/Linkerd)
  - [ ] Policy Engine (OPA)
  - [ ] Multi-cloud support

### 🔮 Planejado para o Futuro
- [ ] Level 6: Multi-Cloud (AWS + Azure + GCP)
- [ ] Comparação com outras soluções (1Password, Doppler)
- [ ] Terraform modules para cada nível
- [ ] Helm charts para Level 5
- [ ] CI/CD pipelines examples
- [ ] Disaster recovery procedures

---

## 💡 Guias de Migração

### Migrar Level 1 → Level 2
```bash
# 1. Pare os containers do Level 1
cd monitoring-security-level1
docker-compose down

# 2. Clone Level 2
cd ..
git clone https://github.com/jlui70/monitoring-security-level2.git
cd monitoring-security-level2

# 3. Copie seus dados (opcional)
cp ../monitoring-security-level1/volumes/* ./volumes/

# 4. Configure .env
cp .env.example .env
# Edite .env com seus valores

# 5. Inicie Level 2
docker-compose up -d
```

### Migrar Level 2 → Level 3
Ver guia completo em: [Level 3 Migration Guide](https://github.com/jlui70/monitoring-security-level3/blob/main/docs/MIGRATION.md)

### Migrar Level 3 → Level 4
Ver guia completo em: [Level 4 Migration Guide](https://github.com/jlui70/monitoring-security-level4/blob/main/docs/MIGRATION.md)

---

## 🐛 Troubleshooting

### Problemas Comuns

**Q: Posso misturar níveis?**  
A: Não recomendado. Cada nível é uma implementação completa. Use um de cada vez.

**Q: Preciso passar por todos os níveis?**  
A: Não! Escolha o nível que atende suas necessidades. O Level 1 é bom para aprender, mas você pode pular para Level 3 ou 4 em produção.

**Q: Quanto tempo leva para implementar cada nível?**  
- Level 1: 15-30 minutos
- Level 2: 1-2 horas
- Level 3: 4-8 horas (setup inicial do Vault)
- Level 4: 2-4 horas (se já conhece AWS)
- Level 5: 1-2 dias (setup Kubernetes + integração)

**Q: Qual o custo real em produção?**  
- Levels 1-3: Apenas custo de infraestrutura (VMs)
- Level 4: $0.40/secret/mês + infraestrutura AWS
- Level 5: Cluster K8s (~$70-150/mês) + secrets

---

## 🤝 Contribuindo

Contribuições são muito bem-vindas! 🎉

### Como Contribuir

1. Escolha o **repositório do nível** que deseja contribuir
2. Faça um **fork** do repositório
3. Crie uma **branch** para sua feature (`git checkout -b feature/melhoria`)
4. **Commit** suas mudanças (`git commit -m 'feat: adiciona melhoria X'`)
5. **Push** para a branch (`git push origin feature/melhoria`)
6. Abra um **Pull Request**

### 📝 Guidelines

- Scripts devem ter tratamento de erros
- Documentação em português (PT-BR)
- Siga as melhores práticas de segurança
- Teste antes de submeter PR

### 🐛 Reportar Bugs

Encontrou um bug? Abra uma issue no repositório correspondente:

- [Issues Level 1](https://github.com/jlui70/monitoring-security-level1/issues)
- [Issues Level 2](https://github.com/jlui70/monitoring-security-level2/issues)
- [Issues Level 3](https://github.com/jlui70/monitoring-security-level3/issues)
- [Issues Level 4](https://github.com/jlui70/monitoring-security-level4/issues)

---

## 📄 Licença

- **Levels 1 e 2:** MIT License
- **Levels 3 e 4:** Veja LICENSE em cada repositório
- **Level 5:** TBD

---

## 🙏 Créditos e Agradecimentos

### 🌟 Tecnologias Utilizadas

Agradecimentos especiais às comunidades open-source:

- **Zabbix** - Enterprise monitoring solution
- **Grafana** - Beautiful metrics visualization
- **Prometheus** - Cloud-native monitoring
- **HashiCorp Vault** - Secrets management platform
- **AWS** - Cloud infrastructure
- **Kubernetes** - Container orchestration
- **Docker** - Containerization platform

### 💙 Comunidade

Este projeto foi criado para ajudar a comunidade brasileira de DevOps e Cloud a implementar segurança de forma progressiva e prática.

---

## 📞 Contato e Suporte

### 🌐 Conecte-se Comigo

- 📹 **YouTube:** [DevOps Project](https://www.youtube.com/@devops-project)
- 💼 **Portfólio:** [devopsproject.com.br](https://devopsproject.com.br/)
- 💻 **GitHub:** [@jlui70](https://github.com/jlui70)

### 💬 Precisa de Ajuda?

- 🐛 Abra uma issue no repositório correspondente
- 💡 Participe das discussões no YouTube
- 📧 Entre em contato via portfólio

### 🌟 Gostou do Projeto?

Se este projeto foi útil para você:

- ⭐ Dê uma **estrela** nos repositórios
- 🔄 **Compartilhe** com a comunidade
- 📹 **Inscreva-se** no canal do YouTube
- 🤝 **Contribua** com melhorias

---

<p align="center">
  <strong>Desenvolvido com ❤️ para a comunidade brasileira de DevOps, SRE e Cloud Engineering</strong>
</p>

<p align="center">
  <sub>Monitoring Security Evolution • 2024-2025 • Todos os direitos reservados</sub>
</p>

<p align="center">
  <sub>Última atualização: Novembro 2025</sub>
</p>
