---
sidebar_position: 7
---
# StateView

## **Função:**

Componente de **feedback visual** para exibir estados de página ou seções:

- **Erro** (ex.: 404, 500, falha de API)
- **Carregando** (spinner, progress bar)
- **Vazio** (nenhum item encontrado, lista vazia)
- **Restrição leve** (ex.: acesso negado, sem permissão, mas sem redirect)

O objetivo é **centralizar o estilo, ícones e layout** para manter consistência em toda a aplicação.

**Importante:**

A intenção para que ele foi criado é uso em conjunto com algum DataDisplay, se for para restrição de algo use RequirePermission ou Guard. (Talvez seria interessante usar ele dentro do guard para não replicar conteúdo, já que ele também vai ter blur, só que seria necessaria incluir o type “restricted”).

## **Props:**

- `type`— “error” | “loading” | “empty” | “restricted”: O tipo de estado que vai ser apresentado e consequentemente define o estilo do state view, tipo icone, cores, etc…
- `message`— string (opcional): Mensagem a ser exibida para o usuário. Se omitida, usa mensagem padrão por `type`.
- `icon`— ReactNode (opcional): Ícone customizado. Se não passado, usa ícone padrão do tipo.
- `requiredRoles` — string[]: lista de roles (ex.: `["admin", "manager"]`).
- `checkStrategy` — “any” | “all” (opcional): se precisa de **qualquer** ou **todas** as permissões (default: `"all"`).
- `actions` — array de ReactNode (opcional): Botões ou links adicionais (ex.: “Tentar novamente”, “Ir para Dashboard”).
- `className` — string (opcional): para estilização extra.

```jsx
<StateView 
  type="empty" 
  message="Nenhum usuário encontrado." 
  actions={[
    <Button key="add" onClick={() => openUserForm()}>Adicionar usuário</Button>
  ]}
/>
```
