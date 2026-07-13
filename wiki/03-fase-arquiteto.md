# 03 — Fase Arquiteto ⭐ (foco)

Do marco **🏆 Programador Completo! → Arquiteto de Software** até a linha de chegada **🎽 Parabéns!**. A metade sênior do mapa: desenho de sistemas, DDD, estilos arquiteturais e Requisitos Não Funcionais (NFRs).

### 21 · Arquitetura de Software

> As decisões estruturais de alto impacto e difícil reversão de um sistema.

Arquitetura é o conjunto de decisões que moldam o sistema e são caras de mudar depois: divisão em componentes, comunicação, dados e atributos de qualidade. O arquiteto atua em níveis diferentes (aplicação, solução, corporativo) e o papel é mais sobre trade-offs e comunicação do que sobre código.

**Níveis de Arquitetura**

- **Arquitetura de Aplicação** — Estrutura interna de um único sistema (camadas, módulos, padrões).
- **Arquitetura de Solução** — Como vários sistemas se combinam para resolver um problema de negócio.
- **Arquitetura Corporativa** — Padrões, governança e estratégia de TI no nível de toda a organização.

**Tipos de Arquiteto**

- **Arquiteto de Software | LLD** — Low-Level Design: detalhe técnico dentro da aplicação.
- **Arquiteto de Soluções | HLD** — High-Level Design: desenho de alto nível e integração de sistemas.
- **Arquiteto Corporativo** — Estratégia e padrões no nível da empresa.

**Papéis**

- **Papéis e Responsabilidades** — Definir padrões, orientar times, decidir trade-offs, garantir os NFRs.
- **Comunicação & documentação** — Arquitetura precisa ser comunicada: diagramas (C4), ADRs, decisões registradas.

