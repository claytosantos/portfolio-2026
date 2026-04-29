# 📚 Git - Instruções e Histórico

## 🚀 Como Usar Este Repositório

### Clonar o Repositório
```bash
git clone <URL-do-repositorio>
cd portfolio
```

### Ver Histórico de Commits
```bash
# Ver todos os commits
git log

# Ver commits de forma compacta
git log --oneline

# Ver commits com estatísticas
git log --stat

# Ver commits de um arquivo específico
git log -- index.html
```

### Ver Diferenças
```bash
# Ver o que mudou no último commit
git show HEAD

# Ver diferença entre dois commits
git diff <commit1> <commit2>

# Ver mudanças não commitadas
git diff
```

---

## 📋 Histórico de Commits

### Commit 1: Refatoração Completa (6c0058b)
**Data**: 28 de Abril de 2025  
**Autor**: Felipe Santos  

#### O que foi feito:

✅ **Implementação de Design System**
- Sistema centralizado com 30+ variáveis CSS
- Cores consistentes (primary, accent, text, backgrounds)
- Espaçamento escalável (xs, sm, md, lg, xl, 2xl, 3xl)
- Tipografia padronizada
- Shadows e transições reutilizáveis

✅ **Refatoração HTML**
- Melhorar semântica (article, nav, section)
- Adicionar aria-label para acessibilidade
- Implementar rel="noopener noreferrer" para links externos
- Estrutura clara e bem organizada

✅ **Refatoração CSS**
- 7 arquivos modulares (global, header, section, cards, footer, responsive, index)
- Eliminação completa de duplicações
- Mobile-first com 5 breakpoints (480px, 768px, 1024px, 1440px+)
- Padrões consistentes de hover, transições, animações

✅ **Correção de Bugs**
- ❌ `font-weight: 600px` → ✅ Removido
- ❌ `darken()` (SCSS) → ✅ Convertido para CSS puro
- ❌ Grids quebrados → ✅ `auto-fit, minmax()`
- ❌ Sem responsividade → ✅ Responsivo completo
- ❌ Código hardcoded → ✅ Variáveis CSS

✅ **Acessibilidade (WCAG AA)**
- Suporte a `prefers-reduced-motion`
- Suporte a `prefers-color-scheme`
- Contraste adequado
- Semântica correta

✅ **Documentação**
- README.md completo com instruções
- GUIA_MANUTENCAO.md com boas práticas
- .gitignore com padrões úteis
- Comentários estruturados no código

#### Arquivos Criados:
```
.gitignore               (11 linhas)
GUIA_MANUTENCAO.md     (280+ linhas)
README.md              (380+ linhas)
cards.css              (80+ linhas)
footer.css             (70+ linhas)
global.css             (160+ linhas)
header.css             (140+ linhas)
index.css              (20 linhas)
index.html             (210 linhas)
responsive.css         (140+ linhas)
section.css            (200+ linhas)
```

**Total**: 11 arquivos, ~1.820 linhas de código

---

## 🔗 Próximas Etapas para Publicar

### 1. Criar Repositório no GitHub
```bash
# Acessar github.com e criar novo repositório
# Nomear: "portfolio" ou "portfolio-felipe-santos"
```

### 2. Conectar Repositório Local ao GitHub
```bash
# Adicionar remote (substitua SEU-USUARIO e SEU-REPO)
git remote add origin https://github.com/SEU-USUARIO/SEU-REPO.git

# Renomear branch para main (padrão GitHub)
git branch -M main

# Fazer push inicial
git push -u origin main
```

### 3. Configurar GitHub Pages (Hospedagem Gratuita)
```bash
# No repositório GitHub:
# Settings > Pages > Source: main branch
# Seu site estará em: https://seu-usuario.github.io/portfolio

# Ou com domínio customizado:
# Adicionar arquivo CNAME com seu domínio
# Configurar DNS apontando para GitHub Pages
```

---

