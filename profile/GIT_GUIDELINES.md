# 🧭 Boas Práticas de Utilização do Git — SP Águas

Este documento estabelece diretrizes e boas práticas para o uso do **Git** nos projetos institucionais da **SP Águas**, garantindo rastreabilidade, segurança, padronização e conformidade com normas de governança pública e de desenvolvimento de software.

---

## 📁 1. Estrutura de Repositórios

Os repositórios devem ser organizados de forma lógica e modular, de acordo com o tipo de projeto:

| Tipo de Projeto | Exemplo de Nome         | Observações                              |
| --------------- | ----------------------- | ---------------------------------------- |
| Backend / API   | `bff-outorgas-api`      | Contém serviços REST, GraphQL, etc.      |
| Frontend Web    | `portal-sibh-frontend`  | Aplicações Vue, React, Angular.          |
| Mobile          | `spaguas-inspecoes-app` | Aplicativos Android/iOS (Flutter, etc.). |
| Dados e Scripts | `hidrometria-scripts`   | Rotinas de ETL, ingestão e automação.    |
| Infraestrutura  | `devops-docker`         | Contêineres, Compose, CI/CD.             |

📌 **Recomendação:** Repositórios monolíticos devem ser evitados. Prefira repositórios temáticos e coesos.

---

## 🌱 2. Fluxo de Trabalho (Workflow)

A SP Águas adota um **fluxo baseado no GitFlow simplificado**, adequado a equipes técnicas de governo:

### **Branches Principais**

| Branch    | Descrição                                          |
| --------- | -------------------------------------------------- |
| `main`    | Código estável, homologado e pronto para produção. |
| `develop` | Código em desenvolvimento e integração contínua.   |

### **Branches Secundárias**

| Branch                           | Uso                                 |
| -------------------------------- | ----------------------------------- |
| `feature/nome-da-funcionalidade` | Novas funcionalidades ou melhorias. |
| `bugfix/nome-do-problema`        | Correção de defeitos.               |
| `hotfix/nome-do-hotfix`          | Correção urgente em produção.       |
| `release/vX.Y.Z`                 | Preparação de versão de entrega.    |

🧩 **Regra:** Sempre criar branches a partir de `develop`, exceto correções urgentes (hotfixes), que partem de `main`.

---

## 🧱 3. Commits Padronizados

Cada **commit** deve ser **claro, atômico e rastreável**. Use mensagens no **padrão convencional (Conventional Commits)**:

### **Formato:**

```
<tipo>(escopo): descrição curta
```

### **Exemplos:**

```
feat(api): adiciona endpoint para cálculo de vazão
fix(ui): corrige label do campo 'nível do rio'
chore(deps): atualiza dependências do Docker
docs(readme): adiciona seção de políticas de segurança
```

### **Tipos aceitos:**

* `feat` → nova funcionalidade
* `fix` → correção de erro
* `docs` → documentação
* `style` → formatação (sem alterar lógica)
* `refactor` → reestruturação de código
* `test` → inclusão/ajuste de testes
* `chore` → tarefas auxiliares (build, CI/CD, dependências)

📎 **Boas práticas:**

* Escreva mensagens no **imperativo** (“adiciona”, “corrige”, “remove”).
* Commits devem ser **pequenos e frequentes**.
* Inclua o **número da issue** quando aplicável (`feat: implementa relatório #123`).

---

## 🔄 4. Pull Requests (PRs)

As PRs devem seguir um fluxo de **revisão colaborativa** e transparente:

### **Antes de abrir um PR:**

1. Atualize seu branch com `develop`.
2. Teste localmente todas as alterações.
3. Confirme que não há credenciais ou dados pessoais.
4. Atualize a documentação se necessário.

### **Ao abrir o PR:**

* Título e resumo claros.
* Marque o revisor (`@spaguas-ti`).
* Indique se fecha uma issue.
* Use **checklists** de validação técnica e de segurança.

### **Após aprovação:**

* Use **merge via squash** ou **merge commit**.
* Nunca merge direto em `main` sem revisão.

---

## 🧩 5. Versionamento Semântico

Adote o padrão **[SemVer](https://semver.org/lang/pt-BR/)**: `MAJOR.MINOR.PATCH`

| Tipo  | Exemplo | Quando usar                          |
| ----- | ------- | ------------------------------------ |
| Major | `2.0.0` | Quebra de compatibilidade.           |
| Minor | `1.2.0` | Nova funcionalidade retrocompatível. |
| Patch | `1.1.2` | Correção sem alterar API.            |

📦 **Taguear versões:**

```
git tag -a v1.3.0 -m "Versão 1.3.0 - Ajustes no cálculo de vazão"
git push origin v1.3.0
```

---

## 🧰 6. Arquivos Essenciais

| Arquivo              | Finalidade                         |
| -------------------- | ---------------------------------- |
| `README.md`          | Instruções e descrição do projeto. |
| `LICENSE`            | Licença MIT.                       |
| `.gitignore`         | Exclusão de arquivos sensíveis.    |
| `CODE_OF_CONDUCT.md` | Regras de convivência.             |
| `SECURITY.md`        | Política de vulnerabilidades.      |
| `CONTRIBUTING.md`    | Guia de contribuição.              |
| `CHANGELOG.md`       | Histórico de versões.              |

---

## 🔒 7. Segurança e Conformidade

* **Nunca** submeter chaves de API, senhas ou dados pessoais.
* Use `.env` e **não versione**.
* Habilite **proteção de branches** e **revisões obrigatórias**.
* Ative **Dependabot** e **CodeQL**.
* Revogue acessos de ex-servidores.

---

## ⚙️ 8. Integração Contínua (CI/CD)

Pipelines baseados em **GitHub Actions** e **Docker Compose**:

* Commits em `develop` devem gerar builds e testes.
* Deploys apenas de `main` com aprovação formal.
* Logs devem ser armazenados em ambiente institucional.
* Nunca use `force push`.

---

## 🧾 9. Documentação e Transparência

* Mantenha documentação atualizada.
* Use Markdown (`docs/`, `README`, `CHANGELOG`).
* Inclua diagramas e exemplos de uso.
* Toda entrega deve ser rastreável e documentada.

---

## 🧹 10. Limpeza e Manutenção

* Remova branches obsoletos.
* Use `git rebase -i` para organizar commits.
* Revise permissões de colaboradores.
* Utilize tags para releases oficiais.

---

## 🧠 11. Exemplo de Fluxo Simplificado

```bash
# Criar uma nova feature
git checkout develop
git pull
git checkout -b feature/ajuste-calc-vazao

# Fazer alterações e commits
git add .
git commit -m "feat(api): adiciona novo método de cálculo de vazão"

# Publicar branch
git push origin feature/ajuste-calc-vazao

# Abrir Pull Request → Revisão → Merge
```

---

## 🏛️ 12. Alinhamento Institucional

Estas diretrizes estão alinhadas ao **PDTIC 2025-2030**, à **LGPD (Lei 13.709/2018)** e às boas práticas de **Governança Digital do Governo do Estado de São Paulo**.

---

<p align="center"><i>💧 “Transparência, inovação e governança pela água.”</i></p>
