🇧🇷 [Leia em Português](README.pt-BR.md) (esta página) | 🇺🇸 [English](README.md)

# IROH — It Runs On Hostinger

> **Software auto-hospedado, simples e resiliente, criado para hospedagem compartilhada tradicional.**

![Mascote da iniciativa IROH](assets/branding/iroh-initiative.png)

---

## 🍵 Filosofia

A **Iniciativa IROH** (*It Runs On Hostinger*) é uma coleção de aplicações web e utilitários open-source e auto-hospedados, projetados especificamente para rodar em ambientes tradicionais de hospedagem compartilhada de baixo custo (como Hostinger, cPanel, Apache e Nginx).

Em uma era de infraestrutura cloud hiper-complexa, microsserviços e assinaturas mensais crescentes, o IROH dá um passo atrás para valorizar a simplicidade, a resiliência tranquila e a independência paciente. Acreditamos que softwares potentes para uso pessoal e de pequenas equipes não devem exigir um cluster Kubernetes ou uma equipe dedicada de DevOps. Se ele consegue rodar limpo em uma hospedagem compartilhada cPanel comum de R$ 15/mês, ele roda em qualquer lugar.

Cada projeto na iniciativa IROH é construído ao redor de formatos abertos de dados (como arquivos Markdown e esquemas SQL padrão), zero vendor lock-in e manutenção ultra-baixa. Você possui seus dados, seu código e seu servidor.

---

## 🚀 Projetos da Iniciativa

| Projeto | Descrição | Stack Tecnológica | Repositório | Status |
| :--- | :--- | :--- | :--- | :--- |
| **[jotter](PROJECTS.md#1-jotter)** | Base de conhecimento Markdown auto-hospedada com wikilinks, WebDAV sync e servidor MCP | Laravel, Vue 3, MySQL/SQLite | [`suporterfid/jotter`](https://github.com/suporterfid/jotter) | `v0 complete` |
| **[grandpasson](PROJECTS.md#2-grandpasson)** | Provedor de Identidade Single Sign-On ("SSOn") centralizado para hospedagem compartilhada | PHP 8.2+, SQLite/MySQL, Vue 3 | [`suporterfid/grandpasson`](https://github.com/suporterfid/grandpasson) | `Em desenvolvimento` |
| **[taskconnect](PROJECTS.md#3-taskconnect)** | Gerenciador de tarefas leve e rápido para produtividade pessoal e de equipe | PHP 8.2+, Vue 3 / Vite, SQLite/MySQL | [`suporterfid/taskconnect`](https://github.com/suporterfid/taskconnect) | `Em desenvolvimento` |
| **[ConvertDocToMd-PHP](PROJECTS.md#4-convertdoctomd-php)** | Utilitário PHP independente que converte arquivos DOC, DOCX e PDF em Markdown | PHP 8.2+ puro | [`suporterfid/ConvertDocToMd-PHP`](https://github.com/suporterfid/ConvertDocToMd-PHP) | `v0 complete` |
| **[statusconnect](PROJECTS.md#5-statusconnect)** | Serviço auto-hospedado de página de status e monitoramento de uptime para hospedagem compartilhada | PHP 8.2+, Vue 3, SQLite/MySQL | [`suporterfid/statusconnect`](https://github.com/suporterfid/statusconnect) | `Planejado` |
| **[tallymark](PROJECTS.md#6-tallymark)** | Contador de cliques e ferramenta minimalista para rastreamento de hábitos e eventos | PHP 8.2+, Vue 3 / Vite, SQLite | [`suporterfid/tallymark`](https://github.com/suporterfid/tallymark) | `Planejado` |

*Para descrições arquiteturais detalhadas, padrões de integração e mapa de dependências, veja o arquivo [PROJECTS.md](PROJECTS.md).*

---

## 🛠️ Requisitos Arquitetonicos Comuns

Todos os projetos sob a chancela IROH seguem um conjunto compartilhado de princípios de engenharia:

* **PHP 8.2+ e Suporte Duplo a Banco de Dados**: Alimentados por PHP moderno com suporte PDO tanto para SQLite (ideal para instalações single-tenant / zero-configuração) quanto para MySQL/MariaDB (padrão em cPanels de hospedagem compartilhada).
* **Sem Serviços Cloud Proprietários Obrigatórios**: As aplicações funcionam 100% autônomas, sem assinaturas SaaS obrigatórias, dependências de bancos externos ou APIs cloud proprietárias.
* **Docker Apenas para Experiência de Desenvolvimento (DX)**: Docker e Docker Compose são utilizados estritamente para ambientes locais de desenvolvimento e testes automatizados. A execução em produção depende de runtimes padrão de servidor.
* **Compatibilidade com cPanel e Hospedagem Compartilhada**: Implantação direta via upload de arquivo ZIP, FTP/SFTP/rsync, `composer install` básico e reescrita de URL padrão via `.htaccess`.
* **Formatos Abertos de Dados**: Os dados são mantidos em arquivos Markdown legíveis por humanos ou em estruturas SQL padrão para garantir total portabilidade e auditabilidade dos dados.

---

## 📜 Manifesto e Padrões de Design

Deseja saber mais sobre a filosofia por trás do IROH, o arquétipo do "ancião sábio" e nossas convenções de design?

* **[MANIFESTO.md](MANIFESTO.md)** — Leia nossa visão completa sobre por que a hospedagem compartilhada importa e nossos princípios fundamentais de design.
* **[BRANDING.md](BRANDING.md)** — Explore nossa identidade visual, paletas de cores, tipografia e diretrizes de tom de voz.

---

## 🤝 Contribuindo

Damos as boas-vindas a contribuições, propostas de projetos e feedbacks da comunidade!

Por favor, leia o arquivo **[CONTRIBUTING.md](CONTRIBUTING.md)** para saber como abrir issues, enviar pull requests, adotar convenções de commit ou propor novos projetos para integrar a iniciativa IROH.

---

## ⚖️ Licença

Toda a documentação e especificações neste repositório são lançadas sob a [Licença MIT](LICENSE). Os projetos individuais dentro da iniciativa IROH mantêm suas respectivas licenças MIT em seus repositórios.
