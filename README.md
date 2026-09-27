# ⚡ Luis Carmo

<a href="https://luisfcarmo.github.io/portifolio/">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=2094F3&width=520&lines=Data+Platform+Engineer;Pipelines+de+dados+de+ponta+a+ponta;Airflow+%C2%B7+Spark+%C2%B7+Iceberg+%C2%B7+AWS" alt="Data Platform Engineer · Pipelines de dados de ponta a ponta" />
</a>

---

<table>
  <tr>
    <td width="56%" valign="top">

### 👨‍💻 Sobre Mim

Data Platform Engineer focado em **engenharia de dados**. Construo pipelines de ponta a ponta, da coleta ao consumo por APIs e agentes de IA, com toda a infraestrutura na AWS escrita como código.

- 🔭 Hoje em três frentes: **Positivo Tecnologia**, **DIIP · PROAD/UFG** e **Enel**
- 🎓 Ciência da Computação na **UFG** (formatura prevista para 2027)
- 📍 **Goiânia, GO** · remoto ou híbrido

<a href="https://luisfcarmo.github.io/portifolio/"><img src="https://img.shields.io/badge/Portf%C3%B3lio-2094F3?style=for-the-badge&logo=githubpages&logoColor=white" alt="Portfólio" /></a>
<a href="https://www.linkedin.com/in/luis-cesar-ferreira-do-carmo/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge" alt="LinkedIn" /></a>
<a href="mailto:luiscesar@discente.ufg.br"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>

</td>
<td width="44%" valign="middle">

```console
$ python main.py --env prod
✓ jobs orquestrados    90.000/dia
✓ airflow em produção  2+ anos
✓ autoted · ufg        em produção
✓ testes automatizados 680+
✓ lakehouse · iceberg  validated
● all systems operational
```

</td>
</tr>
</table>

---

## 🔀 Da fonte ao consumo

O fluxo que implemento nas plataformas em que trabalho, com as ferramentas de cada etapa:

```mermaid
flowchart TB
    subgraph SRC["Fontes"]
        direction TB
        s1["Portais públicos<br/>e e-commerce"]
        s2["Sistemas transacionais<br/>SIPAC · SEI · OLTP"]
        s3["Dados abertos<br/>ANEEL"]
    end

    subgraph ING["Ingestão"]
        direction TB
        i1["Crawlers<br/>Scrapy · Playwright"]
        i2["CDC<br/>Debezium · MSK"]
        i3["APIs e arquivos<br/>Gmail API · PDF · XLS"]
    end

    subgraph LAKE["Lakehouse · S3 + Apache Iceberg"]
        direction LR
        raw["Raw"] -->|"Glue · Spark"| silver["Silver"] -->|"Glue · Spark"| gold["Gold"]
    end

    subgraph OUT["Consumo"]
        direction TB
        o1["SQL<br/>Athena"]
        o2["APIs<br/>FastAPI · PostgreSQL"]
        o3["Agentes de IA<br/>Bedrock · Agno · MCP"]
    end

    ORQ{{"Orquestração<br/>Airflow · Prefect<br/>Step Functions"}}

    SRC --> ING --> LAKE --> OUT
    SRC ~~~ ORQ
    ORQ -.-> ING
    ORQ -.-> LAKE

    classDef bronze fill:#8C5A3C,stroke:#5E3B26,color:#FFFFFF
    classDef prata fill:#B8C0CC,stroke:#7D8794,color:#111111
    classDef ouro fill:#D9A93B,stroke:#9C7412,color:#111111
    class raw bronze
    class silver prata
    class gold ouro
```

**Como eu trabalho**

- **Infra 100% como código:** Terraform do bucket à fila, sem configuração manual em produção.
- **Falha visível, nunca silenciosa:** retries automáticos, alerta quando a ingestão para e registros divergentes isolados em quarentena.
- **Qualidade na entrada:** validação automática antes da carga e testes automatizados em cada etapa.
- **Auditável por padrão:** trilha imutável com hash chain SHA-256, RBAC e IAM de menor privilégio.

---

## 🏗️ Onde isso roda hoje

| | Plataforma | Destaque | Stack |
|:---|:---|:---|:---|
| **Positivo Tecnologia** | Plataforma de dados e IA: coleta em larga escala, data lake e agentes de IA | **+90k jobs/dia** sem intervenção humana | Airflow · Kubernetes/Argo · AWS Batch/Fargate · Glue · Athena · Bedrock |
| **DIIP · PROAD/UFG** | **AutoTED:** ingestão, conciliação orçamentária e auditoria dos TEDs da UFG | Em produção · **680+ testes** | Prefect · FastAPI · PostgreSQL · HTMX · Docker |
| **Enel** | Lakehouse Medallion para servir dados a agentes de IA (POC) | Raw → Silver → Gold em **Apache Iceberg** | Glue/Spark · Iceberg · Step Functions · Athena · Terraform |

---

## 🛠️ Tech Arsenal

**Engenharia de Dados & IA**

<p>
  <img src="https://img.shields.io/badge/Apache_Airflow-017CEE?style=flat-square&logo=apacheairflow&logoColor=white" alt="Apache Airflow" />
  <img src="https://img.shields.io/badge/Apache_Spark-E25A1C?style=flat-square&logo=apachespark&logoColor=white" alt="Apache Spark" />
  <img src="https://img.shields.io/badge/Apache_Iceberg-30363D?style=flat-square" alt="Apache Iceberg" />
  <img src="https://img.shields.io/badge/AWS_Glue_%26_Athena-232F3E?style=flat-square" alt="AWS Glue e Athena" />
  <img src="https://img.shields.io/badge/Step_Functions-232F3E?style=flat-square" alt="AWS Step Functions" />
  <img src="https://img.shields.io/badge/Prefect-070E10?style=flat-square&logo=prefect&logoColor=white" alt="Prefect" />
  <img src="https://img.shields.io/badge/Scrapy-60A839?style=flat-square&logo=scrapy&logoColor=white" alt="Scrapy" />
  <img src="https://img.shields.io/badge/AWS_Bedrock-232F3E?style=flat-square" alt="AWS Bedrock" />
  <img src="https://img.shields.io/badge/Agno_Agents-30363D?style=flat-square" alt="Agno Agents" />
  <img src="https://img.shields.io/badge/pgvector-336791?style=flat-square" alt="pgvector" />
</p>

| **Linguagens** | **Backend & Web** | **Cloud & DevOps** | **Bancos & Observabilidade** |
|:---:|:---:|:---:|:---:|
| <img src="https://skillicons.dev/icons?i=python,java,ts" alt="Python, Java, TypeScript" /> | <img src="https://skillicons.dev/icons?i=fastapi,django,spring,react&perline=2" alt="FastAPI, Django, Spring, React" /> | <img src="https://skillicons.dev/icons?i=aws,terraform,docker,kubernetes,githubactions,linux&perline=3" alt="AWS, Terraform, Docker, Kubernetes, GitHub Actions, Linux" /> | <img src="https://skillicons.dev/icons?i=postgres,mysql,grafana" alt="PostgreSQL, MySQL, Grafana" /> |

---

<div align="center">
  📂 Projetos e trajetória completa no <a href="https://luisfcarmo.github.io/portifolio/"><b>portfólio</b></a>
  <br/><br/>
  ✨ <i>"Code is like humor. When you have to explain it, it’s bad."</i> ✨
</div>
