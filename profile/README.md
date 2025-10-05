<!-- ========================================================= -->
<!-- README institucional da organização SP Águas no GitHub -->
<!-- ========================================================= -->

<!--<p align="center">
  <img src="https://media.licdn.com/dms/image/v2/D4D0BAQEtDh68Uezd3A/company-logo_200_200/company-logo_200_200/0/1727802419122/daeesp_logo?e=2147483647&v=beta&t=hNpFNIquKKSb502E1wH-YikAJXvgbQefwE3H4vaPgjk" alt="SP Águas Logo" width="120" />
</p>-->

<h1 align="center">🌊 SP Águas</h1>
<h3 align="center">Gestão de Recursos Hídricos do Estado de São Paulo</h3>

<p align="center">
  <a href="https://www.spaguas.sp.gov.br"><img src="https://img.shields.io/badge/Site-Institucional-blue?style=flat-square"></a>
  <a href="#"><img src="https://img.shields.io/badge/LGPD-Ready-green?style=flat-square"></a>
  <a href="#"><img src="https://img.shields.io/badge/Open%20Source-Governamental-lightgrey?style=flat-square"></a>
  <a href="#"><img src="https://img.shields.io/badge/Código%20de%20Conduta-Ativo-blueviolet?style=flat-square"></a>
</p>

---

## 📘 Missão Institucional

> Promover a gestão integrada e sustentável dos recursos hídricos no Estado de São Paulo, assegurando a disponibilidade e qualidade da água para as presentes e futuras gerações.

---

## 🏗️ Estrutura dos Repositórios

| Categoria | Descrição |
|------------|------------|
| `dados-hidrometricos` | Coleta e tratamento de dados de nível e vazão em estações fluviométricas. |
| `dados-pluviometricos` | Processamento e análise de séries históricas de chuva. |
| `geoapi` | Serviços de mapas e camadas geoespaciais (GeoServer, Leaflet, etc.). |
| `bff` | Backends for Frontends (Node.js, Python, Rails) para consumo de APIs internas. |
| `mobile` | Aplicativos Android para inspeções de campo e coletas de dados offline. |
| `dashboards` | Painéis de visualização (Grafana, Kibana, Metabase). |

---

## 🤝 Código de Conduta

Para garantir um ambiente respeitoso e colaborativo, todos os participantes devem observar o **Código de Conduta da SP Águas**:

### 1. Respeito e Ética
- Trate todos os colaboradores, internos e externos, com **respeito e cortesia**.  
- Não são toleradas condutas discriminatórias, ofensivas ou de assédio.

### 2. Colaboração
- Prefira **issues** e **pull requests** claros e bem documentados.  
- Sempre descreva o **motivo da alteração**, o **impacto esperado** e a **relação com demandas institucionais**.

### 3. Transparência e Responsabilidade
- Evite informações sensíveis ou dados pessoais em commits, mensagens e documentação.  
- Mantenha a **autoria e rastreabilidade** das contribuições.

### 4. Comunicação
- Utilize linguagem profissional, técnica e impessoal.  
- Para discussões institucionais, utilize os canais oficiais da Gerência de TI.

---

## 🔐 Política de Segurança da Informação

A SP Águas adota práticas de segurança alinhadas à **Lei Geral de Proteção de Dados (LGPD — Lei 13.709/2018)**, **Decreto 10.046/2019**, e **IN SGD/ME nº 1/2019**.

### 1. Controle de Acesso
- O acesso aos repositórios é **controlado por papéis (roles)** conforme a função institucional.  
- Contribuições externas requerem aprovação prévia da **Gerência de TI (SA-GTI)**.

### 2. Dados e Sigilo
- É **proibido** o envio de dados pessoais, credenciais, chaves de API, tokens de acesso ou informações classificadas.  
- Utilize variáveis de ambiente e arquivos `.env` que **não devem ser versionados** (`.gitignore` obrigatório).

### 3. Vulnerabilidades
- Caso identifique uma vulnerabilidade ou falha de segurança, **não abra uma issue pública**.  
  Envie um e-mail para: **seguranca@spaguas.sp.gov.br**.  
  A equipe de segurança avaliará e responderá conforme o nível de criticidade.

### 4. Dependências e Licenças
- Todos os projetos devem declarar dependências e licenças em conformidade com software livre ou com as licenças adquiridas institucionalmente.  
- Sempre revisar e atualizar dependências vulneráveis.

---

## 🧩 Diretrizes de Desenvolvimento

- Preferir **tecnologias open-source** e **padrões abertos (OGC, REST, JSON, GeoJSON, CSV)**.  
- Manter compatibilidade com o ecossistema interno (PostgreSQL/PostGIS, Elasticsearch, Docker, Grafana, etc.).  
- Adotar **versionamento semântico (semver)**.  
- Garantir testes automatizados e documentação de endpoints.

---

## 📄 Licença

Todos os projetos da SP Águas são disponibilizados sob a licença **MIT**, salvo indicação em contrário nos repositórios específicos.

