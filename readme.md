Guia Completo: GitHub Desktop e Git Bash para Projetos VSCode
# Guia Completo: GitHub Desktop e Git Bash para Projetos VSCode

## Sumário
1. [Introdução](#introdução)
2. [Instalação e Configuração](#instalação-e-configuração)
3. [Criando um Repositório](#criando-um-repositório)
4. [Trabalhando com Branches](#trabalhando-com-branches)
5. [Realizando Commits](#realizando-commits)
6. [Merge de Branches](#merge-de-branches)
7. [Sincronização com o GitHub](#sincronização-com-o-github)
8. [Comandos Essenciais do Git Bash](#comandos-essenciais-do-git-bash)
9. [Integração com VSCode](#integração-com-vscode)
10. [Resolução de Conflitos](#resolução-de-conflitos)
11. [Boas Práticas](#boas-práticas)

---

## Introdução

O controle de versão é fundamental para qualquer desenvolvedor. Este guia aborda como usar o **GitHub Desktop** (interface gráfica) e o **Git Bash** (linha de comando) para gerenciar seus projetos do VSCode de forma eficiente.

### O que você vai aprender:
- Criar e gerenciar repositórios locais e remotos
- Trabalhar com branches para organizar funcionalidades
- Realizar commits e merges
- Sincronizar código com o GitHub
- Usar comandos básicos do Git Bash
- Integrar tudo com o VSCode

---

## Instalação e Configuração

### 1. Instalando o GitHub Desktop

1. Acesse [desktop.github.com](https://desktop.github.com/)
2. Baixe a versão para seu sistema operacional
3. Execute o instalador e siga as instruções
4. Faça login com sua conta do GitHub

### 2. Instalando o Git Bash

1. Acesse [git-scm.com](https://git-scm.com/)
2. Baixe o Git para Windows (já inclui o Git Bash)
3. Durante a instalação, selecione "Git Bash Here" para ter acesso via menu de contexto

### 3. Configuração Inicial

Abra o Git Bash e configure suas informações:

```bash
# Configurar nome de usuário
git config --global user.name "Seu Nome"

# Configurar email
git config --global user.email "seu.email@example.com"

# Verificar configurações
git config --list
```

---

## Criando um Repositório

### Método 1: GitHub Desktop

1. **Novo Repositório Local:**
   - Abra o GitHub Desktop
   - Clique em "File" → "New Repository"
   - Preencha os campos:
     - **Name**: nome do seu projeto
     - **Description**: descrição breve
     - **Local Path**: onde será salvo no seu computador
     - **Initialize with README**: marque esta opção
   - Clique em "Create Repository"

2. **Clonar Repositório Existente:**
   - Clique em "File" → "Clone Repository"
   - Selecione o repositório da lista ou insira a URL
   - Escolha o local para salvar
   - Clique em "Clone"

### Método 2: Git Bash

```bash
# Criar um novo repositório
mkdir meu-projeto
cd meu-projeto
git init

# Criar arquivo README
echo "# Meu Projeto" > README.md

# Adicionar arquivo ao staging
git add README.md

# Primeiro commit
git commit -m "Initial commit"

# Conectar com repositório remoto
git remote add origin https://github.com/seuusuario/meu-projeto.git
git push -u origin main
```

---

## Trabalhando com Branches

### No GitHub Desktop

1. **Criar Nova Branch:**
   - Clique no botão "Current Branch" no topo
   - Clique em "New Branch"
   - Digite o nome da branch (ex: "feature-login")
   - Clique em "Create Branch"

2. **Alternar Entre Branches:**
   - Clique em "Current Branch"
   - Selecione a branch desejada da lista

3. **Publicar Branch no GitHub:**
   - Após criar a branch, clique em "Publish Branch"

### No Git Bash

```bash
# Listar todas as branches
git branch -a

# Criar nova branch
git branch feature-login

# Criar e mudar para nova branch
git checkout -b feature-cadastro

# Mudar para uma branch existente
git checkout main

# Mudar para uma branch (comando moderno)
git switch feature-login

# Criar e mudar para nova branch (comando moderno)
git switch -c feature-nova-funcionalidade
```

---

## Realizando Commits

### No GitHub Desktop

1. **Fazer Alterações no Código:**
   - Edite seus arquivos no VSCode
   - As alterações aparecerão automaticamente no GitHub Desktop

2. **Revisar Alterações:**
   - Na aba "Changes", você verá todos os arquivos modificados
   - Clique em um arquivo para ver as diferenças (diff)

3. **Criar Commit:**
   - Na parte inferior esquerda, escreva uma mensagem descritiva
   - Opcionalmente, adicione uma descrição mais detalhada
   - Clique em "Commit to [nome-da-branch]"

### No Git Bash

```bash
# Ver status do repositório
git status

# Adicionar arquivo específico ao staging
git add nome-do-arquivo.js

# Adicionar todos os arquivos modificados
git add .

# Ver diferenças antes de commitar
git diff

# Fazer commit
git commit -m "Adiciona funcionalidade de login"

# Commit com mensagem detalhada
git commit -m "Título do commit" -m "Descrição detalhada das alterações realizadas"
```

---

## Merge de Branches

### No GitHub Desktop

1. **Preparar para Merge:**
   - Mude para a branch de destino (geralmente `main`)
   - Clique em "Branch" → "Merge into current branch"

2. **Realizar Merge:**
   - Selecione a branch que deseja fazer merge
   - Clique em "Merge [nome-da-branch] into main"

3. **Push das Alterações:**
   - Clique em "Push origin" para enviar as alterações para o GitHub

### No Git Bash

```bash
# Mudar para branch principal
git checkout main

# Atualizar branch principal
git pull origin main

# Fazer merge da feature branch
git merge feature-login

# Push das alterações
git push origin main

# Deletar branch local após merge
git branch -d feature-login

# Deletar branch remota
git push origin --delete feature-login
```

---

## Sincronização com o GitHub

### No GitHub Desktop

1. **Push (Enviar alterações):**
   - Após fazer commits, clique em "Push origin"

2. **Pull (Receber alterações):**
   - Clique em "Fetch origin" para verificar atualizações
   - Se houver alterações, clique em "Pull origin"

3. **Sync (Sincronizar):**
   - Use "Fetch origin" regularmente para manter-se atualizado

### No Git Bash

```bash
# Enviar alterações para GitHub
git push origin main

# Receber alterações do GitHub
git pull origin main

# Buscar informações sobre alterações remotas
git fetch origin

# Ver diferenças entre local e remoto
git log HEAD..origin/main --oneline
```

---

## Comandos Essenciais do Git Bash

### Navegação e Arquivos

```bash
# Listar arquivos e pastas
ls

# Entrar em uma pasta
cd nome-da-pasta

# Voltar uma pasta
cd ..

# Mostrar caminho atual
pwd

# Criar pasta
mkdir nova-pasta

# Criar arquivo
touch novo-arquivo.txt
```

### Comandos Git Fundamentais

```bash
# Inicializar repositório
git init

# Clonar repositório
git clone https://github.com/usuario/repositorio.git

# Ver histórico de commits
git log

# Ver histórico resumido
git log --oneline

# Ver alterações não commitadas
git diff

# Ver alterações de um arquivo específico
git diff nome-arquivo.js

# Desfazer alterações em arquivo (cuidado!)
git checkout -- nome-arquivo.js

# Desfazer último commit (mantém alterações)
git reset HEAD~1

# Ver informações sobre repositório remoto
git remote -v
```

### Comandos Avançados

```bash
# Stash (guardar alterações temporariamente)
git stash

# Aplicar stash
git stash pop

# Ver lista de stashes
git stash list

# Criar tag
git tag -a v1.0 -m "Versão 1.0"

# Enviar tags para remoto
git push origin --tags

# Rebase interativo (organizar commits)
git rebase -i HEAD~3
```

---

## Integração com VSCode

### Configurando o VSCode

1. **Terminal Integrado:**
   - Abra VSCode
   - Vá em `Terminal → New Terminal`
   - Configure o Git Bash como padrão em `Terminal → Select Default Profile`

2. **Extensões Recomendadas:**
   - **Git Graph**: Visualizar histórico de commits
   - **GitLens**: Informações detalhadas sobre Git
   - **GitHub Pull Requests**: Gerenciar Pull Requests

### Usando Git no VSCode

1. **Source Control:**
   - Use a aba "Source Control" (Ctrl+Shift+G)
   - Veja alterações, stage arquivos e faça commits

2. **Sincronização:**
   - Use os botões de sync na barra de status
   - Ícone de nuvem mostra status de sincronização

---

## Resolução de Conflitos

### Identificando Conflitos

```bash
# Durante um merge, se houver conflito:
git status

# Arquivos em conflito serão listados como "both modified"
```

### Resolvendo no VSCode

1. **Abrir arquivo em conflito:**
   - VSCode destacará as seções conflitantes
   - Opções: "Accept Current Change", "Accept Incoming Change", "Accept Both Changes"

2. **Finalizar resolução:**
   ```bash
   # Após resolver manualmente
   git add arquivo-resolvido.js
   git commit -m "Resolve conflito em arquivo-resolvido.js"
   ```

### Resolvendo no GitHub Desktop

1. **Conflitos aparecerão na interface**
2. **Clique em "Open in External Editor"**
3. **Resolva no VSCode e salve**
4. **Retorne ao GitHub Desktop e faça commit**

---

## Boas Práticas

### Commits

- **Mensagens descritivas**: Use verbos no imperativo
  - ✅ "Adiciona validação de email"
  - ❌ "Adicionei validação"

- **Commits atômicos**: Um commit por funcionalidade
- **Commitar frequentemente**: Não acumule muitas alterações

### Branches

- **Nomenclatura clara**:
  - `feature/login-usuario`
  - `bugfix/corrige-validacao`
  - `hotfix/erro-critico`

- **Branch por funcionalidade**: Uma branch para cada nova feature
- **Manter branches atualizadas**: Sync regular com main

### Fluxo de Trabalho

1. **Sempre começar da main atualizada**
   ```bash
   git checkout main
   git pull origin main
   ```

2. **Criar branch para nova feature**
   ```bash
   git checkout -b feature/nova-funcionalidade
   ```

3. **Desenvolver e commitar regularmente**

4. **Fazer merge quando feature estiver completa**

5. **Deletar branch após merge**

### Segurança

- **Nunca commitar senhas ou chaves**
- **Use .gitignore** para arquivos sensíveis:
  ```gitignore
  # Arquivo .gitignore
  node_modules/
  .env
  *.log
  dist/
  .vscode/settings.json
  ```

---

## Troubleshooting Comum

### Problemas Frequentes

1. **"Repository not found"**
   ```bash
   # Verificar se o remote está correto
   git remote -v
   
   # Reconfigurar remote
   git remote set-url origin https://github.com/usuario/repositorio.git
   ```

2. **Conflito de merge**
   ```bash
   # Abortar merge
   git merge --abort
   
   # Ou resolver conflitos e continuar
   git add .
   git commit
   ```

3. **Desfazer último commit**
   ```bash
   # Desfaz commit mas mantém alterações
   git reset --soft HEAD~1
   
   # Desfaz commit e alterações (cuidado!)
   git reset --hard HEAD~1
   ```

---

## Recursos Adicionais

### Links Úteis

- [Documentação Oficial do Git](https://git-scm.com/doc)
- [GitHub Desktop Docs](https://docs.github.com/pt/desktop)
- [Atlassian Git Tutorials](https://www.atlassian.com/br/git/tutorials)

### Comandos de Referência Rápida

```bash
# Setup
git config --global user.name "Nome"
git config --global user.email "email"

# Repositório
git init
git clone <url>
git status
git add .
git commit -m "mensagem"
git push origin main
git pull origin main

# Branches
git branch
git branch <nome>
git checkout <nome>
git merge <nome>
git branch -d <nome>

# Histórico
git log
git log --oneline
git diff
```

---

## Conclusão

Este guia abordou os aspectos fundamentais para trabalhar com Git, GitHub Desktop e Git Bash em seus projetos VSCode. A prática constante com essas ferramentas tornará seu fluxo de desenvolvimento mais eficiente e organizado.

Lembre-se: o controle de versão é uma habilidade essencial para qualquer desenvolvedor. Comece com o básico e gradualmente incorpore técnicas mais avançadas conforme sua experiência cresce.

**Próximos passos:**
1. Pratique criando um repositório de teste
2. Experimente diferentes fluxos de trabalho com branches
3. Explore as funcionalidades avançadas do GitHub Desktop
4. Familiarize-se com comandos Git Bash para maior controle

---

*Guia criado com base na documentação oficial do GitHub e melhores práticas da comunidade de desenvolvimento.*