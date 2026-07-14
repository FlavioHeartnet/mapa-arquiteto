# 02 — Fase Programador Pleno / Sénior

Do marco **🏆 Programador Júnior** até **🏆 Programador Completo!**. O foco sai de "fazer funcionar" e vai para qualidade, design e escala.

### 10 · Bancos não relacionais (NoSQL)

> Quando o modelo relacional não é o ideal: documentos, chave-valor, grafos e busca.

NoSQL troca rigidez relacional por escala e flexibilidade. Cada tipo resolve um problema: documentos para dados semiestruturados, chave-valor para cache/sessão, grafos para relações, e search engines para busca textual. Entender o trade-off é papel do pleno/sênior.

- **Document Store → MongoDB** — Guarda documentos JSON/BSON flexíveis; ótimo para dados que variam de forma.
- **Key-Value Store** — Mapa gigante chave→valor (ex.: Redis). Rapidíssimo para cache e sessões.
- **Graph Database** — Modela nós e relações (ex.: Neo4j); ideal para redes sociais, recomendações.
- **Search Engine** — Indexação e busca textual (ex.: Elasticsearch); relevância, full-text, filtros.

---

### 11 · Clean Code Principles

> Código legível é código que a equipe consegue manter e evoluir sem medo.

Código é lido muito mais do que escrito. Clean Code é o conjunto de hábitos que tornam o código óbvio: nomes que revelam intenção, funções pequenas e coesas, poucos comentários (o código se explica) e consistência. Base para tudo que vem depois (SOLID, patterns).

- **A regra do escoteiro** — Deixe o código mais limpo do que encontrou — melhorias pequenas e contínuas.
- **Classes, métodos e arquivos pequenos** — Unidades pequenas são fáceis de entender, testar e reaproveitar.
- **Comente apenas o necessário** — Comentário bom explica o 'porquê', não o 'o quê'. Código claro dispensa a maioria.
- **Nomes significativos** — O nome deve revelar intenção; evite abreviações e nomes genéricos.
- **Formatação e estilo consistentes** — Padrão único (linter/formatter) reduz atrito de leitura no time.
- **Evite abstrações precipitadas** — Não generalize cedo demais; refatore quando o padrão realmente aparecer (relaciona-se a YAGNI).
- **Minimize a complexidade ciclomática** — Menos caminhos (ifs/loops aninhados) = menos bugs e testes mais simples.
- **Exceções > códigos de erro** — Exceções separam o fluxo feliz do tratamento de erro; código fica mais limpo.
- **Funções puras** — Mesma entrada → mesma saída, sem efeito colateral. Fáceis de testar e raciocinar.
- **Evite passar booleanos e nulos** — Booleano esconde intenção na assinatura; null gera NullPointer. Prefira tipos/objetos explícitos.

