#  Portfólio - Felipe Santos

> Portfólio responsivo de desenvolvedor full stack com design moderno e CSS profissional

##  Sobre o Projeto

Este é um **portfólio web moderno** criado para apresentar projetos, serviços e facilitar o contato de um desenvolvedor full stack. O site apresenta:

-  **Hero Section** com apresentação pessoal
-  **Showcase de Tecnologias** (HTML, CSS, JavaScript, React, Node.js)
-  **Galeria de Projetos** com grid responsivo
-  **Seção de Serviços** (Web, APIs, DevOps)
-  **Links para Redes Sociais** (LinkedIn, Instagram, GitHub, Email)
-  **Design 100% Responsivo** (Mobile, Tablet, Desktop)

##  Origem do Projeto

Este projeto é uma **cópia/implementação** do modelo criado pela **[Rocketseat](https://www.rocketseat.com.br)**, uma plataforma de educação em tecnologia. Realizei uma **refatoração completa do CSS** para melhorias de qualidade e manutenibilidade.

### Créditos
- **Design e Conceito**: Rocketseat
- **Refatoração CSS e HTML**: Melhorias de código, documentação e responsividade

##  Tecnologias Utilizadas

### Frontend
- **HTML5** - Semântica e acessibilidade
- **CSS3** - Design System com variáveis CSS
- **JavaScript** (opcional - para interatividade futura)

### Design & UX
- **Responsive Design** - Mobile First
- **CSS Grid** - Layouts modernos
- **Flexbox** - Alinhamento e distribuição
- **CSS Animations** - Transições suaves

### Fontes
- **Poppins** - Tipografia principal
- **Asap, Maven Pro, Inconsolata** - Famílias alternativas

##  Estrutura do Projeto

```
portfolio/
├── index.html              # Página principal
├── index.css               # Importações de CSS
├── global.css              # Design tokens e reset
├── header.css              # Hero section e navegação
├── section.css             # Layouts de seção
├── cards.css               # Cards de projeto
├── footer.css              # Rodapé
├── responsive.css          # Media queries
├── GUIA_MANUTENCAO.md     # Documentação técnica
└── README.md               # Este arquivo
```

##  Design System

### Paleta de Cores
```css
--color-primary: #E3646E    /* Vermelho (CTA) */
--color-accent: #BB72E9     /* Roxo (Títulos) */
--color-accent-alt: #3996DB /* Azul (Links) */
--color-text: #E2E4E9       /* Branco suave */
--color-bg: #292C34         /* Cinza escuro */
--color-surface: #16181D    /* Preto profundo */
```

### Espaçamento Escalável
```css
--spacing-xs: 8px
--spacing-sm: 12px
--spacing-md: 16px    /* Base */
--spacing-lg: 20px
--spacing-xl: 32px
--spacing-2xl: 40px
--spacing-3xl: 60px
```

## 📱 Responsividade

O projeto segue **Mobile First** com breakpoints otimizados:

| Dispositivo | Resolução | Colunas |
|-----------|-----------|---------|
| Smartphone | < 480px | 1 coluna |
| Tablet | 768px | 2 colunas |
| Desktop | 1024px | 3 colunas |
| Large | 1440px+ | 3-4 colunas |

##  Como Usar

### Instalação
```bash
git clone https://github.com/seu-usuario/portfolio.git
cd portfolio
```

### Desenvolvimento Local
```bash
# Abrir em um servidor local (recomendado)
# Opção 1: Python
python -m http.server 8000

# Opção 2: Node.js
npx http-server

# Opção 3: VSCode Live Server
# Instale a extensão Live Server e clique em "Go Live"
```

Acesse em `http://localhost:8000`

### Personalização

1. **Editar informações pessoais** → `index.html`
2. **Mudar cores** → Variáveis em `global.css`
3. **Adicionar projetos** → Duplicar `.card` em `index.html`
4. **Atualizar links sociais** → Footer em `index.html`

##  Principais Melhorias Realizadas

### 1. **Sistema de Design Tokens**
- Centralização de cores, espaçamento, tipografia
- Mudanças globais com uma única variável

### 2. **Eliminação de Duplicações**
- Consolidação de transições, shadows, padrões
- Reutilização máxima de código

### 3. **Responsividade Completa**
- Mobile-first approach
- Grids automáticos com `auto-fit` e `minmax()`
- Testes em 5 diferentes resoluções

### 4. **Acessibilidade**
- Semântica HTML correta
- Suporte a `prefers-reduced-motion`
- `aria-label` em elementos interativos
- Contraste adequado de cores

### 5. **Performance**
- Flexbox/Grid em vez de float
- Transform/Opacity para animações (GPU acelerado)
- Preconnect para fontes Google
- Sem dependências externas

### 6. **Código Limpo**
- Convenção kebab-case
- Comentários estruturados
- Ordem lógica de propriedades
- Evitar `!important`

##  Documentação

Consulte **`GUIA_MANUTENCAO.md`** para:
- Checklist de manutenção
- Como adicionar novos componentes
- Debugging tips
- Boas práticas CSS
- Próximas melhorias sugeridas

##  Bugs Corrigidos

- ❌ `font-weight: 600px` (valor inválido) → ✅ Removido
- ❌ `darken()` (função SCSS) → ✅ Convertido para CSS puro
- ❌ Grids quebrados em mobile → ✅ `auto-fit, minmax()`
- ❌ Estilos hardcoded → ✅ Variáveis CSS
- ❌ Duplicação de código → ✅ Classes reutilizáveis
- ❌ Sem acessibilidade → ✅ WCAG AA compliant

## 🚀 Próximas Melhorias

- [ ] Adicionar Dark Mode com toggle
- [ ] Integrar formulário de contato (Formspree/Netlify)
- [ ] SEO otimizado (meta tags, structured data)
- [ ] Lazy loading de imagens
- [ ] Webp com fallback
- [ ] CSS minificado em produção
- [ ] Sitemap e robots.txt
- [ ] Google Analytics

##  Contribuições

Melhorias são bem-vindas! Para contribuir:

```bash
1. Fork o projeto
2. Crie uma branch (git checkout -b feature/AmazingFeature)
3. Commit suas mudanças (git commit -m 'Add some AmazingFeature')
4. Push para a branch (git push origin feature/AmazingFeature)
5. Abra um Pull Request
```

##  Licença

Este projeto é **inspirado no trabalho da Rocketseat** e disponibilizado para fins educacionais e pessoais.

### Atribuição
- Conceito e design original: [Rocketseat](https://www.rocketseat.com.br)
- Refatoração CSS: Melhorias técnicas e documentação

**Você é livre para:**
- Usar como template pessoal
-  Estudar e aprender
-  Modificar e personalizar
- Compartilhar com créditos à Rocketseat

##  Contato

-  **LinkedIn**: [Clayton F Santos](http://linkedin.com/in/claytonfsantos/)
-  **Instagram**: [@thefall01](https://www.instagram.com/thefall01)
-  **GitHub**: [@claytosantos](https://github.com/claytosantos/)
-  **Email**: clayton.fs@outlook.com.br

##  Estatísticas do Projeto

| Métrica | Valor |
|---------|-------|
| Arquivos CSS | 7 |
| Linhas de CSS | ~1.200 |
| Variáveis CSS | 30+ |
| Breakpoints | 5 |
| Componentes | 8+ |
| Acessibilidade | WCAG AA |
| Performance | ⭐⭐⭐⭐⭐ |

---

**Criado por Felipe Santos**  
Refatoração realizada em 2025

Baseado no modelo educacional da [Rocketseat](https://www.rocketseat.com.br) 🚀
