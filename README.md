# Hændelseslog for Digitale Bankløsninger 🏦

> **Bachelorprojekt | Aarhus Universitet**  
> **Institut for Elektro- og Computerteknologi | Softwareteknologi**  
> **I samarbejde med Bankdata A/S**

![Status](https://img.shields.io/badge/Status-Forberedelse-orange)
![Cloud](https://img.shields.io/badge/Cloud-AWS%20%7C%20Azure-blue)
![Database](https://img.shields.io/badge/Database-PostgreSQL%20%7C%20CosmosDB-green)
![API](https://img.shields.io/badge/API-REST-red)

Dette repository indeholder forberedelse, teknisk eksperimentering (Proof-of-Concept) og dokumentation for bachelorprojektet **"Implementering af Hændelseslog for Digitale Bankløsninger"**.

## 👥 Projektteam

| Navn | Studienummer | Specialisering | Email | Rolle |
|------|-------------|---------------|-------|-------|
| Raman Haman | 202208079 | Software Teknologi | - | TBD |
| Hanad Osman Hashi Aden | 202204919 | Software Teknologi | - | TBD |

**Virksomhed**: Bankdata A/S  
**Virksomhedskontakt**: Ali Reza Dehdar (deh@bankdata.dk)

## 🎯 Projektbeskrivelse

### Overordnet Formål
Udvikle en **skalerbar, sikker og cloud-baseret hændelseslog** der gør det muligt at registrere, lagre og analysere kunders aktiviteter i Bankdatas digitale løsninger (mobilbank og netbank).

### Kritiske Krav & Udfordringer
- **Skalering**: Håndtere **3.000.000 hændelser dagligt** (1M+ kunder, 20% aktive dagligt)
- **Læsebelastning**: ~100.000 læsninger per dag
- **Dataopbevaring**: 1 år hot storage + arkivering til cold storage efter 1 år
- **GDPR-compliance**: Sikker sletning af kundedata på anmodning
- **Sikkerhed**: Enterprise-grade authentication og authorization
- **Performance**: Lav latency for API-kald og hurtig dataudtræk

### Projektomfang
1. **Cloud Infrastructure**: AWS vs. Azure analyse og implementation
2. **Database Design**: Skalerbar arkitektur for massive data volumes
3. **API Development**: REST API med GDPR-funktionalitet
4. **Stakeholder Workshop**: Kravafklaring med Jyske Bank og Sydbank
5. **MEP Integration**: Frontend interface i medarbejderportalen
6. **Security Architecture**: Sikkerhedsintegration med Bankdata systemer

## 📋 Forberedelsesfase - Mål & Strategi

### Hovedformål
- 🎯 **Risikominimering**: Afprøv kritiske teknologivalg før hovedprojekt
- 🏗️ **Arkitekturvalidering**: Test cloud platforms og database performance
- 📚 **Vidensbase**: Dokumenter alle learnings til hovedrapport
- ⚡ **Effektiv overgang**: Klar codebase og infrastructure ved projektstart

## 🚀 Proof-of-Concept (POC) Roadmap

### POC 1: Cloud Platform Evaluering 🌩️
**Timeline**: Uge 1-2  
**Mål**: Sammenlign AWS vs. Azure for projektets behov

**Aktiviteter**:
- [ ] **Cost Analysis**: Estimat for 3M events/dag over 1 år
- [ ] **Performance Testing**: API Gateway latency og throughput
- [ ] **Service Comparison**: Database services, storage options, security
- [ ] **Compliance Check**: GDPR-tools og audit capabilities
- [ ] **Integration Assessment**: Bankdata eksisterende infrastruktur

**Deliverables**:
- Komparativ analyse rapport
- Cost breakdown spreadsheet
- Performance benchmark resultater
- Anbefaling til Bankdata

### POC 2: Database Architecture & Performance 🗄️
**Timeline**: Uge 3-4  
**Mål**: Validere database valg og skalerings-strategi

**Aktiviteter**:
- [ ] **Database Comparison**: GraphQL vs. "PostgreSQL vs. CosmosDB vs. DynamoDB"
- [ ] **Schema Design**: Optimeret til 3M inserts/dag + query patterns
- [ ] **Load Testing**: Simuler daglig belastning og peak traffic
- [ ] **Partitioning Strategy**: Effektiv data partitionering
- [ ] **Cold Storage Migration**: Test arkivering til S3/Azure Blob

**Deliverables**:
- Database performance rapport
- Optimeret schema design
- Load testing resultater
- Migration scripts til cold storage

### POC 3: GDPR-Compliant Data Management 🔒
**Timeline**: Uge 5-6  
**Mål**: Implementer sikker og compliant data handling

**Aktiviteter**:
- [ ] **Data Retention Policy**: Automatisk arkivering efter 1 år
- [ ] **Customer Data Deletion**: GDPR "Right to be Forgotten" API
- [ ] **Audit Logging**: Track alle data access og modifications
- [ ] **Encryption**: Data-at-rest og data-in-transit
- [ ] **Anonymization**: Pseudonymisering af sensitive data

**Deliverables**:
- GDPR compliance documentation
- Deletion API implementation
- Security audit log system
- Data encryption implementation

### POC 4: Event Ingestion & API Development 📡
**Timeline**: Uge 7-8  
**Mål**: Høj-performance data ingestion og REST API

**Aktiviteter**:
- [ ] **Event Data Model**: Definér hændelsesstruktur og metadata
- [ ] **Batch Ingestion**: Optimal batch size for bulk inserts
- [ ] **REST API**: Complete CRUD operations med filtering
- [ ] **API Gateway**: Authentication, rate limiting, monitoring
- [ ] **Error Handling**: Robust fejlhåndtering og retry logic

**Deliverables**:
- Event data model specification
- High-performance ingestion service
- Complete REST API implementation
- API documentation (OpenAPI/Swagger)

### POC 5: MEP Portal Integration & Workshop 🤝
**Timeline**: Uge 9-10  
**Mål**: Frontend interface og stakeholder requirements

**Aktiviteter**:
- [ ] **Stakeholder Workshop**: Afhold workshop med Jyske Bank + Sydbank
- [ ] **Requirements Analysis**: Definér præcise datafelter og use cases
- [ ] **MEP UI Design**: Samarbejd med UX designer
- [ ] **Frontend Implementation**: Søge- og filtreringsinterface
- [ ] **User Testing**: Test med Bankdata medarbejdere

**Deliverables**:
- Workshop report og requirements specification
- MEP portal UI/UX design
- Frontend implementation
- User testing feedback

## 🛠️ Teknologi Stack

### Cloud Infrastructure
| AWS | Azure | Status |
|-----|-------|--------|
| RDS (PostgreSQL) | Azure Database for PostgreSQL | 🔄 Under evaluering |
| API Gateway | Azure API Management | 🔄 Under evaluering |
| S3 Glacier | Azure Blob Archive | 🔄 Under evaluering |
| CloudWatch | Azure Monitor | 🔄 Under evaluering |
| IAM | Azure AD | 🔄 Under evaluering |

### Software Stack
- **Backend**: Node.js (Express.js) eller Python (FastAPI)
- **Database**: PostgreSQL (hot) + Cold Storage (S3/Azure Blob)
- **API**: RESTful med OpenAPI documentation
- **Authentication**: JWT tokens + API Keys
- **Containerization**: Docker + Docker Compose
- **CI/CD**: GitHub Actions
- **Monitoring**: CloudWatch/Azure Monitor
- **Documentation**: LaTeX (Overleaf) + Markdown

## 📁 Repository Struktur

```
📂 Bachelor-Project-Preparation/
├── 📄 README.md                           # Dette dokument
├── 📂 docs/                               # Projektdokumentation
│   ├── 📄 project-charter.md             # Projektformål, scope, success kriterier
│   ├── 📄 stakeholder-requirements.md    # Workshop resultater og krav
│   ├── 📄 technology-analysis.md         # AWS vs Azure sammenligning
│   ├── 📄 architecture-decisions.md      # Arkitektur beslutninger og rationale
│   ├── 📂 meeting-notes/                 # Mødereferater
│   │   ├── 📄 weekly-standup-YYYY-MM-DD.md
│   │   └── 📄 bankdata-sync-YYYY-MM-DD.md
│   └── 📂 diagrams/                      # Arkitektur og systemdiagrammer
│       ├── 📄 system-architecture.png
│       ├── 📄 database-erd.png
│       └── 📄 api-flow-diagram.png
├── 📂 poc/                               # Proof-of-Concept implementeringer
│   ├── 📂 01-cloud-platform-analysis/   # AWS vs Azure evaluering
│   │   ├── 📂 aws-setup/
│   │   ├── 📂 azure-setup/
│   │   ├── 📄 cost-analysis.xlsx
│   │   └── 📄 performance-comparison.md
│   ├── 📂 02-database-architecture/      # Database design og performance
│   │   ├── 📂 postgresql-setup/
│   │   ├── 📂 cosmosdb-setup/
│   │   ├── 📄 schema-design.sql
│   │   ├── 📄 load-testing-results.md
│   │   └── 📂 migration-scripts/
│   ├── 📂 03-gdpr-compliance/           # GDPR implementering
│   │   ├── 📂 data-deletion-api/
│   │   ├── 📂 encryption-implementation/
│   │   ├── 📄 audit-logging.md
│   │   └── 📄 retention-policy.md
│   ├── 📂 04-api-development/           # REST API og event ingestion
│   │   ├── 📂 rest-api/
│   │   ├── 📂 event-ingestion/
│   │   ├── � api-documentation.yaml   # OpenAPI spec
│   │   └── 📂 authentication/
│   ├── 📂 05-mep-integration/           # MEP portal interface
│   │   ├── 📂 frontend-ui/
│   │   ├── 📂 ux-design/
│   │   └── 📄 user-testing-results.md
│   └── 📂 integration-tests/            # End-to-end tests
│       ├── 📂 load-testing/
│       └── 📂 security-testing/
├── 📂 scripts/                          # Utility scripts og automation
│   ├── 📂 deployment/                   # Deployment automation
│   │   ├── 📄 docker-compose.yml
│   │   ├── 📄 Dockerfile
│   │   └── 📂 kubernetes/
│   ├── 📂 monitoring/                   # Monitoring setup
│   │   ├── � cloudwatch-setup.py
│   │   └── 📄 azure-monitor-setup.py
│   ├── 📂 data-generation/              # Test data generation
│   │   ├── 📄 event-generator.py
│   │   └── 📄 load-simulator.py
│   └── 📂 utilities/                    # Diverse hjælpe-scripts
└── 📂 research/                         # Research og eksperimenter
    ├── 📂 banking-standards/            # Banking industri standarder
    ├── 📂 security-best-practices/      # Security research
    └── 📂 performance-benchmarks/       # Performance research
```

## 📊 Projektmilestones & Success Kriterier

### Forberedelsesfase Success Kriterier
#### 🎯 Tekniske Målsætninger
- [ ] **Cloud Platform**: Dokumenteret sammenligning med anbefaling til Bankdata
- [ ] **Database Performance**: Valideret arkitektur der kan håndtere 3M events/dag
- [ ] **GDPR Compliance**: Funktionel deletion API og audit system
- [ ] **API Performance**: REST API med <200ms response time
- [ ] **Security**: Enterprise-grade authentication implementeret

#### 📚 Dokumentations Målsætninger  
- [ ] **Arkitektur Dokumentation**: Complete system design dokumenteret
- [ ] **Performance Benchmarks**: Detaljeret performance analyse
- [ ] **Cost Analysis**: Detaljeret økonomisk analyse for Bankdata
- [ ] **Risk Assessment**: Identificerede risici og mitigation strategies
- [ ] **Best Practices**: Dokumenterede security og development standards

#### 🤝 Stakeholder Målsætninger
- [ ] **Requirements Workshop**: Gennemført med Jyske Bank og Sydbank
- [ ] **Bankdata Alignment**: Løbende alignment med Ali Reza Dehdar
- [ ] **MEP Integration Plan**: Klar integration strategi
- [ ] **Security Approval**: Sikkerhedsarkitektur godkendt af Bankdata

## 📅 Detaljeret Tidsplan

| Uge | Hovedfokus | Milestone | Deliverables |
|-----|------------|-----------|--------------|
| **1** | Project Setup + Cloud Analysis | POC 1 Start | Repository, AWS/Azure accounts |
| **2** | Cloud Platform Comparison | POC 1 Complete | Cloud platform anbefaling |
| **3** | Database Architecture Design | POC 2 Start | Schema design, performance plan |
| **4** | Database Load Testing | POC 2 Complete | Performance benchmarks |
| **5** | GDPR Implementation | POC 3 Start | Deletion API, encryption |
| **6** | Security & Compliance | POC 3 Complete | Security audit, compliance docs |
| **7** | API Development | POC 4 Start | REST API, event ingestion |
| **8** | API Testing & Documentation | POC 4 Complete | Complete API med docs |
| **9** | Stakeholder Workshop + MEP | POC 5 Start | Requirements workshop |
| **10** | Integration & Dokumentation | POC 5 Complete | MEP interface, final rapport |

## 🎓 Relation til Bachelorprojekt Læringsmål

### Teknisk Udvikling & Innovation
- **Omsætte forskningsresultater**: Cloud-native arkitektur baseret på industry best practices
- **Udvikle nye løsninger**: Skalerbar event logging system optimeret til banking
- **Systematisk metode**: Agile udvikling med POC-baseret risikoreduktion

### Analyse & Vurdering
- **Søge og analysere viden**: Dybdegående cloud platform og database sammenligning
- **Vurdere projektresultater**: Performance benchmarks og cost-benefit analyse

### Kommunikation & Refleksion
- **Forklare resultater**: Stakeholder workshops og teknisk dokumentation
- **Bæredygtighed & etik**: GDPR compliance og ansvarlig data håndtering
- **Organisatoriske konsekvenser**: Integration med eksisterende Bankdata infrastruktur

## � Development Workflow & Standards

### Git Workflow
- **Main Branch**: Production-ready code
- **Develop Branch**: Integration branch for features
- **Feature Branches**: `feature/poc-{number}-{description}`
- **Commit Messages**: Conventional commits format
- **Code Review**: Alle POC implementeringer peer-reviewed

### Dokumentations Standards
- **Meeting Notes**: Strukturerede referater med action items
- **Technical Docs**: Markdown med plantUML diagrammer
- **Code Documentation**: Inline comments + README per POC
- **Decision Log**: Architecture Decision Records (ADR) format

### Quality Assurance
- **Code Standards**: ESLint/Prettier for JavaScript, Black for Python
- **Testing**: Unit tests for alle API endpoints
- **Security**: OWASP guidelines for alle implementeringer
- **Performance**: Benchmark alle database queries og API calls

## 🚨 Risiko Management

### Identificerede Risici
| Risiko | Sandsynlighed | Impact | Mitigation Strategy |
|--------|---------------|---------|---------------------|
| **Cloud Platform Valg**: Forkert platform valg | Medium | Høj | Omfattende POC sammenligning |
| **Database Performance**: Ikke skalerbar til 3M events | Medium | Kritisk | Omfattende load testing i POC 2 |
| **GDPR Compliance**: Manglende compliance | Lav | Kritisk | Tidlig implementering i POC 3 |
| **Stakeholder Requirements**: Uklare krav | Høj | Medium | Struktureret workshop i POC 5 |
| **Bankdata Integration**: Integration challenges | Medium | Høj | Tæt samarbejde med Ali Reza |
| **Timeline Pressure**: Forsinket POC completion | Medium | Medium | Agile approach med prioritering |

## 📞 Kontakt & Kommunikation

### Projektteam
- **GitHub Repository**: https://github.com/Hanad08/Bachelor-Project-Preparation
- **Slack/Teams**: TBD
- **Ugentlige Sync**: Fredage 14:00-15:00

### Bankdata Kontakt
- **Primær Kontakt**: Ali Reza Dehdar (deh@bankdata.dk, 93848470)
- **Login/Security Team**: TBD via Ali Reza
- **UX Designer**: TBD for MEP integration

### Stakeholders
- **Jyske Bank**: Workshop deltager (TBD)
- **Sydbank**: Workshop deltager (TBD)

## 📚 Ressourcer & Referencer

### Banking Industry Standards
- **PCI DSS**: Payment Card Industry Data Security Standard
- **ISO 27001**: Information Security Management
- **PSD2**: Payment Services Directive (EU)

### Technical Documentation
- **AWS Well-Architected**: [aws.amazon.com/architecture/well-architected](https://aws.amazon.com/architecture/well-architected/)
- **Azure Architecture**: [docs.microsoft.com/azure/architecture](https://docs.microsoft.com/azure/architecture/)
- **GDPR Technical Guidelines**: [edpb.europa.eu](https://edpb.europa.eu)

### Development Resources
- **REST API Best Practices**: [restfulapi.net](https://restfulapi.net/)
- **Database Performance**: PostgreSQL/SQL Server performance guides
- **Banking Security**: OWASP Banking Standards

---

**📅 Sidste opdatering**: August 29, 2025  
**🏷️ Version**: 2.0  
**📊 Status**: 🚀 Aktiv forberedelse  
**🎯 Næste Milestone**: POC 1 - Cloud Platform Analysis (Uge 1-2)r-Project-Preparation

Dette repository indeholder forberedelse, dokumentation og proof-of-concept (POC) tests for vores bachelorprojekt ved Aarhus Universitet, Institut for Elektro- og Computerteknologi.

Formålet med denne forberedelsesfase er at:
- Afprøve og dokumentere valgte teknologier på forhånd.
- Etablere en solid og veldokumenteret udviklingspipeline.
- Undgå tekniske fremskyndninger under selve projektperioden.
- Skabe et arkiv af genanvendelige kodeeksempler og scripts.