🎬 **Vídeos:**
  - [SOLID, Clean Code e Design Patterns: pare de buscar o código perfeito](https://www.youtube.com/watch?v=yZRd_EWUs1g)

---

### 12 · Princípios SOLID

> 5 princípios de design OO que reduzem acoplamento e facilitam manutenção e extensão.

SOLID é o alicerce do design orientado a objetos profissional. Cada letra ataca uma fonte de rigidez e acoplamento. Aplicados juntos, resultam em código que se estende sem quebrar e se testa com facilidade — pré-requisito para Design Patterns e boas arquiteturas.

- **S — Single Responsibility** — Uma classe deve ter só um motivo para mudar (uma responsabilidade). Reduz efeitos colaterais. [▶ vídeo](https://www.youtube.com/watch?v=EWHTE1dQM4U)
- **O — Open/Closed** — Aberto para extensão, fechado para modificação: adicione comportamento sem alterar o que já funciona (casa com Strategy). [▶ vídeo](https://www.youtube.com/watch?v=T6pF7BfAPIo)
- **L — Liskov Substitution** — Subtipos devem substituir seus tipos-base sem quebrar o comportamento esperado. [▶ vídeo](https://www.youtube.com/watch?v=f6-5ANuTkys)
- **I — Interface Segregation** — Muitas interfaces específicas > uma genérica; não force clientes a depender do que não usam. [▶ vídeo](https://www.youtube.com/watch?v=jHbI9ej5O1Y)
- **D — Dependency Inversion** — Dependa de abstrações, não de implementações; injete dependências (casa com Adapter). [▶ vídeo](https://www.youtube.com/watch?v=s8g32ePcPps)

🎬 **Vídeos:**
  - [SOLID: Responsabilidade Única](https://www.youtube.com/watch?v=EWHTE1dQM4U)
  - [Open/Closed + Strategy](https://www.youtube.com/watch?v=T6pF7BfAPIo)
  - [Liskov — o mais crítico](https://www.youtube.com/watch?v=f6-5ANuTkys)
  - [Interface Segregation](https://www.youtube.com/watch?v=jHbI9ej5O1Y)
  - [Inversão de Dependências + Adapter](https://www.youtube.com/watch?v=s8g32ePcPps)

---

### 13 · Object Calisthenics

> 9 regras 'de academia' que forçam bons hábitos de OO no dia a dia.

Object Calisthenics são restrições deliberadas que, quando praticadas, empurram seu código para orientação a objetos limpa: menos condicionais, mais objetos ricos, menos acoplamento. São exercícios — nem toda regra é lei absoluta, mas praticá-las muda seu estilo.

- **Apenas um nível de indentação por método** — Força métodos curtos e extração; combate aninhamento. [▶ vídeo](https://www.youtube.com/watch?v=pW9Bb4PteWU)
- **Nunca usar ELSE** — Use retorno antecipado, polimorfismo ou guard clauses. [▶ vídeo](https://www.youtube.com/watch?v=pW9Bb4PteWU)
- **Envolva todos os tipos primitivos** — Crie Value Objects (ex.: CPF, Dinheiro) em vez de String/int soltos. [▶ vídeo](https://www.youtube.com/watch?v=YGNH71KPIes)
- **Coleções de primeira classe** — Uma classe que só encapsula uma coleção concentra as regras dela.
- **Apenas um ponto por linha (Lei de Demeter)** — Não navegue a.b.c.d; fale só com vizinhos diretos. [▶ vídeo](https://www.youtube.com/watch?v=KXaPJhG9yCk)
- **Não abrevie** — Nomes completos; se o nome fica longo demais, a classe faz coisa demais.
- **Classes pequenas (máx. ~50 linhas)** — Força coesão e responsabilidade única. [▶ vídeo](https://www.youtube.com/watch?v=_OKbQKjiKR8)
- **Máx. 2 variáveis de instância** — Empurra para decompor a classe em objetos menores. [▶ vídeo](https://www.youtube.com/watch?v=_OKbQKjiKR8)
- **Sem getters/setters** — Diga ao objeto o que fazer (Tell, Don't Ask) em vez de expor estado. [▶ vídeo](https://www.youtube.com/watch?v=PXHqooNlkVM)

🎬 **Vídeos:**
  - [Lei de Demeter](https://www.youtube.com/watch?v=KXaPJhG9yCk)
  - [Pare de usar Getters/Setters](https://www.youtube.com/watch?v=PXHqooNlkVM)
  - [Armadilha dos tipos primitivos](https://www.youtube.com/watch?v=YGNH71KPIes)
  - [Coesão das classes](https://www.youtube.com/watch?v=_OKbQKjiKR8)
  - [Eliminar o ELSE](https://www.youtube.com/watch?v=pW9Bb4PteWU)

---

### 14 · Princípios de qualidade de Código

> Três lembretes que evitam over-engineering e duplicação.

DRY, KISS e YAGNI são heurísticas para manter o código enxuto: não repita conhecimento, não complique à toa e não construa o que ninguém pediu ainda. Contrabalançam a tentação de 'preparar para o futuro' cedo demais.

- **DRY — Don't Repeat Yourself** — Cada conhecimento tem uma única fonte da verdade; duplicação vira bug futuro.
- **KISS — Keep It Simple, Stupid** — A solução mais simples que funciona costuma ser a melhor.
- **YAGNI — You Ain't Gonna Need It** — Não implemente o que só 'talvez' será útil; adia complexidade até ela ser real. [▶ vídeo](https://www.youtube.com/watch?v=wjtfJ9c4KdM)

🎬 **Vídeos:**
  - [O maior erro dos programadores e como o YAGNI salva seu código](https://www.youtube.com/watch?v=wjtfJ9c4KdM)

---

### 15 · Pirâmide de Testes

> Muitos testes rápidos na base, poucos e caros no topo.

A pirâmide equilibra confiança e velocidade: a maioria dos testes é unitária (rápida, isolada), uma camada média de integração e poucos testes de ponta-a-ponta (lentos, frágeis). Inverter a pirâmide (muito E2E) deixa a suíte lenta e instável.

- **Testes unitários — 80%** — Testam uma unidade isolada (função/classe). Rápidos; a base da confiança.
- **Testes de integração — 15%** — Verificam módulos trabalhando juntos (ex.: serviço + banco).
- **Testes funcionais / E2E — 5%** — Simulam o usuário no sistema inteiro. Valiosos, mas lentos e frágeis — use com parcimônia.

---

### 16 · Design Patterns

> Soluções reutilizáveis para problemas recorrentes de design (catálogo GoF).

Design Patterns são vocabulário comum para soluções que já se provaram. Divididos em Criacionais (como criar objetos), Estruturais (como compô-los) e Comportamentais (como colaboram). Não são regras a decorar — são ferramentas para reconhecer e aplicar no problema certo.

**Criacionais**

- **Simple Factory** — Centraliza a criação de objetos numa fábrica. [▶ vídeo](https://www.youtube.com/watch?v=3-ESljj0jgI)
- **Factory Method** — Subclasses decidem qual objeto criar.
- **Abstract Factory** — Fábrica de famílias de objetos relacionados.
- **Builder** — Constrói objetos complexos passo a passo.
- **Singleton** — Uma única instância global — cuidado com testes e concorrência. [▶ vídeo](https://www.youtube.com/watch?v=E8ey3HjSthg)
- **Prototype** — Cria objetos clonando um protótipo.

**Estruturais**

- **Adapter** — Adapta uma interface incompatível a outra esperada. [▶ vídeo](https://www.youtube.com/watch?v=Fg1kEjaaBrs)
- **Decorator** — Adiciona comportamento dinamicamente, sem herança. [▶ vídeo](https://www.youtube.com/watch?v=7B60j9EGrrU)
- **Facade** — Interface simples para um subsistema complexo. [▶ vídeo](https://www.youtube.com/watch?v=4Aq9UHQ5f5Y)
- **Proxy** — Um substituto que controla acesso ao objeto real. [▶ vídeo](https://www.youtube.com/watch?v=el1MtIPXTqo)
- **Bridge** — Separa abstração de implementação para variarem juntas.
- **Composite** — Trata objetos e composições de forma uniforme (árvores).
- **Flyweight** — Compartilha objetos para economizar memória.

**Comportamentais**

- **Observer** — Notifica dependentes quando o estado muda (eventos). [▶ vídeo](https://www.youtube.com/watch?v=mv9JxI85Ac8)
- **Strategy** — Troca algoritmos em tempo de execução; casa com Open/Closed. [▶ vídeo](https://www.youtube.com/watch?v=DzlXwgsc_AU)
- **State** — Objeto muda de comportamento conforme seu estado interno. [▶ vídeo](https://www.youtube.com/watch?v=OrCgWzpNszk)
- **Template Method** — Define o esqueleto de um algoritmo, deixando passos para subclasses. [▶ vídeo](https://www.youtube.com/watch?v=j5fGTi8ObK4)
- **Chain of Responsibility** — Passa a requisição por uma cadeia de handlers.
- **Command** — Encapsula uma ação como objeto (undo, filas).
- **Iterator** — Percorre coleções sem expor a estrutura interna.
- **Mediator** — Centraliza a comunicação entre objetos.
- **Memento** — Salva e restaura estado (snapshots).
- **Visitor** — Adiciona operações a uma hierarquia sem alterá-la.

🎬 **Vídeos:**
  - [Simple Factory](https://www.youtube.com/watch?v=3-ESljj0jgI)
  - [Strategy](https://www.youtube.com/watch?v=DzlXwgsc_AU)
  - [Decorator](https://www.youtube.com/watch?v=7B60j9EGrrU)
  - [Observer](https://www.youtube.com/watch?v=mv9JxI85Ac8)
  - [Adapter](https://www.youtube.com/watch?v=Fg1kEjaaBrs)
  - [Facade](https://www.youtube.com/watch?v=4Aq9UHQ5f5Y)
  - [Proxy](https://www.youtube.com/watch?v=el1MtIPXTqo)
  - [State](https://www.youtube.com/watch?v=OrCgWzpNszk)
  - [Template Method](https://www.youtube.com/watch?v=j5fGTi8ObK4)
  - [Singleton](https://www.youtube.com/watch?v=E8ey3HjSthg)

---

### 17 · Técnicas de Refactoring

> Melhorar a estrutura interna do código sem mudar o comportamento externo.

Refatorar é pagar dívida técnica de forma segura: pequenos passos, com testes garantindo que nada quebrou. Reconhecer 'code smells' e aplicar refatorações conhecidas mantém o código saudável ao longo do tempo.

- **O que é débito técnico** — O custo futuro de atalhos tomados hoje; acumula juros se não for pago.
- **Code Smells** — Sinais de problema: métodos longos, classes grandes, duplicação, muitos parâmetros.
- **Métodos de Composição** — Extrair método, inline, extrair variável — reorganizar em unidades claras.
- **Organização de Dados** — Encapsular campos, substituir primitivos por objetos, mover comportamento junto dos dados.
- **Simplificar expressões condicionais** — Guard clauses, polimorfismo no lugar de switch, decompor condicionais.
- **Simplificar chamadas de métodos** — Renomear, reduzir parâmetros, introduzir objeto-parâmetro.

---

### 18 · Otimização e Performance

> Fazer o sistema responder rápido e aguentar carga sem desperdício.

Performance vem de medir antes de otimizar e de aplicar padrões conhecidos: cache para evitar trabalho repetido, assincronismo para não bloquear, e otimização de SQL onde o gargalo costuma estar. Concorrência e CDN completam o kit.

- **Cache-Aside Pattern** — A app consulta o cache; se não achar, busca no banco e popula o cache. Padrão de cache mais comum. [▶ vídeo](https://www.youtube.com/watch?v=vRO0UfvsbDw)
- **Jobs Assíncronos** — Tarefas pesadas saem do fluxo da requisição para filas/workers; a resposta fica rápida.
- **Concorrência e Paralelismo** — Concorrência = lidar com várias tarefas ao mesmo tempo; paralelismo = executá-las de fato ao mesmo tempo. [↗ ref](https://oxylabs.io/blog/concurrency-vs-parallelism)
- **Otimização de SQL** — Índices certos, evitar N+1, analisar plano de execução (EXPLAIN).
- **CDN** — Rede de servidores que serve conteúdo perto do usuário; reduz latência e carga na origem. [↗ ref](https://www.geeksforgeeks.org/what-is-content-delivery-networkcdn-in-system-design/)

🎬 **Vídeos:**
  - [CACHE-ASIDE: escalabilidade & performance](https://www.youtube.com/watch?v=vRO0UfvsbDw)

📎 **Aprofundamento:**
  - [Concurrency vs Parallelism — Oxylabs](https://oxylabs.io/blog/concurrency-vs-parallelism)
  - [Top 8 Cache Eviction Strategies — ByteByteGo](https://blog.bytebytego.com/)

---

### 19 · Básico das Cloud Providers

> Conhecer os serviços equivalentes de AWS, Azure e GCP.

Nuvem é onde os sistemas modernos rodam. Você não precisa dominar tudo, mas sim reconhecer o mapa: compute, storage, funções serverless, filas, bancos gerenciados e balanceadores — e como cada provedor nomeia o mesmo serviço. A tabela abaixo compara os 24 tipos de serviço mais comuns entre AWS, Azure e Google Cloud. A certificação AWS Cloud Practitioner é um bom ponto de partida.

| Tipo de Serviço | AWS | Azure | Google Cloud |
|---|---|---|---|
| Virtual Machines | Elastic Compute Cloud (EC2) | Virtual Machine | Compute Engine |
| Kubernetes Platform | Elastic Kubernetes Service (EKS) | Azure Kubernetes Service (AKS) | Google Kubernetes Engine (GKE) |
| Functions as a Service | Lambda | Azure Functions | Cloud Functions |
| Object Storage | Simple Storage Service (S3) | Blob Storage | Cloud Storage |
| Block Storage | Elastic Block Store (EBS) | Managed Disk | Persistent Disk |
| File Storage | Elastic File System (EFS) | File Storage | File Store |
| Networking | Virtual Private Cloud (VPC) | Virtual Network (VNet) | Virtual Private Cloud (VPC) |
| Domain Name System | Route 53 | Azure DNS | Cloud DNS |
| Load Balancing | Elastic Load Balancing (ELB) | Load Balancer | Cloud Load Balancing |
| Cloud Firewall | Web Application Firewall (WAF) | Web Application Firewall (WAF) | Cloud Armor |
| RDBMS | RDS | SQL Database | Cloud SQL |
| NoSQL | DynamoDB | Cosmos DB | Firebase Realtime Database |
| Data Warehouse | Redshift | Synapse Analytics | BigQuery |
| BigData | Elastic MapReduce (EMR) | HDInsight | Dataproc |
| Streaming Service | Kinesis | Streaming Analytics | Dataflow |
| AutoML | SageMaker | Machine Learning | Vertex AI |
| Data Catalog | Glue | Data Factory | Data Fusion |
| Event Driven System | EventBridge | Event Grid | Eventarc |
| Message Queue | Simple Queuing Service (SQS) | Storage Queues | Pub/Sub |
| Notification | Simple Notification Service (SNS) | Service Bus | Firebase Cloud Messaging |
| Monitoring | CloudWatch | Monitor | Cloud Monitoring |
| Infrastructure as Code | CloudFormation | Resource Manager | Deployment Manager |
| Identity Management | IAM | Active Directory | Cloud Identity |
| Key Encryption | KMS | Key Vault | Cloud KMS |

> 📷 Tabela original (imagem): [assets/cloud-services-aws-azure-gcp.png](assets/cloud-services-aws-azure-gcp.png)

📎 **Aprofundamento:**
  - [AWS Certified Cloud Practitioner](https://aws.amazon.com/certification/certified-cloud-practitioner/)
  - [Solutions Architect — Treinamento AWS](https://aws.amazon.com/training/)

---

### 20 · Pipelines de CI/CD

> Automatizar build, testes e deploy para entregar com segurança e frequência.

CI (Integração Contínua) roda build+testes a cada commit; CD (Entrega/Deploy Contínuo) leva o código validado ao ambiente automaticamente. Reduz erro humano, acelera feedback e é pré-requisito para zero-downtime e escala.

- **GitHub Actions** — Automação nativa do GitHub via workflows YAML. [↗ ref](https://docs.github.com/actions/quickstart)
- **GitLab CI** — Pipelines integrados ao GitLab (.gitlab-ci.yml).
- **Azure DevOps Pipelines** — CI/CD do ecossistema Microsoft.
- **Jenkins** — Servidor de automação clássico, extensível por plugins.

📎 **Aprofundamento:**
  - [What is CI/CD? — GeeksforGeeks](https://www.geeksforgeeks.org/what-is-ci-cd/)
  - [Quickstart GitHub Actions — Docs](https://docs.github.com/actions/quickstart)


---
🏆 Ao concluir → **Programador Completo!** → ➡️ [03 — Fase Arquiteto](03-fase-arquiteto.md)
