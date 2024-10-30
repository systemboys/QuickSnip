> ### QuickSnip

# Scripts Prontos: Backend e Frontend

---

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
<!-- /Botões de navegação -->

Exemplos de CRUD (Create, Read, Update, Delete) com integração de frontend e backend, utilizando React.JS no frontend e Prisma no backend.

## Conteúdo
1. **Exemplos CRUD com React e Prisma**
   - **Formulário de Cadastro (Create)**
     - Formulário simples de cadastro com validação de campos
     - Envio de dados para o backend via API (fetch ou Axios)
     - Armazenamento de dados no banco usando Prisma
   - **Listagem de Itens com DataTable (Read)**
     - Integração com biblioteca DataTable (React Table, Material UI, etc.)
     - Consulta de dados no backend (Prisma findMany)
     - Paginação e filtros de dados
   - **Edição de Registro (Update)**
     - Edição de itens com dados predefinidos no formulário
     - Atualização dos registros no backend via API
     - Validação de dados antes da atualização
   - **Exclusão de Registro (Delete)**
     - Botão de exclusão com confirmação
     - Exclusão de registros via API e atualização da lista no frontend
     - Tratamento de erros e feedback ao usuário
   - **Integração Completa de Frontend e Backend**
     - Exemplo completo de um CRUD (Create, Read, Update, Delete)
     - Reutilização de componentes e lógica no frontend
     - Organização de rotas e controllers no backend
       - [Refatoração de rotas e uso de controllers](#refatora%C3%A7%C3%A3o-de-rotas-e-uso-de-controllers "Refatoração de rotas e uso de controllers")
       - Como mover a lógica de rotas para controllers para melhor organização
       - Vantagens da modularização e manutenibilidade do código
2. **Trabalhando Fenestra, API de janelas para react/redux**
   - **Corrigindo problemas**
     - Formulário simples de cadastro com validação de campos

---

Este item "Scripts Prontos: Backend e Frontend" contém scripts prontos para diversos cenários, como formulários com integração completa entre frontend e backend, listagem de itens, edição, e exclusão com DataTables e outras funcionalidades. A ideia é que essa seção funcione como um guia rápido para montar um CRUD completo ou mesmo pacotes prontos que você pode adaptar e reutilizar facilmente.

---

## Refatoração de rotas e uso de controllers

Sim, é totalmente possível adicionar **controllers** no seu projeto futuramente, mesmo que você já tenha definido as rotas diretamente em um arquivo de rotas, como o `routes.ts`. Adicionar controllers ajuda a manter o código mais organizado e modularizado, especialmente à medida que o sistema cresce em complexidade.

Atualmente, você provavelmente está definindo suas rotas diretamente no arquivo de rotas, algo como:

```ts
import { Router } from 'express';

const router = Router();

router.get('/users', (req, res) => {
    // Lógica diretamente aqui
    res.send('List of users');
});

router.post('/users', (req, res) => {
    // Lógica diretamente aqui
    res.send('User created');
});

export default router;
```

### Como adicionar **controllers** mais tarde

Para mover a lógica para um **controller**, você só precisa criar arquivos de **controllers** e referenciar esses controllers nas suas rotas. Aqui vai um exemplo de como refatorar seu código para usar **controllers**.

#### 1. Criar o arquivo do controller (ex: `user.controller.ts`):

```ts
// user.controller.ts
import { Request, Response } from 'express';

export const getUsers = (req: Request, res: Response) => {
    // Lógica de obtenção de usuários
    res.send('List of users from controller');
};

export const createUser = (req: Request, res: Response) => {
    // Lógica de criação de usuário
    res.send('User created from controller');
};
```

#### 2. Atualizar o arquivo de rotas (`routes.ts`):

Agora, você pode importar os métodos do controller e vinculá-los às rotas:

```ts
// routes.ts
import { Router } from 'express';
import { getUsers, createUser } from './controllers/user.controller'; // Importar o controller

const router = Router();

// Usar o controller nas rotas
router.get('/users', getUsers);
router.post('/users', createUser);

export default router;
```

### Vantagens de usar **controllers**:
1. **Organização**: Você separa a lógica de negócios das rotas, facilitando a leitura e manutenção.
2. **Reusabilidade**: Pode reusar a lógica de controle em diferentes rotas, evitando duplicação de código.
3. **Testabilidade**: Fica mais fácil testar a lógica dos controllers isoladamente, sem a necessidade de configurar toda a rota.

### Conclusão
Você pode começar com rotas simples e mover a lógica para controllers quando o projeto crescer ou quando sentir que é necessário. Isso não vai causar nenhum problema para o seu projeto e, na verdade, vai melhorar a organização do código a longo prazo.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](./README.md#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](./README.md#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

