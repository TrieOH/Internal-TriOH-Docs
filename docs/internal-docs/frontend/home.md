---
sidebar_position: 1
---
# Frontend Branch - Home

**Status**: Planejamento/Desenvolvimento

## Links Rápidos

- [Repositório Antigo](https://github.com/cciuenf/SCTI-2025-Frontend)
- [Deploy](https://sctiuenf.com.br)
- [Docs](https://nextjs.org/docs)

## Features (possivelmente vou mover para outro local depois)

### Auth (ainda está como placeholder)

- **Descrição**: controla login, logout e callback.
- **Localização**: `src/features/auth`
- **Componentes**:
    - `LoginButton` → props: `callbackUrl?`
    - `LogoutButton` → props: `redirectTo?`
- **Actions**: `loginAction`, `logoutAction`, `getSessionAction`
- **Types**: `UserSession`

## Design System

### UI Base (shadcn/ui)

- Componentes customizáveis baseados em Radix UI
- Estilização com Tailwind CSS
- Temas claro/escuro

### Tokens

- **Cores**:
    - `primary`, `secondary`, `accent`, `background`, `foreground`, `muted`, `error`
- **Paleta:**
    - Primary: #000022
    - Secondary: #9ABDFF
    - Accent: #E28413
- **Espaçamentos**:
    - Escala baseada em múltiplos de 4px (0.5rem = 8px)
- **Tipografia**:
    - Fonte principal: Inter (a definir)
    - Tamanhos: xs, sm, base, lg, xl, 2xl, ...

### Padrões de Ícones

- Biblioteca principal: `lucide-react`
- Tamanhos padronizados: sm (16px), md (20px), lg (24px)

### Padrões de Feedback

- `StateView` sempre com ícone + mensagem + ação
- Toasts para notificações temporárias
- Confirmações para ações destrutivas

## Detalhes

[Arquitetura](internal-docs/frontend/arquitetura)

[Layout](internal-docs/frontend/layout)

[Catálogo de Componentes Compartilhados](internal-docs/frontend/componentes/home)

[Lib](internal-docs/frontend/lib)

[Fluxo Comum](internal-docs/frontend/fluxo)