📎 **Aprofundamento:**
  - [Fundamentos da Arquitetura de Software (livro)](https://www.oreilly.com/library/view/fundamentals-of-software/9781492043447/)

---

### 22 · Domain Driven Design (DDD)

> Modelar o software a partir do domínio do negócio, alinhando código e linguagem do especialista.

DDD ataca a complexidade de negócio colocando o domínio no centro. A modelagem estratégica define fronteiras (Bounded Contexts) e uma linguagem comum (Ubiquitous Language); a tática dá os blocos para implementar cada contexto. É a ponte entre negócio e código — e base para decidir onde microsserviços fazem sentido.

**Modelagem Estratégica**

- **Subdomínios (core/support/generic)** — Separe o que é diferencial de negócio (core) do que é apoio ou genérico.
- **Bounded Contexts** — Fronteira onde um modelo e sua linguagem são consistentes; evita 'modelo único' impossível.
- **Ubiquitous Language** — Uma linguagem comum entre devs e especialistas, refletida no código.
- **Context Mapping** — Como os contextos se relacionam (parceria, cliente-fornecedor, anticorrupção).

**Modelagem Tática**

- **Entidades** — Objetos com identidade própria que persiste ao longo do tempo.
- **Value Objects** — Objetos definidos pelo valor (ex.: Dinheiro, CPF), imutáveis e sem identidade.
- **Aggregates** — Cluster de objetos tratado como uma unidade de consistência, com uma raiz.
- **Repositórios** — Abstraem a persistência dos agregados como se fossem coleções.
- **Domain Services** — Regras de negócio que não pertencem a uma entidade específica.
- **Domain Events** — Fatos relevantes do domínio ('PedidoConfirmado') que disparam reações.

🎬 **Vídeos:**
  - [Microsserviços: a maior armadilha (e o que DDD tem a ver)](https://www.youtube.com/watch?v=JXeJUfBCg4U)

📎 **Aprofundamento:**
  - [EventStorming (modelagem colaborativa)](https://www.eventstorming.com/)
  - [Domain-Driven Design — Eric Evans (livro)](https://www.domainlanguage.com/ddd/)

---

### 23 · Estilos Arquiteturais

> A evolução da estrutura: de camadas ao serverless, cada estilo com seus trade-offs.

Não existe arquitetura 'melhor' — existe a adequada ao contexto. A sequência costuma ir do simples (camadas, monólito modular) ao distribuído (microsserviços, eventos, serverless) conforme a necessidade de escala e autonomia cresce. Migrar cedo demais para microsserviços é um erro clássico.

- **Arquitetura em Camadas** — Separação em apresentação, aplicação, domínio e infraestrutura. Ponto de partida clássico. [▶ vídeo](https://www.youtube.com/watch?v=s8g32ePcPps)
- **Monólito modular** — Um único deploy, mas internamente modular e bem isolado. Muitas vezes a melhor escolha antes de distribuir.
- **Microsserviços** — Serviços independentes, com deploy e dados próprios. Ganha autonomia/escala ao custo de complexidade distribuída. [▶ vídeo](https://www.youtube.com/watch?v=JXeJUfBCg4U)
- **Orientada a Eventos (EDA)** — Componentes se comunicam por eventos assíncronos; alto desacoplamento e resiliência.
- **Serverless** — Execução sob demanda (FaaS), escala automática e cobrança por uso; sem gerenciar servidores. [↗ ref](https://www.datadoghq.com/knowledge-center/serverless-architecture/)
- **Peer-to-Peer (P2P)** — Nós atuam como cliente e servidor; sem ponto central. [↗ ref](https://www.geeksforgeeks.org/peer-to-peer-p2p-architecture/)

🎬 **Vídeos:**
  - [Microsserviços: a maior armadilha da arquitetura moderna](https://www.youtube.com/watch?v=JXeJUfBCg4U)

📎 **Aprofundamento:**
  - [Serverless Architecture — Datadog](https://www.datadoghq.com/knowledge-center/serverless-architecture/)
  - [Peer-to-Peer Architecture — GeeksforGeeks](https://www.geeksforgeeks.org/peer-to-peer-p2p-architecture/)
  - [Criando Microsserviços — Sam Newman (livro)](https://www.oreilly.com/library/view/building-microservices-2nd/9781492034018/)

---

### 24 · Requisitos Não Funcionais (NFRs)

> Os atributos de qualidade — o COMO do sistema. O núcleo do trabalho do arquiteto.

Enquanto requisitos funcionais dizem O QUE o sistema faz, os NFRs dizem QUÃO BEM: rápido, disponível, consistente, seguro, escalável. É aqui que arquitetura se prova. Cada grupo abaixo é um eixo de decisão com trade-offs (ex.: consistência vs disponibilidade, custo vs performance).

**Planejamento de Capacidade**

- **Latência vs Throughput** — Latência = tempo de uma requisição; throughput = quantas por segundo. Otimizar um pode custar o outro. [↗ ref](https://aws.amazon.com/compare/the-difference-between-throughput-and-latency/)
- **Carga (RPS)** — Requests Per Second esperados; base para dimensionar recursos.
- **Concorrência simultânea** — Quantas requisições coexistem; afeta pools, threads e conexões.
- **Utilização e saturação** — Quão perto do limite os recursos estão; saturação vira fila e lentidão.
- **Taxa de erros** — % de falhas sob carga; indicador-chave de saúde (SLO/SLA).

**Escalabilidade e Performance**

- **Vertical vs Horizontal Scaling** — Vertical = máquina maior (limite físico); Horizontal = mais máquinas (escala real, exige statelessness).
- **Elasticidade (Auto Scaling)** — Aumentar/reduzir instâncias automaticamente conforme a demanda.
- **Load Balancing** — Distribui tráfego entre instâncias; essencial para escala horizontal.
- **Bottlenecks** — O recurso mais lento limita o todo; encontre e ataque o gargalo real.

**Banco de dados & estratégia de leitura**

- **Database Replication** — Réplicas de leitura aliviam o primário e aumentam disponibilidade.
- **CQRS** — Separa modelos de escrita e leitura; otimiza cada caminho independentemente.
- **Estratégias de Cache** — Cache-aside, write-through, TTL, invalidação; e políticas de eviction (LRU, LFU). [↗ ref](https://blog.bytebytego.com/)
- **Database Sharding** — Particiona os dados entre bancos por uma chave; escala escrita além de um só nó. [↗ ref](https://aws.amazon.com/what-is/database-sharding/)

**Redução de carga e latência**

- **Assincronicidade / Filas de Mensageria** — Desacopla produtor e consumidor; absorve picos e melhora resiliência.
- **CDN** — Serve conteúdo estático perto do usuário; corta latência e carga na origem. [↗ ref](https://www.geeksforgeeks.org/what-is-content-delivery-networkcdn-in-system-design/)

**Performance Anti-Patterns (evitar)**

- **Busy Database** — Colocar lógica/carga demais no banco, tornando-o o gargalo.
- **Instanciação Imprópria** — Criar objetos caros repetidamente (conexões, clients) em vez de reusar.
- **Persistência Monolítica** — Forçar tudo num único banco quando cargas exigiam soluções diferentes.
- **Noisy Neighbor** — Um tenant/serviço consome recursos e degrada os vizinhos.
- **Retry Storm** — Retentativas em cascata amplificam a falha; use backoff + circuit breaker.
- **No Caching** — Recalcular/rebuscar o que poderia ser cacheado; desperdício óbvio.

**Consistência de Dados**

- **Tipos de Consistência** — Forte (sempre atualizado) vs eventual (converge com o tempo). Trade-off com disponibilidade/latência.
- **Teorema CAP** — Sob partição de rede, escolha entre Consistência e Disponibilidade — não dá para ter tudo.
- **Idempotência** — A mesma operação repetida não muda o resultado; essencial com retries e filas.
- **ACID vs BASE** — ACID (relacional, forte) vs BASE (disponível, consistência eventual — típico NoSQL).

**Disponibilidade / Resiliência / Tolerância a falhas**

- **Redundância** — Duplicar componentes para eliminar ponto único de falha (SPOF). [↗ ref](https://www.geeksforgeeks.org/what-is-high-availability-in-system-design/)
- **Failover** — Trocar automaticamente para uma réplica saudável quando algo cai. [↗ ref](https://www.geeksforgeeks.org/failover-mechanisms-in-system-design/)
- **Zero Downtime Deployment** — Blue-green, canary, rolling — atualizar sem derrubar o serviço. [↗ ref](https://www.geeksforgeeks.org/zero-downtime-deployments-in-distributed-systems/)
- **Graceful Degradation** — Degradar funcionalidade parcial em vez de cair por completo.
- **Chaos Engineering** — Injetar falhas de propósito para provar a resiliência (ex.: Chaos Monkey).
- **Tracing e Monitoramento** — Métricas, logs e traces distribuídos; observabilidade para achar e prever falhas.

**Segurança como Requisito Arquitetural**

- **VPN** — Túnel cifrado para acesso privado a recursos internos.
- **WAF** — Web Application Firewall filtra ataques na camada de aplicação.
- **DDoS** — Ataques de negação por volume; mitigação com CDN/scrubbing/rate limiting.
- **SQL Injection** — Injeção via input mal tratado; previna com queries parametrizadas. [↗ ref](https://owasp.org/www-project-top-ten/)
- **Criptografia de dados** — Em trânsito (TLS) e em repouso; proteja dados sensíveis por padrão.

🎬 **Vídeos:**
  - [Escalando uma arquitetura do zero a 1 milhão de usuários](https://www.youtube.com/watch?v=9g7twJrXqoY)
  - [CACHE-ASIDE: escalabilidade, performance e arquitetura](https://www.youtube.com/watch?v=vRO0UfvsbDw)

📎 **Aprofundamento:**
  - [System Design — Performance, Capacidade e Escalabilidade (fidelissauro.dev)](https://fidelissauro.dev/)
  - [What is Sharding? — AWS](https://aws.amazon.com/what-is/database-sharding/)
  - [High Availability — GeeksforGeeks](https://www.geeksforgeeks.org/what-is-high-availability-in-system-design/)
  - [Failover Mechanisms — GeeksforGeeks](https://www.geeksforgeeks.org/failover-mechanisms-in-system-design/)
  - [Zero Downtime Deployments — GeeksforGeeks](https://www.geeksforgeeks.org/zero-downtime-deployments-in-distributed-systems/)
  - [Throughput vs Latency — AWS](https://aws.amazon.com/compare/the-difference-between-throughput-and-latency/)

---

### 25 · Sistemas distribuídos & Padrões Arquiteturais

> Os padrões que atravessam tudo quando o sistema deixa de caber numa máquina.

Sistemas distribuídos trazem problemas próprios: rede não confiável, consistência parcial, falhas parciais. Os padrões abaixo são o repertório para lidar com isso — vários aparecem nos NFRs, aqui reunidos como ferramentas de arquitetura distribuída.

- **Replicação** — Cópias dos dados em vários nós para leitura e tolerância a falhas.
- **Particionamento (Sharding)** — Dividir dados/carga entre nós para escalar escrita.
- **Consenso** — Nós concordam sobre um valor apesar de falhas (Raft, Paxos).
- **Sagas** — Transações distribuídas por passos compensáveis, sem lock global.
- **Circuit Breaker** — Interrompe chamadas a um serviço que está falhando; evita cascata.
- **Observabilidade** — Métricas + logs + traces para entender o comportamento do sistema distribuído.

🎬 **Vídeos:**
  - [Escalando do zero a 1 milhão de usuários](https://www.youtube.com/watch?v=9g7twJrXqoY)

📎 **Aprofundamento:**
  - [Designing Data-Intensive Applications — Kleppmann (livro)](https://dataintensive.net/)
  - [The System Design Newsletter — Neo Kim](https://newsletter.systemdesign.one/)

---

### 26 · Certificação & System Design

> Validar o conhecimento e treinar entrevistas de arquitetura/system design.

Fechar o mapa é consolidar: certificações AWS Solutions Architect provam conhecimento de nuvem, e a prática de System Design (desenhar sistemas sob restrições) é o formato de entrevista sênior. Estudar casos reais (ByteByteGo, blogs de engenharia) acelera muito.

- **AWS Solutions Architect — Associate** — Certificação de entrada para arquitetura de soluções na AWS. [↗ ref](https://aws.amazon.com/certification/certified-solutions-architect-associate/)
- **AWS Solutions Architect — Professional** — Nível avançado; cenários complexos e multi-conta. [↗ ref](https://aws.amazon.com/certification/certified-solutions-architect-professional/)
- **System Design Interview Prep** — Praticar o desenho de sistemas sob restrições (escala, consistência, custo). [↗ ref](https://bytebytego.com/)

📎 **Aprofundamento:**
  - [ByteByteGo — Technical Interview Prep](https://bytebytego.com/)
  - [System Design Interview Vol. 1 e 2 — Alex Xu](https://blog.bytebytego.com/)


---
🎽 **PARABÉNS!** — linha de chegada. Veja também: [Livros](04-livros.md) · [Vídeos](05-videos.md) · [Conteúdos](06-conteudos-e-referencias.md) · [Treinamentos & Artigos](07-treinamentos-e-artigos.md)
