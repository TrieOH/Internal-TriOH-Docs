---
sidebar_position: 10
---
## **Função:**

Um **wrapper padronizado para formulários** no Next.js, tipado com TypeScript, que:

- Centraliza **validação** (com Zod/Yup ou outro schema validator).
- Garante consistência de **estilo** (inputs, labels, botões).
- Controla **estado de envio** (loading, sucesso, erro).
- Pode integrar com **server actions** (como você já usa).

## **Props:**

- `onSubmit`— (values: T) => Promise<void>: Função chamada no submit. Pode ser server action.
- `schema`— ZodSchema<T>: Validação dos valores.
- `icon`— ReactNode (opcional): Ícone customizado. Se não passado, usa ícone padrão do tipo.
- `defaultValues` — Partial<T> (opcional): Valores iniciais para os inputs.
- `checkStrategy` — “any” | “all” (opcional): se precisa de **qualquer** ou **todas** as permissões (default: `"all"`).
- `actions` — array de ReactNode (opcional): Botões ou links adicionais (ex.: “Tentar novamente”, “Ir para Dashboard”).
- `className` — string (opcional): para estilização extra.

```md
```jsx
<StateView 
  type="empty" 
  message="Nenhum usuário encontrado." 
  actions={[
    <Button key="add" onClick={() => openUserForm()}>Adicionar usuário</Button>
  ]}
/>
```
```
