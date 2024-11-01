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
     - [Edição de registros com formulário polimorfo](#edi%C3%A7%C3%A3o-de-registros-com-formul%C3%A1rio-polimorfo "Edição de registros com formulário polimorfo")
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
3. **Testes e Simulações de Interface**
   - **Preenchimento Automático de Formulários com JavaScript Nativo**
     - [Preencher diferentes tipos de campos usando o console do navegador](#preencher-diferentes-tipos-de-campos-usando-o-console-do-navegador "Preencher diferentes tipos de campos usando o console do navegador")

---

Este item "Scripts Prontos: Backend e Frontend" contém scripts prontos para diversos cenários, como formulários com integração completa entre frontend e backend, listagem de itens, edição, e exclusão com DataTables e outras funcionalidades. A ideia é que essa seção funcione como um guia rápido para montar um CRUD completo ou mesmo pacotes prontos que você pode adaptar e reutilizar facilmente.

---

## Edição de registros com formulário polimorfo

Para fazer com que o campo "UserGridFullName" do formulário se torne polimorfo, ou seja, ele seja preenchido com o valor já existente quando estiver no modo de edição, e fique vazio no modo de registro, você pode fazer uma pequena alteração no valor inicial do campo. Isso pode ser feito verificando o valor da variável `polymorphic`. Se for igual a `2`, você define o valor do campo como `{admin.full_name}`, caso contrário, deixa o valor como uma string vazia. Veja como você pode modificar o código:

> ### ( i ) Campo de texto `type="text"`.

```jsx
// ... outras linhas ...
<Form.Group className="mb-3" as={Col} controlId="UserGridFullName">
    <Form.Label>Nome completo</Form.Label>
    <Form.Control
        type="text"
        size="sm"
        placeholder="Nome do usuário do sistema..."
        value={polymorphic === 2 ? (fullUsername || admin.full_name) : fullUsername} // Aqui o valor é polimorfo
        onChange={(e) => setFullUsername(e.target.value)}
        ref={fullUsernameInputRef}
    />
</Form.Group>
// ... outras linhas ...
```

### Explicação:
- `polymorphic === 2 ? (fullUsername || admin.full_name) : fullUsername`: 
  - Se `polymorphic` for igual a `2` (modo edição), o campo será preenchido com o valor de `admin.full_name`, a menos que o estado `fullUsername` já tenha sido alterado.
  - Se `polymorphic` for diferente de `2` (modo registro), o campo será preenchido apenas com o valor da variável `fullUsername`, que inicialmente está vazia.
  

Isso garante que, ao editar um administrador, o campo já venha preenchido com o nome completo, mas que também permita alterar o valor durante a edição. No modo de registro, o campo aparecerá vazio como esperado.

> ### ( i ) Campo de seleção `<select>...</select>`.

Para aplicar a mesma lógica de polimorfismo ao campo `<select>`, a abordagem é similar à usada no campo de texto. Você precisa inicializar o estado do `level` com o valor correto no modo de edição, garantindo que ele possa ser editado normalmente.

### Modificação para o campo `<select>`:

```jsx
// ... outras linhas ...
const [level, setLevel] = useState('');

// Usar useEffect para inicializar o valor de level no modo de edição
useEffect(() => {
    if (polymorphic === 2 && admin?.level !== undefined) {
        setLevel(admin.level); // Inicializa apenas se o level do admin estiver disponível
    }
}, [polymorphic, admin]);

// ... outras linhas ...

<Form.Select
    size="sm"
    value={level}
    onChange={(e) => setLevel(e.target.value)} // Permite editar o nível
    ref={levelInputRef}
>
    <option value="">&raquo; Selecione &laquo;</option>
    <option value="0">Ilimitado</option>
    <option value="1">Limitado</option>
</Form.Select>
// ... outras linhas ...
```

### Explicação:
- **`useState` inicial vazio**: O estado `level` é inicializado com uma string vazia para garantir que o campo `<select>` possa ser editado posteriormente.
  
- **`useEffect` para inicializar o valor**: Quando o formulário está no modo de edição (`polymorphic === 2`), o valor do `level` é carregado a partir do objeto `admin`, mas isso ocorre apenas uma vez (quando o formulário é renderizado). Isso evita que o valor seja sobrescrito durante a interação do usuário.
  
- **Controle do valor via `onChange`**: O campo `<select>` usa o estado `level` para controlar o valor selecionado, e o `onChange` atualiza o estado sempre que o usuário fizer uma nova escolha.

Assim como no campo de texto, o valor inicial será carregado no modo de edição, mas o usuário ainda poderá modificar a seleção.

> ### ( i ) Estrutura com vários campos

Sim, a estrutura que você usou está correta para inicializar um campo de formulário baseado no valor de `admin` quando está no modo de edição. No entanto, se você tiver **cinco campos**, você precisa garantir que cada um seja controlado de forma independente, assim como fizemos para o campo `level`. Cada campo deve ter seu próprio estado e lógica de inicialização dentro do `useEffect`, mas a estrutura geral é a mesma.

Vou mostrar como ficaria com cinco campos no total, seguindo a mesma lógica para cada um.

### Exemplo com cinco campos:

```jsx
// ... outras linhas ...
const [fullUsername, setFullUsername] = useState('');
const [email, setEmail] = useState('');
const [role, setRole] = useState('');
const [level, setLevel] = useState('');
const [status, setStatus] = useState('');

// Usar useEffect para inicializar os valores dos campos no modo de edição
useEffect(() => {
    if (polymorphic === 2) {
        if (admin?.full_name) setFullUsername(admin.full_name);
        if (admin?.email) setEmail(admin.email);
        if (admin?.role) setRole(admin.role);
        if (admin?.level !== undefined) setLevel(admin.level); // Verifica se não é undefined
        if (admin?.status !== undefined) setStatus(admin.status); // Mesmo tratamento para status
    }
}, [polymorphic, admin]);

// ... outras linhas ...

<Form.Group className="mb-3" as={Col} controlId="UserGridFullName">
    <Form.Label>Nome completo</Form.Label>
    <Form.Control
        type="text"
        size="sm"
        value={fullUsername}
        onChange={(e) => setFullUsername(e.target.value)}
        placeholder="Nome do usuário do sistema..."
    />
</Form.Group>

<Form.Group className="mb-3" as={Col} controlId="UserGridEmail">
    <Form.Label>Email</Form.Label>
    <Form.Control
        type="email"
        size="sm"
        value={email}
        onChange={(e) => setEmail(e.target.value)}
        placeholder="Email do usuário..."
    />
</Form.Group>

<Form.Group className="mb-3" as={Col} controlId="UserGridRole">
    <Form.Label>Função</Form.Label>
    <Form.Select
        size="sm"
        value={role}
        onChange={(e) => setRole(e.target.value)}
    >
        <option value="">&raquo; Selecione &laquo;</option>
        <option value="admin">Administrador</option>
        <option value="editor">Editor</option>
    </Form.Select>
</Form.Group>

<Form.Group className="mb-3" as={Col} controlId="UserGridLevel">
    <Form.Label>Nível de Acesso</Form.Label>
    <Form.Select
        size="sm"
        value={level}
        onChange={(e) => setLevel(e.target.value)}
    >
        <option value="">&raquo; Selecione &laquo;</option>
        <option value="0">Ilimitado</option>
        <option value="1">Limitado</option>
    </Form.Select>
</Form.Group>

<Form.Group className="mb-3" as={Col} controlId="UserGridStatus">
    <Form.Label>Status</Form.Label>
    <Form.Select
        size="sm"
        value={status}
        onChange={(e) => setStatus(e.target.value)}
    >
        <option value="">&raquo; Selecione &laquo;</option>
        <option value="active">Ativo</option>
        <option value="inactive">Inativo</option>
    </Form.Select>
</Form.Group>
// ... outras linhas ...
```

### Explicação:
1. **Estados separados**: Cada campo tem seu próprio estado controlado (`fullUsername`, `email`, `role`, `level`, `status`).
2. **`useEffect` inicializa os valores no modo de edição**: O `useEffect` verifica se estamos no modo de edição (`polymorphic === 2`). Se for o caso, ele inicializa os estados com os valores que vierem do objeto `admin`.
3. **Campos `<select>` e `<input>`**: Tanto os campos de texto quanto os selects são controlados da mesma forma, com o `value` ligado ao estado e `onChange` atualizando o estado conforme o usuário interage com o formulário.

### Dica:
Lembre-se de garantir que os valores vindos de `admin` sejam válidos antes de inicializar o estado (como fizemos com `admin?.level !== undefined`), para evitar erros caso algum valor seja `null` ou `undefined`.

### Evitar problema com a validação do campo em modo Edição

Esse é um problema ocorre no modo de edição, quando o valor inicial do campo é preenchido diretamente com `admin.full_name`, e não é atualizado o estado `fullUsername` (controlado pelo hook `useState`). Portanto, mesmo que o campo pareça preenchido visualmente, a validação está verificando o estado, que permanece vazio até que o usuário interaja com o campo.

Para corrigir isso, você pode inicializar o estado `fullUsername` com o valor de `admin.full_name` quando o formulário estiver no modo de edição. Uma forma de garantir que o campo seja validado corretamente é usar um `useEffect` que observe a mudança no valor de `polymorphic` e inicialize `fullUsername` com o valor correto ao entrar no modo de edição.

Aqui está a modificação:

### Modificação no uso de `useEffect`:

```jsx
// ... outras linhas ...
const [fullUsername, setFullUsername] = useState('');

// Usar useEffect para inicializar o valor de fullUsername no modo de edição
useEffect(() => {
    if (polymorphic === 2 && admin?.full_name) {
        setFullUsername(admin.full_name); // Inicializar fullUsername no modo de edição
    }
}, [polymorphic, admin]);

// ... outras linhas ...

async function handleSubmitForm(e) {
    e.preventDefault();

    // Verificar se o campo "Nome completo do Usuário do sistema" está vazio.
    if (fullUsername.trim() === '') {
        fullUsernameInputRef.current.focus();
        return;
    }

// ... outras linhas ...
```

### Explicação:

- O `useEffect` é usado para monitorar a variável `polymorphic` e o objeto `admin`. Se o formulário estiver no modo de edição (`polymorphic === 2`) e houver um valor em `admin.full_name`, ele inicializa o estado `fullUsername` com o nome completo do administrador.
- Dessa forma, o estado `fullUsername` será preenchido corretamente no momento em que o formulário for renderizado no modo de edição, e a validação irá funcionar corretamente, pois `fullUsername` terá um valor não vazio.

Com essa alteração, o valor do campo será sempre refletido corretamente no estado do componente, permitindo que a validação funcione conforme esperado, tanto para registro quanto para edição.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](./README.md#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](./README.md#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

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

## Preencher diferentes tipos de campos usando o console do navegador

Ótima ideia! Vamos criar um exemplo mais específico, preenchendo os campos de formulário com base nos `ids` que você mencionou. Aqui está o script atualizado:

### HTML Exemplo:
Aqui está uma estrutura de HTML para o formulário que você poderia usar:

```html
<form>
  <div>
    <label for="formGridFullName">Nome Completo</label>
    <input type="text" id="formGridFullName" placeholder="Nome Completo">
  </div>
  
  <div>
    <label for="formGridEmail">Email</label>
    <input type="email" id="formGridEmail" placeholder="Email">
  </div>
  
  <div>
    <label for="formGridBiologicalSex">Sexo Biológico</label>
    <select id="formGridBiologicalSex">
      <option value="" disabled selected>Selecione</option>
      <option value="masculino">Masculino</option>
      <option value="feminino">Feminino</option>
    </select>
  </div>
  
  <div>
    <label for="formGridPassword">Senha</label>
    <input type="password" id="formGridPassword" placeholder="Senha">
  </div>
  
  <div>
    <label for="custom-switch">Aceitar Termos</label>
    <input type="checkbox" id="custom-switch">
  </div>
</form>
```

### JavaScript para Preencher os Campos:
Aqui está o script que você pode executar no console do navegador para preencher esses campos:

```javascript
// Preencher campo de texto (Nome Completo)
document.querySelector('#formGridFullName').value = "João da Silva";

// Preencher campo de email
document.querySelector('#formGridEmail').value = "joao.silva@exemplo.com";

// Selecionar opção no campo de seleção (Sexo Biológico)
document.querySelector('#formGridBiologicalSex').value = "masculino"; 
document.querySelector('#formGridBiologicalSex').dispatchEvent(new Event('change')); // dispara o evento de mudança

// Preencher campo de senha
document.querySelector('#formGridPassword').value = "senhaSegura123";

// Marcar o checkbox (custom switch)
document.querySelector('#custom-switch').checked = true;
document.querySelector('#custom-switch').dispatchEvent(new Event('change')); // dispara o evento de mudança

// Disparar eventos de input e change para garantir que a interface reaja (caso esteja usando React/Angular/etc)
document.querySelectorAll('input, select').forEach(el => {
  el.dispatchEvent(new Event('input', { bubbles: true }));
  el.dispatchEvent(new Event('change', { bubbles: true }));
});
```

### Explicação:

1. **Nome Completo (`id="formGridFullName"`)**: O campo de texto é preenchido com o valor `"João da Silva"`.
2. **Email (`id="formGridEmail"`)**: O campo de email é preenchido com `"joao.silva@exemplo.com"`.
3. **Sexo Biológico (`id="formGridBiologicalSex"`)**: O campo `select` é preenchido com a opção `"masculino"`. Para garantir que o evento de seleção seja processado corretamente, o evento `change` é disparado.
4. **Senha (`id="formGridPassword"`)**: O campo de senha é preenchido com `"senhaSegura123"`.
5. **Switch (Checkbox) (`id="custom-switch"`)**: O checkbox é marcado (`checked = true`), e o evento `change` é disparado para simular a interação do usuário.

Esse código simula a ação do usuário preenchendo os campos e disparando os eventos necessários para que a interface do formulário responda como se fosse uma interação real.

### Execução:
Você pode simplesmente copiar e colar esse código no console do navegador enquanto estiver na página com o formulário, e o JavaScript preencherá os campos automaticamente.

Caso tenha mais campos ou queira ajustes, é só me avisar!

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](./README.md#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](./README.md#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

