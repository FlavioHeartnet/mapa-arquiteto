# 01 — Fase Programador Júnior

Da **Largada** ao marco **🏆 Programador Júnior**. É a base: como o computador funciona, uma linguagem, banco relacional, Git, redes/web, APIs, MVC e Docker. Cada tópico traz explicação, vídeos e links para aprofundar.

### 01 · Fundamentos

> Entender o que acontece 'embaixo do capô' antes de escrever código de verdade.

Programar bem exige um modelo mental de como a máquina executa seu código. CPU, memória e sistema operacional definem o que é rápido, o que é caro e por que bugs acontecem. Sem essa base, você decora sintaxe sem entender causas.

- **Como funciona um computador** — CPU busca-decodifica-executa instruções; memória (RAM) guarda dados voláteis; disco persiste. Tudo vira código de máquina no fim.
- **Como os programas rodam na memória** — Um processo tem stack (chamadas/variáveis locais) e heap (alocação dinâmica). Vazamentos, stack overflow e ponteiros nascem daqui.
- **Como os processadores funcionam** — Clock, núcleos, cache L1/L2/L3 e pipeline. Acesso a cache é ordens de grandeza mais rápido que RAM — daí a importância de localidade de dados.
- **Sistemas Operacionais** — Gerencia processos, threads, memória virtual, escalonamento e I/O. É o intermediário entre seu programa e o hardware.
- **Compilada vs interpretada** — Compilada (C, Go, Rust) vira binário antes de rodar → rápida. Interpretada (Python, JS) executa em runtime → flexível. JIT (Java, C#) fica no meio.
- **Linux (Ubuntu ou Debian)** — O SO da maioria dos servidores. Aprenda terminal, permissões, processos e pacotes — você vai operar em Linux a carreira inteira.

🎬 **Vídeos:**
  - [Hardware — CS50 Understanding Technology](https://www.youtube.com/watch?v=6mbFO0ZLMW8)
  - [Curso de Linux — Primeiros Passos](https://www.youtube.com/watch?v=6nN2EglOqCM)

📎 **Aprofundamento:**
  - [CS50 — Introduction to Computer Science](https://cs50.harvard.edu/x/2025/)
  - [Linux Command Cheat Sheet (100 comandos)](https://www.geeksforgeeks.org/linux-commands-cheat-sheet/)

---

### 02 · Escolha uma linguagem

> Uma linguagem é ferramenta; o que transfere entre elas é lógica, algoritmos e paradigmas.

Escolha uma linguagem e vá fundo — dominar uma bem ensina conceitos que se repetem em todas. Opções: C#, Python, JavaScript, Java, PHP, Ruby, Go, Rust, C++. O que realmente importa é lógica, estruturas de dados e paradigmas de programação, especialmente Orientação a Objetos.

- **Lógica de programação** — Condições, laços, funções e composição. É a gramática do raciocínio computacional.
- **Algoritmos e estruturas de dados** — Arrays, listas, mapas, árvores, grafos + Big-O. Define se seu código escala ou trava com muitos dados.
- **Paradigma: Procedural** — Código organizado em procedimentos/funções executados em sequência. Simples e direto.
- **Paradigma: Funcional** — Funções puras, imutabilidade e composição; evita estado compartilhado. Reduz bugs de efeito colateral.
- **Paradigma: Orientado a Objetos** — Modela o mundo em objetos que combinam dados e comportamento. Base para SOLID, Design Patterns e DDD.
- **POO — Abstração** — Expor só o essencial e esconder o resto; pensar em 'o que faz', não 'como faz'.
- **POO — Herança** — Uma classe reusa/estende outra. Poderosa, mas use com parcimônia (prefira composição).
- **POO — Polimorfismo** — O mesmo contrato com comportamentos diferentes; permite trocar implementações sem alterar quem chama.
- **POO — Encapsulamento** — Proteger o estado interno atrás de métodos; ninguém mexe direto nos dados da classe.

🎬 **Vídeos:**
  - [Programming Languages — CS50](https://www.youtube.com/watch?v=31CxTRTi9ns)

📎 **Aprofundamento:**
  - [CS50P — Introduction to Programming with Python](https://cs50.harvard.edu/python/)

---

### 03 · SQL e Bancos relacionais

> Modelar dados em tabelas com relacionamentos e garantir integridade com transações ACID.

Bancos relacionais (SQL) guardam dados em tabelas ligadas por chaves. Dominar CRUD, relacionamentos, transações e as garantias ACID é pré-requisito para qualquer backend sério — e base para depois entender NoSQL e escalabilidade de leitura.

- **Operações de CRUD** — Create, Read, Update, Delete — as 4 operações básicas (INSERT/SELECT/UPDATE/DELETE).
- **Relacionamentos** — 1:1, 1:N e N:N via chaves estrangeiras e tabelas de junção. Normalização evita dados duplicados.
- **ACID** — Atomicidade (tudo ou nada), Consistência (regras respeitadas), Isolamento (transações não se atrapalham), Durabilidade (persiste após commit). [↗ ref](https://www.geeksforgeeks.org/acid-properties-in-dbms/)
- **Transações** — Agrupam operações que devem suceder ou falhar juntas; BEGIN/COMMIT/ROLLBACK. [↗ ref](https://www.geeksforgeeks.org/transaction-in-dbms/)
- **Índices** — Estruturas (B-tree) que aceleram buscas ao custo de escrita/espaço. Essenciais para performance de SELECT. [↗ ref](https://www.geeksforgeeks.org/indexing-in-databases-set-1/)

**Escolha um banco**

- **MySQL** — Muito popular, maduro, ótimo para web.
- **PostgreSQL** — Robusto, recursos avançados (JSON, extensões). Preferido por muita gente sênior.
- **SQLite** — Banco em arquivo, sem servidor; ideal para protótipos e apps locais.
- **MariaDB** — Fork open-source do MySQL.
- **Oracle** — Enterprise, comum em grandes corporações.

🎬 **Vídeos:**
  - [CS50 — Databases with SQL](https://cs50.harvard.edu/sql/)

📎 **Aprofundamento:**
  - [SQLBolt — Learn SQL (interativo)](https://sqlbolt.com/)
  - [SQL Performance Tuning — GeeksforGeeks](https://www.geeksforgeeks.org/sql-performance-tuning/)

---

### 04 · Versionamento de Código (Git)

> Controlar histórico, trabalhar em equipe e colaborar via repositórios remotos.

Git registra cada mudança e permite branches, merges e reverter erros. É a espinha dorsal do trabalho em equipe. Os repositórios remotos (GitHub, GitLab, Bitbucket) hospedam o código e integram CI/CD, code review e issues.

- **Conceitos essenciais** — commit, branch, merge, rebase, pull request, conflito. Aprenda o fluxo (feature branch → PR → merge).

**Repositórios remotos**

- **GitHub** — O mais usado; ecossistema Actions, Copilot, comunidade open-source.
- **GitLab** — Forte em CI/CD integrado e self-hosted.
- **Bitbucket** — Integra bem com o ecossistema Atlassian (Jira).

📎 **Aprofundamento:**
  - [Lista de comandos úteis do Git (Gist)](https://gist.github.com/leocomelli/2545add34e4fec21ec16)

---

### 05 · Redes e Internet

> Como dados trafegam na web: DNS, HTTP, cliente-servidor.

Toda aplicação moderna roda em rede. Entender DNS, o modelo requisição/resposta HTTP e como o navegador se comunica com o servidor é base para APIs, segurança e performance.

- **Fundamentos da WEB** — Cliente-servidor, URL, o ciclo requisição→resposta e o papel do navegador.
- **DNS** — Traduz nomes (site.com) em IPs. Camada crítica de disponibilidade e latência. [↗ ref](https://howdns.works/)
- **HTTP** — Protocolo texto sem estado sobre TCP; base de tudo na web.

📎 **Aprofundamento:**
  - [How DNS works (ilustrado)](https://howdns.works/)
  - [Uma típica sessão HTTP — MDN](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Session)

---

### 06 · Segurança (nível web)

> Proteger a aplicação: autenticação, autorização, HTTPS e ameaças comuns.

Segurança web começa por controlar quem entra (autenticação), o que cada um pode fazer (autorização) e por trafegar tudo cifrado (HTTPS). Conhecer CORS, cookies/sessão e as ameaças do OWASP Top Ten evita vulnerabilidades clássicas.

- **HTTP vs HTTPS** — HTTPS = HTTP sobre TLS: cifra o tráfego e garante identidade do servidor. Padrão obrigatório hoje.
- **Login / autenticação e autorização** — Autenticação = provar quem você é (senha, token, OAuth). Autorização = o que você pode fazer (papéis/permissões).
- **CORS** — Regra do navegador que controla quais origens podem chamar sua API. Fonte comum de dor de cabeça no front.
- **Cookies / Sessão** — Cookies guardam estado no cliente; sessão associa requisições a um usuário logado. [↗ ref](https://developer.mozilla.org/docs/Web/HTTP/Cookies)
- **VPN / Firewall** — VPN cria túnel privado; firewall filtra tráfego. Camadas de proteção de rede.
- **OWASP Top Ten** — As 10 vulnerabilidades web mais críticas (injection, XSS, quebra de acesso…). Leitura obrigatória. [↗ ref](https://owasp.org/www-project-top-ten/)

📎 **Aprofundamento:**
  - [OWASP Top Ten](https://owasp.org/www-project-top-ten/)
  - [Using HTTP cookies — MDN](https://developer.mozilla.org/docs/Web/HTTP/Cookies)

---

### 07 · APIs & Integrações

> Como sistemas conversam: REST, JSON, métodos e status HTTP, gRPC e GraphQL.

APIs são o contrato pelo qual sistemas se integram. REST sobre HTTP/JSON é o padrão; gRPC e GraphQL resolvem casos específicos (performance e consultas flexíveis). Dominar métodos, status codes e versionamento é essencial no backend.

- **O que é uma API** — Interface que expõe funcionalidades de um sistema para outro consumir de forma controlada.
- **APIs REST e RESTful** — Recursos identificados por URLs, manipulados por métodos HTTP; sem estado. RESTful = segue as restrições do REST.
- **JSON** — Formato de troca de dados leve e legível; padrão de fato em APIs web.
- **Métodos HTTP** — GET (ler), POST (criar), PUT/PATCH (atualizar), DELETE (remover). Semântica importa.
- **Status codes** — 2xx sucesso, 3xx redirect, 4xx erro do cliente, 5xx erro do servidor. Comunicam o resultado.
- **HATEOAS** — Respostas incluem links para as próximas ações possíveis; nível máximo de maturidade REST.
- **Paginação, filtros e versionamento** — Controlam volume de dados e evolução da API sem quebrar clientes.
- **gRPC** — RPC binário sobre HTTP/2 com contratos (protobuf); rápido, ótimo entre microsserviços. [↗ ref](https://aws.amazon.com/compare/the-difference-between-grpc-and-rest/)
- **GraphQL** — O cliente pede exatamente os campos que quer numa só chamada; evita over/under-fetching. [↗ ref](https://aws.amazon.com/compare/the-difference-between-graphql-and-rest/)
- **HTTP/3 (QUIC)** — Nova versão sobre UDP; menos latência e melhor em redes instáveis. [↗ ref](https://kinsta.com/pt/blog/http3/)

🎬 **Vídeos:**
  - [CS50W Lecture 4 — ORMs, APIs](https://www.youtube.com/watch?v=24Kf3v7kZyE)

📎 **Aprofundamento:**
  - [gRPC x REST — AWS](https://aws.amazon.com/compare/the-difference-between-grpc-and-rest/)
  - [GraphQL vs REST — AWS](https://aws.amazon.com/compare/the-difference-between-graphql-and-rest/)
  - [O que é HTTP/3 — Kinsta](https://kinsta.com/pt/blog/http3/)

---

### 08 · Model-View-Controller (MVC)

> Padrão que separa dados (Model), interface (View) e lógica de fluxo (Controller).

MVC organiza a aplicação em três responsabilidades: Model (dados/regras), View (apresentação) e Controller (recebe a requisição e coordena). Quase todo framework web se apoia nesse conceito — escolha um e vá fundo.

- **Model** — Dados e regras de negócio; independente da tela.
- **View** — O que o usuário vê; recebe dados prontos do controller.
- **Controller** — Recebe a requisição, chama o model e escolhe a view/resposta.

**Escolha um framework**

- **NestJS** — Node/TypeScript, arquitetura opinativa (módulos, DI).
- **Spring Boot** — Java, padrão enterprise robusto.
- **Laravel** — PHP, produtivo e elegante.
- **Django** — Python, 'batteries included'.
- **ASP.NET** — C#/.NET, forte no ecossistema Microsoft.
- **Flask** — Python, micro-framework minimalista.
- **Ruby on Rails** — Ruby, convenção sobre configuração.
- **Symfony** — PHP, componentizado e flexível.

---

### 09 · Docker

> Empacotar a aplicação e suas dependências em contêineres portáveis.

Docker resolve o 'na minha máquina funciona': empacota app + dependências numa imagem que roda igual em qualquer lugar. Base para ambientes reproduzíveis, CI/CD e, depois, orquestração (Kubernetes).

- **Conceitos de conteinerização** — Contêiner isola processos compartilhando o kernel; mais leve que VM.
- **Comandos básicos** — run, build, ps, logs, exec, stop. O dia a dia do Docker.
- **Imagens / Volumes / Network** — Imagem é o template; volume persiste dados; network liga contêineres.
- **Dockerfile** — Receita declarativa para construir a imagem da sua app.
- **Docker Compose** — Sobe vários contêineres (app + banco + cache) com um só arquivo YAML.


---
➡️ Próxima fase: [02 — Pleno / Sénior](02-fase-pleno-senior.md)
