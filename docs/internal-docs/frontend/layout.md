# Layout

## Auth

### Visão Geral

A página de autenticação será uma interface moderna e intuitiva com dois componentes principais: login e registro. A transição entre esses componentes será realizada com Framer Motion.

### Componentes

- **Container Principal**: Card nas laterais, cada lateral tendo seu componente, esquerda registro e direita login.
- **Toggle Switch**: Botão para alternar entre login e registro
- **Formulários**:
    - **Login**
    - **Registro**
- **Elementos Adicionais**:
    - Opção "Esqueci minha senha"
    - Login social (Google, Instagram)
    - Mensagens de erro/feedback
    - Indicador de carregamento

### Animações (Framer Motion)

- Transição deslizante entre os formulários de login e registro
- Animação de carregamento durante processos de autenticação

### Fluxo de Redirecionamento

1. Usuário tenta acessar uma página protegida
2. Sistema redireciona para página de autenticação
3. URL contém parâmetro `?next=/caminho/original`
4. Após login bem-sucedido:
    - Sistema verifica existência do parâmetro `next`
    - Se existir, redireciona o usuário para o caminho especificado
    - Se não existir, redireciona para a página inicial/dashboard, etc…

### Segurança

- Validação de dados em tempo real (zod)
- Limitar quantidade de requisições em um intervalo de tempo (para evitar spam)
