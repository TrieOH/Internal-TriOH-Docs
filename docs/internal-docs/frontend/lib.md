---
sidebar_position: 4
---
# Fetch (lib/fetch/)

Será responsável por carregar todas as infos envolvendo o fetch, seja do httpClient

# Auth (lib/auth/)

## **checkAccess.ts**

`src/types/auth/types.ts` - Tipos específicos, tipo role e permission

`src/lib/auth/checkAccess.ts` - Função para verificar se o usuário tem permissão

- `checkAccess(user, requirements)` → retorna `{ allowed: boolean}`.
- recebe `roles`, `permissions`, `strategy ("any" | "all")`.
- usado no **Guard** (rota inteira) e no **RequirePermission** (UI granular).
- `requiredRoles` — string[]: lista de roles (ex.: `["admin", "manager"]`).
- `checkStrategy` — “any” | “all” (opcional) : se precisa de **qualquer** ou **todas** as permissões (default: `"all"`).
