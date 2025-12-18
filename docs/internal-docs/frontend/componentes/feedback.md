---
sidebar_position: 6
---
# Feedback

## Componentes de Feedback (`feedback`)

| Nome | Função | Props | Localização |
| --- | --- | --- | --- |
| `Toast` | Mostra estados da UI (erro, carregando, vazio) | `state`, `message`, `icon` | `src/components/shared/feedback/Toast.tsx` |
| `LoadingIndicator` | Container de conteúdo com bordas e sombras | `title?`, `children`, `className?` | `src/components/shared/feedback/LoadingIndicator.tsx` |
| `CardSkeleton` | Tabela de dados | `data`, `columns`, `pagination?` | `src/components/shared/feedback/CardSkeleton.tsx` |
| [`StateView`](internal-docs/frontend/componentes/state_view) | Mostra estados da UI (erro, carregando, vazio) | `state`, `message`, `icon`, `actions` | `src/components/shared/feedback/StateView.tsx` |

[StateView](internal-docs/frontend/componentes/state_view)
