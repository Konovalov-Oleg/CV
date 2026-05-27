<h1 align="center">Oleg Konovalov</h1>

<p align="center">
  <strong>Java Software Engineer · 8+ years experience</strong><br>
  Dubai · Open to tech-lead and staff roles · Available for relocation
</p>
https://www.linkedin.com/in/konovalov-oleg-java/
<p align="center">
  <a href="mailto:oledjan2014@gmail.com">Email</a> ·
  <a href="https://www.linkedin.com/in/konovalov-oleg-java/">LinkedIn</a> ·
  <a href="https://github.com/Konovalov-Oleg">GitHub</a> ·
  <a href="https://t.me/oleg_kon0valov">Telegram</a>
</p>

---

## About

Java Software Engineer with **8+ years** of commercial experience in banking and fintech. Took three large products from scratch to production, designing distributed architectures for high-throughput payment flows (up to **100M transactions/day**) on Spring/Kafka/Kubernetes. Hands-on experience decommissioning monoliths and integrating with legacy systems over SOAP, IBM MQ and ActiveMQ. Currently focused on AML/CFT compliance services - fuzzy name matching, sanctions screening, observability-driven calibration. Regularly conduct technical interviews and lead code reviews.

## Tech Stack

![Java](https://img.shields.io/badge/-Java-007396?style=flat&logo=openjdk&logoColor=white)
![Kotlin](https://img.shields.io/badge/-Kotlin-7F52FF?style=flat&logo=kotlin&logoColor=white)
![Spring](https://img.shields.io/badge/-Spring-6DB33F?style=flat&logo=spring&logoColor=white)
![Hibernate](https://img.shields.io/badge/-Hibernate-59666C?style=flat&logo=hibernate&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![Oracle](https://img.shields.io/badge/-Oracle-F80000?style=flat&logo=oracle&logoColor=white)
![Redis](https://img.shields.io/badge/-Redis-DC382D?style=flat&logo=redis&logoColor=white)
![ClickHouse](https://img.shields.io/badge/-ClickHouse-FFCC01?style=flat&logo=clickhouse&logoColor=black)
![Kafka](https://img.shields.io/badge/-Kafka-231F20?style=flat&logo=apachekafka&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/-RabbitMQ-FF6600?style=flat&logo=rabbitmq&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white)
![Prometheus](https://img.shields.io/badge/-Prometheus-E6522C?style=flat&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/-Grafana-F46800?style=flat&logo=grafana&logoColor=white)
![GitLab](https://img.shields.io/badge/-GitLab-FC6D26?style=flat&logo=gitlab&logoColor=white)

**Backend** - Java 17/21, Kotlin, Spring (Boot, Web, Security, Data JPA/Hibernate, Cloud, Integration, Cache), jOOQ, Apache POI, JAXB

**Storage & Messaging** - PostgreSQL, Oracle, Redis, ClickHouse, S3/MinIO, Apache Kafka, RabbitMQ, ActiveMQ/Artemis, IBM MQ

**Integration & Auth** - REST, SOAP, gRPC, Keycloak, Kerberos

**Infra & Observability** - Docker/Podman, Kubernetes, HashiCorp Vault, Liquibase, Flyway, Gradle, Maven, GitLab CI/CD, Jenkins, Prometheus, Grafana, OpenTelemetry, Sentry, ELK, Zabbix

**Testing** - JUnit 5, Mockito, Testcontainers, RestAssured, WireMock

## Experience

### [Uzum Bank](https://uzumbank.uz/en)
*09/2024 – Present · 1.8 years*

- Designed and own a screening service that checks individuals against sanctions lists, PEP databases and internal watchlists across all payment flows - card transactions, P2P, cross-border transfers, consumer lending and merchant onboarding
- Built and calibrated a fuzzy name-matching engine: Cyrillic → Latin transliteration with Unicode normalisation, token-level Levenshtein/Jaro-Winkler comparison, and a greedy weighted-pairing algorithm; thresholds tuned with compliance officers on labeled data
- Reduced API p95 latency **from 100ms to 40ms** on a watchlist of hundreds of thousands of records - moved the dataset to Redis (removed Postgres from the hot path) and added a custom 3-character prefix index over normalised names, so expensive Levenshtein runs against a few hundred candidates per request instead of the full list
- Migrated the service from VMs to Kubernetes, raising availability **from 99.95% to 99.99%**
- Added Prometheus histograms over the matcher's similarity scores; the score distribution acts as a regression detector - code changes, normalisation tweaks or input-quality drift shift the distribution and trigger Grafana alerts before compliance officers see false positives
- Conduct technical interviews

**Stack:** Java 17/21, Spring (Boot, Web, Security, Data JPA/Hibernate, Cache, Cloud), PostgreSQL, JDBC, Redis, Kafka, HashiCorp Vault, Docker, Kubernetes, Liquibase, JUnit 5, Mockito, Testcontainers, RestAssured, Prometheus, Grafana, OpenTelemetry, Sentry, Gradle, GitLab CI/CD

### [Raiffeisen Bank](https://www.raiffeisen.ru/en/)
*08/2020 – 09/2024 · 4.2 years*

- Built and led development of services that request, validate and convert official document extracts into XML/PDF; a **~100M-transactions-per-day** flow. The platform processes requests from regulators and bank clients
- Designed the architecture for the overall platform and for individual microservices during the decommissioning of a legacy monolith
- Built shared platform components - for example, a Spring Boot starter for Testcontainers used by several teams
- Wrote several CI/CD pipelines from scratch; set up application metrics in Prometheus, dashboards in Grafana and distributed tracing
- Implemented integrations over SOAP, REST (Keycloak, Kerberos), Kafka, ActiveMQ/Artemis, RabbitMQ and IBM MQ
- Shipped the React UI for the new application
- Code-reviewed four developers
- Conducted technical interviews
- Supported the legacy monolith in parallel with the migration

**Stack:** Java 11/17, Kotlin, Spring (Boot, Web, Cloud, Security, Integration, Data JPA/Hibernate), PostgreSQL, ClickHouse, Redis, Kafka, ActiveMQ/Artemis, RabbitMQ, IBM MQ, REST, SOAP, Docker/Podman, Kubernetes, Apache POI, JAXB, S3 (MinIO), JUnit, Mockito, Testcontainers, WireMock, Gradle, Flyway, React, Prometheus, Grafana, ELK, Zabbix

### [Kaspi Bank](https://ir.kaspi.kz)
*10/2017 – 08/2020 · 2.9 years*

- Built classical and agency factoring products from scratch; embedded new business-process logic into the existing lending flow
- Implemented a backend data collection and audit pipeline feeding the DWH for BI analytics
- Optimised the sellers API, cutting response time **by 60%** and significantly improving the application-submission flow
- Created and rolled out an in-house transactional outbox library - removed boilerplate, sped up delivery and cut production incidents **by 30%**
- Added form autocomplete and validation: address suggestions via Google Places (Place Autocomplete) and counterparty lookup by BIN/IIN via Kompra API - reduced submission errors **by 80%**

**Stack:** Java 8/11, Spring (Boot, Cloud, Security, Web), Kafka, ActiveMQ, Oracle DB, jOOQ, Sentry, Grafana, ELK, Docker, Testcontainers, WireMock, JUnit, Mockito, Jira, Confluence, Jenkins

## Education

**Kuban State Agrarian University** (named after I.T. Trubilin), Krasnodar
Master's degree, 2015–2020 · Faculty of Mechanisation, Ground Transport Systems

## Additional

- Interview and onboard backend engineers regularly
- Comfortable building frontend (React) when end-to-end feature delivery requires it
- Familiar with Kotlin and can use it as a primary backend language
- Open to tech-lead and staff roles, available for relocation
