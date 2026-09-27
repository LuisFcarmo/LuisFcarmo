# Luis Carmo

<a href="https://luisfcarmo.github.io/portifolio/">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=2094F3&width=520&lines=Data+Platform+Engineer;Pipelines+de+dados+de+ponta+a+ponta;Airflow+%C2%B7+Spark+%C2%B7+Iceberg+%C2%B7+AWS" alt="Data Platform Engineer · Pipelines de dados de ponta a ponta" />
</a>

Data Platform Engineer focado em engenharia de dados. Construo pipelines de ponta a ponta, da coleta ao consumo por APIs e agentes de IA, com a infraestrutura na AWS escrita como código.

Hoje na Positivo Tecnologia, na DIIP/UFG e na Enel. Estudante de Ciência da Computação na UFG, em Goiânia.

[Portfólio](https://luisfcarmo.github.io/portifolio/) · [LinkedIn](https://www.linkedin.com/in/luis-cesar-ferreira-do-carmo/) · [Email](mailto:luiscesar@discente.ufg.br)

## Da fonte ao consumo

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

## Onde isso roda hoje

| Onde | O que é | Stack |
|:---|:---|:---|
| Positivo Tecnologia | Plataforma de dados e IA com mais de 90 mil jobs por dia no Airflow | Airflow, Kubernetes/Argo, AWS Batch, Glue, Athena, Bedrock |
| DIIP · PROAD/UFG | AutoTED, sistema em produção de ingestão e conciliação orçamentária da UFG | Prefect, FastAPI, PostgreSQL, Docker |
| Enel | POC de Lakehouse Medallion para servir dados a agentes de IA | Glue/Spark, Iceberg, Step Functions, Terraform |

## Stack

| Linguagens | Backend | Cloud & DevOps | Dados & Observabilidade |
|:---:|:---:|:---:|:---:|
| <img src="https://skillicons.dev/icons?i=python,java,ts" alt="Python, Java, TypeScript" /> | <img src="https://skillicons.dev/icons?i=fastapi,django,spring,react&perline=2" alt="FastAPI, Django, Spring, React" /> | <img src="https://skillicons.dev/icons?i=aws,terraform,docker,kubernetes,githubactions,linux&perline=3" alt="AWS, Terraform, Docker, Kubernetes, GitHub Actions, Linux" /> | <img src="https://skillicons.dev/icons?i=postgres,mysql,grafana" alt="PostgreSQL, MySQL, Grafana" /> |

<p align="center"><i>"Code is like humor. When you have to explain it, it’s bad."</i></p>