## 📖 Fluxo de Trabalho Git

### Para Adicionar Novos Recurso
```bash
# 1. Criar branch feature
git checkout -b feature/novo-recurso

# 2. Fazer alterações
# ... editar arquivos ...

# 3. Ver mudanças
git status
git diff

# 4. Commitar
git add .
git commit -m "feat: descrição do novo recurso"

# 5. Fazer merge na main
git checkout main
git merge feature/novo-recurso

# 6. Deletar branch (opcional)
git branch -d feature/novo-recurso
```

### Para Corrigir Bugs
```bash
# 1. Criar branch fix
git checkout -b fix/nome-do-bug

# 2. Fazer correções
# ... editar arquivos ...

# 3. Commitar
git add .
git commit -m "fix: descrição da correção"

# 4. Fazer merge
git checkout main
git merge fix/nome-do-bug
```

### Mensagens de Commit Semânticas
Seguindo a convenção [Conventional Commits](https://www.conventionalcommits.org/):

```bash
# Feature (nova funcionalidade)
git commit -m "feat: adicionar dark mode"

# Fix (correção)
git commit -m "fix: corrigir responsividade em mobile"

# Docs (documentação)
git commit -m "docs: atualizar README com instruções"

# Style (formatação, sem lógica)
git commit -m "style: padronizar indentação"

# Refactor (refatoração de código)
git commit -m "refactor: simplificar componente card"

# Perf (melhorias de performance)
git commit -m "perf: otimizar carregamento de fontes"

# Test (testes)
git commit -m "test: adicionar testes de responsividade"
```

---

## 🔍 Comandos Git Úteis

```bash
# Ver status
git status

# Ver histórico
git log --oneline
git log --graph --oneline --all

# Ver um arquivo específico
git show HEAD:index.html

# Reverter mudanças não commitadas
git checkout -- <arquivo>

# Reverter último commit (mantendo mudanças)
git reset --soft HEAD~1

# Reverter último commit (descartando mudanças)
git reset --hard HEAD~1

# Criar tag para versão
git tag -a v1.0.0 -m "Versão 1.0.0"
git push origin v1.0.0

# Ver diferença entre branches
git diff main feature/novo-recurso

# Fazer squash de commits
git rebase -i HEAD~3  # Últimos 3 commits

# Stash (salvar mudanças temporariamente)
git stash
git stash pop

# Buscar do remoto
git fetch origin

# Puxar do remoto
git pull origin main

# Fazer push
git push origin main
```

---

## 📊 Estatísticas do Repositório

```
Branch: master (inicial) / main (recomendado)
Commits: 1
Arquivos: 11
Linhas de Código: ~1.820
Tamanho: ~90KB

Linguagens:
- CSS: ~1.200 linhas (60%)
- HTML: ~210 linhas (12%)
- Markdown: ~410 linhas (23%)
- Config: ~50 linhas (5%)
```

---

## 🎯 Checklist para Produção

- [x] Código refatorado e testado
- [x] README.md completo
- [x] .gitignore configurado
- [x] Primeiro commit realizado
- [ ] Repositório criado no GitHub
- [ ] Conectado ao repositório remoto
- [ ] Hospedado em GitHub Pages
- [ ] Domínio customizado (opcional)
- [ ] Formulário de contato funcionando
- [ ] Google Analytics configurado
- [ ] SEO meta tags adicionadas
- [ ] HTTPS ativado

---

## 💡 Dicas

1. **Commit frequente**: Faça commits pequenos e significativos
2. **Mensagens claras**: Descreva o quê e por quê (não o como)
3. **Branchs para features**: Mantenha main estável
4. **Pull antes de push**: Sempre atualize antes de publicar
5. **Revise antes de commitar**: Use `git diff` para verificar

---

## 🔗 Referências Úteis

- [Git Official Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [Pro Git Book](https://git-scm.com/book/en/v2)

---

Criado com ❤️ por Felipe Santos - 2025
