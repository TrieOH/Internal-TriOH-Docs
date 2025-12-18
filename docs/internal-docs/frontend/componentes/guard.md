---
sidebar_position: 3
---
# Guard

## **Função:**

Envolve uma página ou seção protegida.

Ele verifica se o usuário **tem permissão/autenticação** para acessar aquele conteúdo:

- Se tem acesso, renderiza o conteúdo normalmente
- Caso não tenha aplica um Blur sobre a página e mostra um estado visual (ex: cadeado + mensagem) e redireciona caso se aplique o usuário para a página necessária (login, autenticação, permissão especial).
- O redirecionamento inclui automaticamente um query param next, que indica para onde o usuário deve voltar depois de completar a ação. Ex: “/login?next=/dashboard”

**Importante:**

- `isAllowed` — boolean: Resultado da verificação, verificação (idealmente derivado de uma checagem server-side). Se falso o usuário não verá o conteúdo protegido
    - É necessário usar o checkStrategy do lib/auth/checkAccess.ts, para adquirir esse valor

O Guard pode ter auto redirect além dos botões de ação então é necessário ter cuidado para não usar mais de um redirect por página.

Fica de responsabilidade da página em questão implementar a lógica de redirect de volta para a página no query params, caso tenha o mesmo. (Criar uma utils para isso e evitar repetições, ex: uma função que recebe outra função e seus estados)

## **Props:**

- `children` — ReactNode: Conteúdo autorizado, oque deve ser renderizado na página, caso o usuário tenha permissão.
- `callbackUrl` — string(opcional): URL de destino para onde o usuário deve voltar(ser redirecionado) após o sucesso. Deve ser validada (usar caminhos relativos ou validados para evitar open-redirect). Se omitido a atual é usada, essa é a url que vai em ?next={callbackUrl}. **"para onde voltar depois da autenticação"**.
- `targetUrl` — string(opcional): URL da página a qual o usuário será redirecionado. Se não informado ele não é redirecionado. **"pra onde mandar quando a permissão não existe"**.
- `requiredRoles` — string[]: lista de roles (ex.: `["admin", "manager"]`).
- `checkStrategy` — “any” | “all” (opcional) : se precisa de **qualquer** ou **todas** as permissões (default: `"all"`).
- `mode` — [”block” | “mask"](opcional): URL de destino para onde o usuário deve voltar(ser redirecionado) após o sucesso. Deve ser validada (usar caminhos relativos ou validados para evitar open-redirect).  Mask (Default)
    - Block: default não renderizada o children, quando negado (em tese essa vai ser a opção mais segura, porém menos agradável)
    - Mask: Mantém renderizado o children com internet e pointer events none + aria hidden e um blur por cima
- `icon` — ReactNode (opcional): ícone ilustrativo (cadeado, carteira, etc.). Se não informado, usa um padrão
- `redirectDelayMs` — number | null (opcional): tempo em ms antes de tentar o redirect automático. `null` = nunca redirecionar automaticamente. Se não informado = undefined, então ir instantaneamente
- `message` — string(opcional): Mensagem que diz ao usuário que ele será redirecionado para a determinada página, se não fornecida usar uma padrão.
- `actions` — array de ReactNode (opcional): botões/links extras a mostrar (ex.: “Entrar com Google”, “Entrar com GitHub”, “Falar com suporte”).
- `className` — string (opcional): para estilização extra.

```jsx
<Guard 
	callbackUrl="/example" 
	targetUrl="/login" 
	redirectDelayMs={undefined} 
	requiredRoles={["admin"]}
>
	<Conteudo/>
</Guard>
```
