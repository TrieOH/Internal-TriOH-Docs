---
sidebar_position: 5
---
# Fluxo Comum

### Autenticação

- Fluxo com `Guard` + `callbackUrl`
- Redirecionamento após login para página anterior
- Páginas protegidas com middleware ou/e validação no fetch

### Listagem

- Sempre usar `List` ou `Table` com `StateView` para feedback
- Paginação
- Filtros salvos no localStorage

### Navegação

- Botões e links sempre via `NextLink` encapsulado
- Breadcrumbs para hierarquia de páginas (talvez?)
- Menu móvel responsivo

### Formulários

- Validação com Zod
- Feedback de erro inline ou Toast
- Submissão via Server Actions
