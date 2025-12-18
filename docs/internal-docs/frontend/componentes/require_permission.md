---
sidebar_position: 5
---
# RequirePermission

## **Função:**

Não navega o usuário, não redireciona… ele **controla renderização condicional da UI** com base em roles/permissions.

**Importante:**

- `isAllowed` — boolean: Resultado da verificação, verificação (idealmente derivado de uma checagem server-side). Se falso o usuário não verá o conteúdo protegido
    - É necessário usar o checkStrategy do lib/auth/checkAccess.ts, para adquirir esse valor

## **Props:**

```md
- `children` — ReactNode: Conteúdo autorizado, oque deve ser renderizado na página, caso o usuário tenha permissão.
- `requiredRoles` — string[]: lista de roles (ex.: `["admin", "manager"]`).
- `checkStrategy` — “any” | “all” (opcional) : se precisa de **qualquer** ou **todas** as permissões (default: `"all"`).
- `className` — string (opcional): para estilização extra.
```

```jsx
<RequirePermission requiredRoles={["admin"]}>
	<Conteudo/>
</RequirePermission>
```
