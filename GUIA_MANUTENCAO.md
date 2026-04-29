# 📋 Guia de Manutenção e Boas Práticas CSS

## 📐 Arquitetura

O projeto usa uma estrutura **modular e escalável** com separação clara de responsabilidades:

```
index.css (main)
├── global.css         → Design tokens + reset + utilitários
├── header.css         → Hero section + navegação
├── section.css        → Layouts de seção + grids
├── cards.css          → Cards de projeto
├── footer.css         → Rodapé
└── responsive.css     → Media queries (mobile-first)
```

## 🎨 Design Tokens

Todos os valores estão centralizados em **variáveis CSS** no `global.css`:

```css
/* Cores */
--color-primary: #E3646E (vermelho principal)
--color-accent: #BB72E9 (roxo para títulos)
--color-text: #E2E4E9 (texto principal)

/* Espaçamento */
--spacing-sm: 12px
--spacing-md: 16px
--spacing-lg: 20px

/* Tipografia */
--font-primary: 'Poppins', sans-serif
--text-sm: 16px
--text-md: 24px
--text-lg: 32px
```

## ✅ Checklist de Manutenção

### Ao Adicionar Novos Componentes
- [ ] Use variáveis CSS para cores e espaçamento
- [ ] Inclua estados `:hover`, `:active` e `:focus`
- [ ] Adicione transições suaves (`--transition-base`)
- [ ] Implemente responsividade (480px, 768px, 1024px)
- [ ] Teste com teclado (tab, enter)

### Ao Modificar Estilos
- [ ] Procure por duplicações (reutilize padrões)
- [ ] Verifique cascata CSS (evite `!important`)
- [ ] Teste em múltiplos navegadores
- [ ] Mantenha performance (evite muitas shadows/blurs)

## 🔧 Principais Melhorias Realizadas

### 1. **Eliminação de Duplicações**
**Antes:**
```css
/* Repetido em vários lugares */
.card {
  transition: transform 0.3s ease;
}
.servicos-grid article {
  transition: transform 0.3s;
}
```

**Depois:**
```css
/* Centralizado */
--transition-base: 0.3s ease-in-out;

.card {
  transition: all var(--transition-base);
}
```

### 2. **Padronização de Spacing**
**Antes:**
```css
padding: 20px;
margin: 10px 0;
gap: 20px;
```

**Depois:**
```css
padding: var(--spacing-lg);
margin: var(--spacing-md) 0;
gap: var(--spacing-lg);
```

### 3. **Grid Responsivo**
**Antes:**
```css
.grid {
  grid-template-columns: repeat(3, minmax(250px, 1fr));
}
/* Quebrava em mobile */
```

**Depois:**
```css
.grid {
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
}

@media (max-width: 768px) {
  /* Ajusta automaticamente */
}
```

### 4. **Correção de Bugs**
- ✅ Removido `font-weight: 600px` (valor inválido)
- ✅ Removido `darken()` (função SCSS em CSS puro)
- ✅ Padronizado uso de pseudo-elementos (`::before`)
- ✅ Melhorado contraste de texto com overlays

## 📱 Responsividade

### Breakpoints Padrão
```
480px   → Smartphones
768px   → Tablets
1024px  → Desktop
1440px  → Large Desktop
```

### Mobile-First Approach
```css
/* Base: Mobile (320px) */
.grid {
  grid-template-columns: 1fr;
}

/* Tablet (768px) */
@media (min-width: 768px) {
  .grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* Desktop (1024px) */
@media (min-width: 1024px) {
  .grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
```

## 🎯 Performance

### Otimizações Aplicadas
1. **Flexbox/Grid** em vez de float
2. **Will-change** não usado (overhead desnecessário)
3. **Transform/Opacity** para animações (GPU acelerado)
4. **Backdrop-filter** evitado (suporte limitado)
5. **Preload de fontes** com `preconnect`

## 🔐 Acessibilidade

```css
/* Respeitar preferência por movimento reduzido */
@media (prefers-reduced-motion: reduce) {
  * {
    animation: none !important;
    transition: none !important;
  }
}

/* Suporte a modo escuro (já implementado) */
@media (prefers-color-scheme: dark) {
  /* Padrão escuro mantido */
}
```

## 📝 Convenções de Nomenclatura

### Classes
- Use **kebab-case**: `.social-media-item`
- Prefixo funcional: `.btn-primary`, `.card-content`
- Evite nomes baseados em estilo: ❌ `.red-text`, ✅ `.text-error`

### Variáveis CSS
- **Cores**: `--color-primary`, `--color-text`
- **Spacing**: `--spacing-sm`, `--spacing-lg`
- **Tipografia**: `--text-sm`, `--text-lg`

## 🚀 Como Adicionar Nova Seção

### 1. Criar o CSS
```css
/* novasecao.css */
.nova-secao {
  padding: var(--spacing-3xl) var(--spacing-md);
  background-color: var(--color-surface);
}

@media (max-width: 768px) {
  .nova-secao {
    padding: var(--spacing-2xl) var(--spacing-sm);
  }
}
```

### 2. Importar no index.css
```css
@import url(novasecao.css);
```

### 3. Usar no HTML
```html
<section class="nova-secao">
  <!-- Conteúdo -->
</section>
```

## 🐛 Debugging

### Verificar Cascata
```css
/* Usar seletor específico */
.container .card {  /* Especificidade: 0,1,2 */
}

/* Evitar */
.card {  /* Especificidade: 0,0,1 */
}
```

### Inspecionar Computed Styles
```
Chrome DevTools > Elements > Styles > Computed
```

## 📚 Recursos Úteis

- [MDN - CSS Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/grid)
- [MDN - Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout)
- [Can I Use](https://caniuse.com) - Compatibilidade de navegadores

## ✨ Próximas Melhorias Sugeridas

1. **Temas (Light/Dark)**: Adicionar toggle de modo escuro
2. **CSS-in-JS**: Considerar styled-components se evoluir para React
3. **Crítico CSS**: Inline estilos críticos para melhor LCP
4. **Lazy Loading**: Imagens com `loading="lazy"`
5. **WebP Fallback**: Otimizar formato de imagens
