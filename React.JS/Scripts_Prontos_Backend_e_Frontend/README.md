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
     - [`Gravando` dados do formulário na tabela usando o `ORM Prisma`](#gravando-dados-do-formul%C3%A1rio-na-tabela-usando-o-orm-prisma "Gravando dados do formulário na tabela usando o ORM Prisma")
   - **Listagem de Itens com DataTable (Read)**
     - Integração com biblioteca DataTable (React Table, Material UI, etc.)
     - Consulta de dados no backend (Prisma findMany)
     - [Implementação de Indicador de Carregamento Centralizado para DataTable com React e CSS](#implementa%C3%A7%C3%A3o-de-indicador-de-carregamento-centralizado-para-datatable-com-react-e-css "Implementação de Indicador de Carregamento Centralizado para DataTable com React e CSS")
     - Paginação e filtros de dados
     - [Formatação de Dados da API em um Array no Formato Específico (`JSON`)](#formata%C3%A7%C3%A3o-de-dados-da-api-em-um-array-no-formato-espec%C3%ADfico-json "Formatação de Dados da API em um Array no Formato Específico (JSON)")
   - **Consulta de Registro Único (Single)**
     - [Rota Genérica para Consulta de Registro Único por ID](#rota-gen%C3%A9rica-para-consulta-de-registro-%C3%BAnico-por-id "Rota Genérica para Consulta de Registro Único por ID")
     - [Exemplo de Componente React para Exibir Detalhes de um Registro](#exemplo-gen%C3%A9rico-de-requisi%C3%A7%C3%A3o-no-frontend "Exemplo de Componente React para Exibir Detalhes de um Registro")
   - **Edição de Registro (Update)**
     - [Edição de registros com formulário polimorfo](#edi%C3%A7%C3%A3o-de-registros-com-formul%C3%A1rio-polimorfo "Edição de registros com formulário polimorfo")
     - Edição de itens com dados predefinidos no formulário
     - Atualização dos registros no backend via API
     - Validação de dados antes da atualização
   - **Exclusão de Registro (Delete)**
     - [Botão de exclusão com confirmação](#bot%C3%A3o-de-exclus%C3%A3o-com-confirma%C3%A7%C3%A3o "Botão de exclusão com confirmação")
     - Exclusão de registros via API e atualização da lista no frontend
     - [Exemplo Genérico de Rota DELETE com Parâmetros Dinâmicos e Filtragem](#exemplo-gen%C3%A9rico-de-rota-delete-com-par%C3%A2metros-din%C3%A2micos-e-filtragem "Exemplo Genérico de Rota DELETE com Parâmetros Dinâmicos e Filtragem")
     - [Rota Genérica de Exclusão via ID e Integração com Frontend React](#rota-gen%C3%A9rica-de-exclus%C3%A3o-via-id-e-integra%C3%A7%C3%A3o-com-frontend-react "Rota Genérica de Exclusão via ID e Integração com Frontend React")
     - Tratamento de erros e feedback ao usuário
   - **Integração Completa de Frontend e Backend**
     - Exemplo completo de um CRUD (Create, Read, Update, Delete)
       - [Rota de Criação de Registro (Create) com Prisma e Requisição no Frontend](#rota-de-cria%C3%A7%C3%A3o-de-registro-create-com-prisma-e-requisi%C3%A7%C3%A3o-no-frontend "Rota de Criação de Registro (Create) com Prisma e Requisição no Frontend")
     - Reutilização de componentes e lógica no frontend
     - Organização de rotas e controllers no backend
       - [Refatoração de rotas e uso de controllers](#refatora%C3%A7%C3%A3o-de-rotas-e-uso-de-controllers "Refatoração de rotas e uso de controllers")
       - Como mover a lógica de rotas para controllers para melhor organização
       - Vantagens da modularização e manutenibilidade do código
       - [Rota com Parâmetro Dinâmico e Filtragem por Chave Estrangeira no Prisma](#rota-com-par%C3%A2metro-din%C3%A2mico-e-filtragem-por-chave-estrangeira-no-prisma "Rota com Parâmetro Dinâmico e Filtragem por Chave Estrangeira no Prisma")
         - [Requisição da Rota no Componente React](#instru%C3%A7%C3%B5es-para-requisi%C3%A7%C3%A3o-da-rota-no-frontend-react "Requisição da Rota no Componente React")
2. **Trabalhando Fenestra, API de janelas para react/redux**
   - **Corrigindo problemas**
     - Formulário simples de cadastro com validação de campos
   - **Manipulação de Estilos e Classes em Componentes Modais**
     - [Adicionando Classe na Div Mãe](#adicionando-classe-na-div-m%C3%A3e "Adicionando Classe na Div Mãe")
3. **Testes e Simulações de Interface**
   - **Preenchimento Automático de Formulários com JavaScript Nativo**
     - [Preencher diferentes tipos de campos usando o console do navegador](#preencher-diferentes-tipos-de-campos-usando-o-console-do-navegador "Preencher diferentes tipos de campos usando o console do navegador")
4. **Configuração e Segurança em Projetos React**
   - #### **[Uso de Variáveis de Ambiente com Arquivo .env no React](#uso-de-vari%C3%A1veis-de-ambiente-com-arquivo-env-no-react-1 "Uso de Variáveis de Ambiente com Arquivo .env no React")**
     - [Estrutura e convenções do arquivo `.env` com `REACT_APP_`](#1-estrutura-e-conven%C3%A7%C3%B5es "Estrutura e Convenções")
     - [Acessando variáveis de ambiente no código usando `process.env`](#2-utiliza%C3%A7%C3%A3o-no-c%C3%B3digo "Utilização no Código")
     - [Adicionando `.env` ao `.gitignore` para evitar exposição](#3-adicionando-o-arquivo-ao-gitignore "Adicionando o Arquivo ao .gitignore")
     - [Configuração para diferentes ambientes (desenvolvimento, produção, testes)](#4-vari%C3%A1veis-diferentes-para-ambientes-diferentes "Variáveis Diferentes para Ambientes Diferentes")
     - [Considerações de segurança e limites (ex.: não incluir dados sensíveis no frontend)](#5-limita%C3%A7%C3%B5es-e-avisos "Limitações e Avisos")
     - [Gerenciamento de URLs de API por Ambiente com Variáveis de Ambiente no React](#gerenciamento-de-urls-de-api-por-ambiente-com-vari%C3%A1veis-de-ambiente-no-react "Gerenciamento de URLs de API por Ambiente com Variáveis de Ambiente no React")
   - **Uso de Dados do `localStorage` em Componentes React**
     - **[Acessando `companyId` do `localStorage` para Requisições API](#guia-como-acessar-dados-do-localstorage-para-requisi%C3%A7%C3%B5es-api-em-componentes-react "Acessando `companyId` do `localStorage` para Requisições API")**
       - [Instruções para acessar dados como `companyId` do `localStorage` em componentes React](#passo-a-passo-1 "Instruções para acessar dados como `companyId` do `localStorage` em componentes React")
       - [Exemplo genérico para reutilização em múltiplos componentes](#exemplo-gen%C3%A9rico "Exemplo genérico para reutilização em múltiplos componentes")
       - [Considerações de segurança e verificação de dados antes do uso](#reutiliza%C3%A7%C3%A3o-em-outros-componentes "Considerações de segurança e verificação de dados antes do uso")

---

Este item "Scripts Prontos: Backend e Frontend" contém scripts prontos para diversos cenários, como formulários com integração completa entre frontend e backend, listagem de itens, edição, e exclusão com DataTables e outras funcionalidades. A ideia é que essa seção funcione como um guia rápido para montar um CRUD completo ou mesmo pacotes prontos que você pode adaptar e reutilizar facilmente.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Gravando dados do formulário na tabela usando o ORM Prisma

Para fazer o formulário enviar os dados para a rota `/addAdmins` a fim de gravar as informações na tabela "admins", você precisa fazer alguns ajustes na função de envio de dados. Aqui estão os passos detalhados para garantir que tudo funcione corretamente:

### Passo 1: Configurar o envio de dados para a API

Na função `handleSubmitForm`, após a validação dos campos, você pode enviar os dados para a rota `/addAdmins` usando `fetch` para realizar uma solicitação POST com o corpo da requisição em formato JSON. Veja como você pode fazer isso:

1. Adicione a função de envio de dados com `fetch`.
2. Capture a resposta e lide com os possíveis erros.

Aqui está o código atualizado:

```jsx
// Interceptar o evento do submit.
async function handleSubmitForm(e) {
    e.preventDefault();

    // Verificar se o campo "Nome completo do Usuário do sistema" está vazio.
    if (fullUsername.trim() === '') {
        fullUsernameInputRef.current.focus();
        return;
    }
    // Verificar se o campo "Email do usuário" está vazio.
    if (email.trim() === '') {
        emailInputRef.current.focus();
        return;
    }
    // Verificar se o campo "Sexo Biológico" está vazio.
    if (biologicalSex.trim() === '') { // Alterado para biologicalSex
        biologicalSexInputRef.current.focus();
        return;
    }
    // Verificar se o campo "Usuário do sistema" está vazio.
    if (userName.trim() === '') {
        userNameInputRef.current.focus();
        return;
    }
    // Verificar se o campo "Senha do Usuário do sistema" está vazio.
    if (password.trim() === '') {
        passwordInputRef.current.focus();
        return;
    }

    // -------------------------- Gravar dados---------------------------
    // Preparar o objeto com os dados a serem enviados
    const formData = {
        full_name:      fullUsername,
        email:          email,
        biological_sex: biologicalSex, // Corrigido
        username:       userName,
        password:       password,
        level:          parseInt(level), // Recebe valor INT
    };

    try {
        // Fazer a solicitação POST para a API
        const response = await fetch('http://localhost:3000/addAdmins', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify(formData) // Enviar o objeto como JSON
        });

        if (response.ok) {
            const data = await response.json();
            console.log('Admin adicionado com sucesso:', data);

            // Resetar o formulário após o envio bem-sucedido
            handleReset();
        } else {
            const errorData = await response.json();
            console.error('Erro ao adicionar admin:', errorData);
            alert('Erro ao adicionar admin. Verifique os dados e tente novamente.');
        }
    } catch (error) {
        console.error('Erro de rede ou servidor:', error);
        alert('Erro de rede ou servidor. Tente novamente mais tarde.');
    }
    // ------------------------- /Gravar dados---------------------------

    // Exibir no console os valores obitidos nos campos.
    // console.log("Submit", { fullUsername, email, biologicalSex, userName, password, level });

    // Resetar após enviar os dados.
    handleReset();
}
```

### Passo 2: Verificar o envio de dados

Certifique-se de que sua API esteja rodando no servidor local e que a rota `POST /addAdmins` esteja funcionando corretamente. Quando o formulário for enviado com sucesso, os dados serão enviados para a API, e o administrador será adicionado ao banco de dados.

### Passo 3: Lidando com o `level`

No código do frontend, está sendo enviado o campo `level` com um valor inteiro (`int`), pois um seletor para níveis sendo definido com números inteiros, o valor deve ser recebido com `parseInt(level)`.

### Passo 4: Mensagens de feedback para o usuário

Depois de adicionar o administrador com sucesso ou se houver algum erro, você pode mostrar mensagens para o usuário através de `alert()` ou outros componentes de feedback mais elaborados, como `toasts` ou `modals`, dependendo da sua necessidade.

Agora, o seu formulário enviará corretamente as informações para a rota `/addAdmins`, e a rota salvará os dados no banco de dados.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Implementação de Indicador de Carregamento Centralizado para DataTable com React e CSS

Passos com as modificações necessárias, para inplementação de indicador de carregamento.

### Passo 1: Adicionar um Indicador de Carregamento

1. **Crie um componente de `Loader`**: Adicione esse componente logo após as importações no seu arquivo antes da exportação do seu componente para exibir uma animação de carregamento enquanto os dados estão sendo carregados.

    ```jsx
    // Componente de carregamento
    const Loader = () => (
      <div className={styles.loaderContainer}>
        <div className={styles.loader}></div>
      </div>
    );
    ```

2. **Modifique o `return` do componente `ListUsers`**: Adicione o componente `Loader` antes da tabela para que ele seja exibido enquanto `dataLoaded` estiver `false`.

    ```jsx
    return (
        <Container>
            {!dataLoaded && <Loader />} {/* Exibe o loader se os dados ainda não foram carregados */}
            {dataLoaded && (
                <>
                    {/* ...restante do conteúdo */}
                </>
            )}
        </Container>
    );
    ```

### Passo 2: Adicionar Estilos para o Indicador de Carregamento

1. **Adicione o seguinte CSS** no arquivo `styles.module.css` para estilizar o componente `Loader`:

    ```css
    .loaderContainer {
        display: flex;
        justify-content: center;
        align-items: center;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(255, 255, 255, 0.8); /* Fundo semitransparente */
        z-index: 9999;
    }
    
    .loader {
        border: 16px solid #f3f3f3;
        border-top: 16px solid #3498db;
        border-radius: 50%;
        width: 120px;
        height: 120px;
        animation: spin 2s linear infinite;
    }
    
    @keyframes spin {
        0% { transform: rotate(0deg); }
        100% { transform: rotate(360deg); }
    }
    ```

Essas são as únicas modificações necessárias!

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Formatação de Dados da API em um Array no Formato Específico (JSON)

Para formatar os dados retornados pela consulta em um array no formato desejado, você pode fazer o seguinte:

```jsx
// Realizar a chamada à API para buscar dados associados ao parâmetro especificado.
const [listBackground, setListBackground] = useState([]);
useEffect(() => {
  Api.get(`/backgroundsId/${category}`).then((res) => {
    const formattedData = res.data.map((item) => ({
      image: `/img/backgrounds/${item.thumb}`,
      title: item.title,
      category: item.category,
      date: item.date,
    }));
    setListBackground(formattedData);
  });
}, []);

console.log(listBackground); // Retorno no console.
```

> ( ! ) A chamada à API deve ficar dentro do componente!

Aqui, usamos o método `map()` para percorrer cada item retornado pela consulta e criar um novo objeto no formato desejado. Em seguida, definimos o estado `listBackground` com o array `formattedData`, que contém os dados formatados.

Certifique-se de que as propriedades `thumb`, `title`, `category` e `date` correspondam aos nomes corretos dos campos na resposta da API.

> Esse código faz uma chamada à API para obter dados da tabela "backgroundsId" com base na categoria fornecida. Ele usa os hooks `useState` e `useEffect` para fazer a chamada da API e formatar os dados recebidos.
>
> A chamada à API é feita através do `Api.get()` e usa o caminho `/backgroundsId/${category}` para buscar os dados correspondentes à categoria especificada.
>
> Quando a resposta da API é recebida, o código formata os dados retornados usando o método `map()`. Cada item retornado é transformado em um objeto com as propriedades `image`, `title`, `category` e `date`.
>
> Em seguida, os dados formatados são atribuídos ao estado `listBackground` usando a função `setListBackground`. Isso atualiza o estado com os dados obtidos da API.
>
> O `useEffect` é usado para executar esse código sempre que a categoria for alterada. A dependência vazia `[]` no final indica que o efeito deve ser executado apenas uma vez, após a montagem do componente.
>
> Por fim, o `console.log(listBackground)` é usado para exibir o valor atual de `listBackground` no console. Isso pode ser útil para verificar se os dados foram obtidos corretamente e para depurar eventuais problemas.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Rota Genérica para Consulta de Registro Único por ID

Para criar uma rota genérica que busque um registro específico pelo `ID`, vou apresentar um exemplo que você pode reutilizar em diferentes componentes. Esta rota irá fazer uma consulta `GET` baseada no `ID` do registro e retornará os dados desse registro em formato JSON. A lógica do frontend em React também é genérica, para que você possa adaptá-la a qualquer componente "single" que precise exibir detalhes de um item específico.

### **Rota no Backend (Node.js/Express)**

Abaixo, uma rota genérica `GET` para buscar um registro específico em uma tabela do banco de dados pelo `ID` usando Prisma:

```ts
// Rota genérica para obter um registro pelo ID
routes.get('/getEntity/:id', async (req, res) => {
    const { id } = req.params;

    try {
        // Buscar o registro no banco de dados
        const entity = await prisma.entity.findUnique({
            where: { id: parseInt(id) },
        });

        if (!entity) {
            return res.status(404).json({ error: 'Registro não encontrado' });
        }

        // Retornar o registro encontrado
        return res.status(200).json(entity);
    } catch (error) {
        console.error('Erro ao buscar registro:', error);
        return res.status(500).json({ error: 'Erro ao buscar registro' });
    }
});
```

#### **Instruções para Adaptação**:
- **Nome da Rota**: Substitua `'/getEntity/:id'` pelo endpoint desejado, como `'/getUser/:id'` ou `'/getProduct/:id'`.
- **Tabela (Entidade)**: Substitua `entity` no código Prisma pelo nome da tabela real definida no seu `schema.prisma` (ex.: `prisma.users`, `prisma.products`, etc.).

### Como Requisitar a Rota no Frontend (React)

No frontend, você pode fazer uma requisição `GET` para essa rota passando o `ID` do registro que deseja obter.

### **Exemplo Genérico de Requisição no Frontend**

Abaixo, uma função genérica que realiza a requisição e busca os dados do registro pelo `ID`:

```jsx
import React, { useEffect, useState } from 'react';

function SingleEntityComponent({ id }) {
    const [entityData, setEntityData] = useState(null);
    const [error, setError] = useState(null);

    useEffect(() => {
        async function fetchData() {
            try {
                const response = await fetch(`http://localhost:5000/getEntity/${id}`);
                if (!response.ok) throw new Error('Erro ao buscar dados');

                const data = await response.json();
                setEntityData(data);
            } catch (error) {
                console.error('Erro de rede ou servidor:', error);
                setError('Erro ao buscar dados. Tente novamente mais tarde.');
            }
        }

        if (id) {
            fetchData(); // Executa a requisição ao montar o componente ou quando o ID muda
        }
    }, [id]);

    if (error) return <p>{error}</p>;

    return (
        <div>
            {entityData ? (
                <div>
                    <h2>{entityData.title}</h2> {/* Exemplo: ajuste conforme os campos */}
                    <p>{entityData.description}</p> {/* Exemplo: ajuste conforme os campos */}
                    {/* Renderize outros dados do registro */}
                </div>
            ) : (
                <p>Carregando...</p>
            )}
        </div>
    );
}

export default SingleEntityComponent;
```

### **Instruções para Adaptação**:
- **URL**: Substitua `http://localhost:5000/getEntity/${id}` pelo endpoint correto da API.
- **Campos**: Adapte `entityData.title` e `entityData.description` para os campos reais da resposta da API.
- **Tratamento de Erro**: A variável `error` exibe uma mensagem em caso de erro na requisição. Você pode personalizar essa mensagem ou substituí-la por um componente de feedback visual (ex.: toast ou modal).

### Exemplo Completo: Passo a Passo

1. **Crie a Rota no Backend**:
   - Defina a rota `GET` com `findUnique` para buscar um registro específico pelo `ID`.
   - Retorne o registro encontrado ou um erro caso não exista.

2. **Defina o Componente "Single" no Frontend**:
   - Use `useEffect` para fazer a requisição `GET` quando o componente for montado.
   - Guarde os dados do registro no estado `entityData` e exiba no componente.
   - Adapte os campos e a lógica de renderização para corresponder aos dados específicos que você deseja exibir.

3. **Verifique e Teste a Requisição**:
   - Certifique-se de que o ID passado para o componente corresponde ao registro que deseja exibir.
   - Use `console.log(entityData)` para depurar e visualizar a resposta.

Essa abordagem permite que você reutilize essa estrutura genérica para buscar e exibir detalhes de qualquer registro específico em uma "página single" em React, apenas substituindo o nome da rota e os campos conforme necessário.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

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
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Botão de exclusão com confirmação

### Simplificando o formulário para enviar o ID de um item, formulário que confirma a remoção de item

Para atender à sua solicitação, vou simplificar o formulário de maneira que ele contenha apenas a mensagem "Deseja mesmo excluir este registro?" e dois botões, "Sim" (para enviar o formulário) e "Não" (para não fazer nada). Também ajustarei o envio para que o formulário envie apenas o valor `"y"` conforme solicitado. Aqui está o código atualizado:

```jsx
import {
    Container,
    Button,
    Col,
    Form,
    Row
} from 'react-bootstrap';

import React, { useState, useRef } from 'react';

// Ícones Font-Awesome.
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome';
import {
    faCheck,
    faTimes
} from '@fortawesome/free-solid-svg-icons';

export function DeleteUser() {

    // Definir o estado para o valor "y".
    const [confirmationValue] = useState("y");

    // Referenciar o formulário.
    const formRef = useRef();

    // Função Reset, para resetar o formulário.
    function handlePopUpNo() {
        // Não faz nada, pois é apenas o botão "Não".
    }

    // Função de envio do formulário.
    async function handleSubmitForm(e) {
        e.preventDefault();

        // Preparar o objeto com os dados a serem enviados
        const formData = { confirmation: confirmationValue };

        try {
            // Fazer a solicitação POST para a API
            const response = await fetch('http://localhost:3000/deleteYourTable', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify(formData) // Enviar o valor "y" como JSON
            });
    
            if (response.ok) {
                const data = await response.json();
                console.log('Registro excluído com sucesso:', data);
    
                // Resetar o formulário após o envio bem-sucedido (aqui não há necessidade, pois é uma confirmação simples)
            } else {
                const errorData = await response.json();
                console.error('Erro ao excluir registro:', errorData);
                alert('Erro ao excluir registro. Tente novamente.');
            }
        } catch (error) {
            console.error('Erro de rede ou servidor:', error);
            alert('Erro de rede ou servidor. Tente novamente mais tarde.');
        }
    }

    return (
        <Container>
            <Form ref={formRef} onSubmit={handleSubmitForm}>
                <Row className="mb-3">
                    <Col sm={12}>
                        <p>Deseja mesmo excluir este registro?</p>
                    </Col>
                </Row>
                <Button variant="danger" type="submit">
                    <FontAwesomeIcon icon={faCheck} />{' '}Sim
                </Button>
                <Button type="button" onClick={handlePopUpNo} variant="secondary" className="ms-2">
                    <FontAwesomeIcon icon={faTimes} />{' '}Não
                </Button>
            </Form>
        </Container>
    );
}
```

### Alterações feitas:
1. **Mensagem de confirmação**: Foi adicionada a mensagem "Deseja mesmo excluir este registro?" acima dos botões.
2. **Botão "Sim"**: O botão de envio foi renomeado para "Sim", com o ícone correspondente.
3. **Botão "Não"**: O botão de reset foi renomeado para "Não" e removi sua funcionalidade, como solicitado.
4. **Envio do formulário**: O formulário agora envia apenas o valor `"y"` como parte de um objeto `confirmation`.

Esse código simplificado atende ao que foi solicitado, mantendo apenas a lógica necessária para exibir a mensagem e enviar a confirmação da exclusão.

### Passando informação para o componente

Para passar o `item.id` para o componente `DeleteUser`, você precisa modificar a chamada de abertura da janela (`fenestra.open`) para incluir o `id` como uma prop do componente. Vou fazer a modificação na linha que você mencionou:

```jsx
<FontAwesomeIcon
    className={styles.faTrashCan}
    icon={faTrashCan}
    size="1x"
    title='Excluir usuário'
    onClick={() => props.fenestra.open({
        title: "Resumida",
        resizeable: false,
        left: (window.innerWidth - 350) / 2,
        top: (window.innerHeight - 150) / 2,
        width: 350,
        height: 150,
        content: ({ fenestra }) => <DeleteUser id={item.id} />
    })}
/>
```

### O que foi alterado:
1. **Passagem do `id` como prop**: A linha foi alterada para que o componente `DeleteUser` receba o `id` através de uma prop, ou seja, `id={item.id}`.
2. **Dentro do componente `DeleteUser`**: Certifique-se de acessar essa prop para usá-la conforme necessário. Por exemplo, dentro do seu componente `DeleteUser`, você pode fazer o seguinte:

   ```jsx
   export function DeleteUser({ id }) {
       // Utilize o ID aqui, por exemplo, ao enviar a requisição:
       console.log("ID recebido:", id);
   
       // ... restante do componente
   }
   ```

Dessa forma, o `id` será passado corretamente para o componente `DeleteUser` e você poderá utilizá-lo para qualquer operação, como enviar no corpo da requisição ou exibir na mensagem de confirmação.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Exemplo Genérico de Rota DELETE com Parâmetros Dinâmicos e Filtragem

Este exemplo mostra como criar uma rota DELETE que recebe múltiplos parâmetros dinâmicos. Esse padrão é útil para excluir registros com base em uma relação entre duas entidades (por exemplo, um administrador associado a uma empresa).

#### Estrutura da Rota no Backend (Node.js/Express)

```ts
// Exemplo genérico de rota DELETE com múltiplos parâmetros
routes.delete('/deleteEntity/:parentId/:childId', async (req, res) => {
    const { parentId, childId } = req.params;

    try {
        // Verificar se o registro existe e está associado ao parâmetro fornecido
        const recordExists = await prisma.yourEntity.findFirst({
            where: { 
                id: parseInt(childId), // Substitua 'id' pelo campo que identifica o registro filho
                parent_field: parseInt(parentId) // Substitua 'parent_field' pela chave estrangeira
            }
        });

        if (!recordExists) {
            return res.status(404).json({ error: 'Registro não encontrado ou não associado.' });
        }

        // Excluir o registro
        await prisma.yourEntity.delete({
            where: { id: parseInt(childId) } // Certifique-se de usar o campo correto aqui
        });

        res.status(200).json({ message: 'Registro excluído com sucesso.' });
    } catch (error) {
        console.error('Erro ao excluir registro:', error);
        res.status(500).json({ error: 'Erro ao excluir registro.' });
    }
});
```

**Substitua os valores genéricos conforme necessário:**
- `yourEntity`: Nome da entidade/tabela no Prisma (ex.: `admins`, `products`).
- `parentId`: Identificador do registro "pai" (ex.: `idCompany`).
- `childId`: Identificador do registro que será excluído (ex.: `id` do administrador).
- `parent_field`: Nome da coluna da chave estrangeira que referencia o "pai" (ex.: `company_id`).

### Instruções para Reutilizar a Estrutura

1. **Defina a Rota no Backend:**
   - Escolha a URL e parâmetros apropriados para o contexto. Exemplo: `/deleteItem/:categoryId/:itemId`.
   - Use `req.params` para capturar os valores dinâmicos na rota.
   - Substitua `yourEntity`, `parent_field`, `parentId` e `childId` conforme as entidades e relações do seu projeto.

2. **Validar Existência e Associação do Registro:**
   - Use o método `findUnique` ou `findFirst` do Prisma para verificar se o registro existe e está associado ao parâmetro "pai".
   - Se não encontrar o registro, retorne um status `404` com uma mensagem apropriada.

3. **Excluir o Registro:**
   - Após validar a existência e associação do registro, utilize `delete` do Prisma para excluí-lo.
   - Envie uma resposta `200` com uma mensagem de sucesso.

4. **Tratar Erros:**
   - Use `try-catch` para capturar e logar erros. Retorne um status `500` com uma mensagem de erro genérica em caso de falha.

### Exemplo de Requisição no Frontend (React)

Para excluir o registro a partir do frontend, utilize uma função com `fetch` ou `axios` que envia uma requisição DELETE para a rota.

```jsx
import React from 'react';

const handleDelete = async (parentId, childId) => {
    try {
        const response = await fetch(`/deleteEntity/${parentId}/${childId}`, {
            method: 'DELETE'
        });
        
        if (!response.ok) throw new Error('Erro ao excluir o registro');

        const result = await response.json();
        console.log(result.message); // Exibe a mensagem de sucesso
        // Atualize o estado ou faça outras ações necessárias após a exclusão
    } catch (error) {
        console.error('Erro:', error.message);
    }
};
```

**Explicação do código:**
- `parentId` e `childId` são os parâmetros dinâmicos passados para a rota.
- `fetch` com o método `DELETE` envia a requisição para o backend.
- Em caso de sucesso, uma mensagem de confirmação é exibida no console e o frontend pode atualizar o estado para refletir a exclusão.

### Resumo para Adaptação em Outros Projetos

1. **Configuração da Rota:** Defina a URL da rota com os parâmetros dinâmicos.
2. **Verificação de Existência e Associação:** Use `findUnique` para validar que o registro existe e está associado ao registro pai.
3. **Exclusão do Registro:** Utilize `delete` do Prisma após a verificação.
4. **Requisição no Frontend:** Utilize `fetch` ou `axios` para enviar a requisição DELETE, passando os parâmetros necessários.
5. **Tratamento de Erros e Sucesso:** Implemente logs e mensagens de feedback para garantir uma boa experiência para o usuário.

Essa estrutura pode ser reutilizada e adaptada facilmente para outras operações de exclusão em sistemas com relações de chave estrangeira.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Rota Genérica de Exclusão via ID e Integração com Frontend React

Aqui está uma versão genérica das instruções para que você possa usá-las em diferentes contextos e componentes ao configurar rotas de exclusão por ID com integração no frontend em React.

### **Rota de Exclusão por ID**

#### **Descrição**:
Esta rota é usada para excluir um registro de uma tabela específica com base em seu `ID`. A requisição para essa rota é do tipo `DELETE`.

#### **Rota**:
```jsx
// Rota genérica para excluir um registro pelo ID
routes.delete('/deleteEntity/:id', async (req, res) => {
    const { id } = req.params;

    try {
        // Verificar se o registro existe na tabela especificada
        const entityExists = await prisma.entity.findUnique({
            where: { id: parseInt(id) },
        });

        if (!entityExists) {
            return res.status(404).json({ error: 'Registro não encontrado' });
        }

        // Excluir o registro
        await prisma.entity.delete({
            where: { id: parseInt(id) },
        });

        return res.status(200).json({ message: 'Registro excluído com sucesso' });
    } catch (error) {
        console.error('Erro ao excluir registro:', error);
        return res.status(500).json({ error: 'Erro ao excluir registro' });
    }
});
```

#### **Instruções para Adaptação**:
- **Nome da Rota**: Substitua `'/deleteEntity/:id'` pela rota desejada, como `'/deleteUser/:id'` ou `'/deleteProduct/:id'`.
- **Tabela (Entidade)**: Substitua `entity` no código Prisma pelo nome da tabela real no seu `schema.prisma` (ex.: `prisma.users`, `prisma.products`, etc.).

### **Como Requisitar a Rota no Frontend**

No frontend (React), faça uma requisição `DELETE` para a rota de exclusão, passando o `ID` do registro a ser excluído.

#### **Exemplo Genérico de Requisição no Frontend**:
```javascript
async function handleDelete(id) {
    try {
        // Requisição DELETE para a API com o ID
        const response = await fetch(`http://localhost:5000/deleteEntity/${id}`, {
            method: 'DELETE',
            headers: {
                'Content-Type': 'application/json'
            }
        });

        if (response.ok) {
            const data = await response.json();
            console.log('Registro excluído com sucesso:', data);

            // Execute ações adicionais aqui, como atualizar a lista de registros
        } else {
            const errorData = await response.json();
            console.error('Erro ao excluir registro:', errorData);
            alert('Erro ao excluir registro. Tente novamente.');
        }
    } catch (error) {
        console.error('Erro de rede ou servidor:', error);
        alert('Erro de rede ou servidor. Tente novamente mais tarde.');
    }
}
```

#### **Instruções para Adaptação**:
- **URL**: Substitua `'http://localhost:5000/deleteEntity/${id}'` pelo endpoint correto da rota de exclusão.
- **Ações Adicionais**: Após a exclusão, você pode adicionar ações específicas, como atualizar a lista de registros ou exibir uma mensagem de sucesso.

### **Exemplo de Uso no Componente React**

No componente React, utilize a função de exclusão, passando o ID do registro a ser removido:

```jsx
import React from 'react';

function DeleteButton({ id }) {
    async function handleDelete() {
        try {
            const response = await fetch(`http://localhost:5000/deleteEntity/${id}`, {
                method: 'DELETE',
                headers: {
                    'Content-Type': 'application/json'
                }
            });

            if (response.ok) {
                console.log('Registro excluído com sucesso');
                // Atualize a interface ou lista de registros, se necessário
            } else {
                console.error('Erro ao excluir registro');
                alert('Erro ao excluir registro. Tente novamente.');
            }
        } catch (error) {
            console.error('Erro de rede ou servidor:', error);
            alert('Erro de rede ou servidor. Tente novamente mais tarde.');
        }
    }

    return <button onClick={handleDelete}>Excluir</button>;
}

export default DeleteButton;
```

#### **Notas**:
- **ID**: O ID do registro deve ser passado corretamente ao componente.
- **Mensagens de sucesso/erro**: O código exibe mensagens no console ou em um `alert()` para indicar o sucesso ou falha da operação. Para uma experiência melhor, você pode usar componentes de feedback como `toasts` ou `modals`.

Esse guia genérico permite que você configure e reutilize a lógica de exclusão de registros com facilidade em diversos componentes e tabelas do seu sistema.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Rota de Criação de Registro (Create) com Prisma e Requisição no Frontend

### Rota Backend: Criação de Registro (Create)

Primeiro, vamos configurar a rota `POST` para adicionar um novo registro à tabela do banco de dados usando Prisma.

#### **Exemplo da Rota no Backend (Node.js/Express)**

```ts
// Rota genérica para criar um novo registro
routes.post('/createEntity', async (req, res) => {
    const { title, description } = req.body; // Adapte os campos conforme a tabela

    try {
        // Criar o novo registro no banco de dados
        const newEntity = await prisma.entity.create({
            data: {
                title,        // Exemplo de campo: substitua conforme necessário
                description   // Exemplo de campo: substitua conforme necessário
            }
        });

        return res.status(201).json(newEntity);
    } catch (error) {
        console.error('Erro ao criar registro:', error);
        return res.status(500).json({ error: 'Erro ao criar registro' });
    }
});
```

#### **Instruções para Adaptação**:
- **Rota**: Substitua `'/createEntity'` pelo endpoint desejado, como `'/createUser'` ou `'/createProduct'`.
- **Tabela (Entidade)**: Troque `entity` pelo nome real da tabela definida no `schema.prisma` (ex.: `users`, `products`).
- **Campos**: Ajuste `title` e `description` para os campos que deseja salvar, de acordo com a tabela do banco.

---

### Requisição no Frontend (React)

Para enviar os dados do formulário para essa rota, faremos uma requisição `POST` usando `fetch` em um componente React.

#### **Exemplo de Requisição para Criar Registro**

```jsx
import React, { useState } from 'react';

function CreateEntityForm() {
    const [title, setTitle] = useState('');
    const [description, setDescription] = useState('');
    const [message, setMessage] = useState('');

    async function handleSubmit(event) {
        event.preventDefault();

        const formData = {
            title,
            description,
        };

        try {
            const response = await fetch('http://localhost:5000/createEntity', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify(formData)
            });

            if (response.ok) {
                const data = await response.json();
                setMessage('Registro criado com sucesso!');
                console.log('Novo registro:', data);

                // Limpar o formulário após a criação
                setTitle('');
                setDescription('');
            } else {
                const errorData = await response.json();
                console.error('Erro ao criar registro:', errorData);
                setMessage('Erro ao criar registro. Tente novamente.');
            }
        } catch (error) {
            console.error('Erro de rede ou servidor:', error);
            setMessage('Erro de rede ou servidor. Tente novamente mais tarde.');
        }
    }

    return (
        <div>
            <form onSubmit={handleSubmit}>
                <label>
                    Título:
                    <input
                        type="text"
                        value={title}
                        onChange={(e) => setTitle(e.target.value)}
                    />
                </label>
                <label>
                    Descrição:
                    <input
                        type="text"
                        value={description}
                        onChange={(e) => setDescription(e.target.value)}
                    />
                </label>
                <button type="submit">Criar Registro</button>
            </form>
            {message && <p>{message}</p>}
        </div>
    );
}

export default CreateEntityForm;
```

#### **Instruções para Adaptação**:
- **URL da Requisição**: Substitua `'http://localhost:5000/createEntity'` pela URL do endpoint correto.
- **Campos do Formulário**: Adapte `title` e `description` conforme necessário para outros campos.

#### **Resumo das Etapas**:
1. **Backend**: Crie a rota `POST /createEntity`, receba os dados de `req.body` e salve-os na tabela usando Prisma.
2. **Frontend**: Defina o formulário em React para capturar os dados e enviar para a rota.
3. **Requisição**: Faça a requisição `POST`, trate a resposta e exiba uma mensagem de sucesso ou erro para o usuário.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
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
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Rota com Parâmetro Dinâmico e Filtragem por Chave Estrangeira no Prisma

Aqui está um exemplo genérico, com instruções detalhadas para adicionar uma rota que receba um parâmetro dinâmico e filtre registros com base em uma chave estrangeira. Também incluo a forma de fazer a requisição no frontend para utilizar essa rota. 

### Exemplo Genérico para Criar uma Rota com Parâmetro e Filtragem

1. **Estrutura da Rota no Backend (Node.js/Express)**

   Adicione uma rota na sua API que receba um parâmetro dinâmico (ex.: `:id`) e faça uma consulta ao banco de dados utilizando o Prisma, filtrando pelo campo de chave estrangeira (ex.: `foreign_key_field`).

   ```ts
   // Estrutura genérica da rota
   routes.get('/your-entity/:id', async (req, res) => {
       const { id } = req.params;

       try {
           const data = await prisma.yourEntity.findMany({
               where: {
                   foreign_key_field: Number(id) // Substitua 'foreign_key_field' pelo nome da chave estrangeira real
               },
               orderBy: {
                   id: 'desc'
               }
           });

           console.log(data); // Log para verificar a saída
           res.status(200).json(data);
       } catch (error) {
           console.error('Erro ao buscar dados:', error);
           res.status(500).json({ error: 'Erro ao buscar dados' });
       }
   });
   ```

   **Substitua os valores genéricos conforme necessário**:
   - `your-entity`: o nome da entidade (ex.: `admins`, `products`, etc.).
   - `foreign_key_field`: o nome da chave estrangeira no banco de dados (ex.: `company_id`).
   - `id`: o campo de ordenação pode ser `id` ou qualquer outra coluna desejada.

2. #### **Instruções para Requisição da Rota no Frontend (React)**

   Para fazer a requisição no componente do frontend, você pode utilizar `fetch` ou uma biblioteca como `axios`. Aqui está um exemplo usando `fetch`:

   ```jsx
   import React, { useEffect, useState } from 'react';

   const YourComponent = ({ id }) => {
       const [data, setData] = useState([]);
       const [error, setError] = useState(null);

       // Realizar a chamada à API para buscar dados associados ao parâmetro especificado.
       useEffect(() => {
           const fetchData = async () => {
               try {
                   const response = await fetch(`/your-entity/${id}`); // Passado o parâmetro.
                   if (!response.ok) throw new Error('Erro na requisição');
                   
                   const result = await response.json();
                   setData(result);
               } catch (err) {
                   setError(err.message);
                   console.error('Erro ao buscar dados:', err);
               }
           };

           if (id) {
               fetchData();
           }
       }, [id]);

       return (
           <div>
               {error && <p>Erro: {error}</p>}
               <ul>
                   {data.map((item) => (
                       <li key={item.id}>{item.nome}</li> {/* Ajuste conforme os campos */}
                   ))}
               </ul>
           </div>
       );
   };

   export default YourComponent;
   ```

   **Explicação do código:**
   - `fetchData()`: Faz uma requisição `GET` para a rota, usando o `id` passado como parâmetro.
   - `setData()`: Armazena o resultado retornado para renderização.
   - `error`: Exibe uma mensagem caso ocorra erro na requisição.

### Resumo das Etapas para Reutilizar o Exemplo

1. **No Backend**:
   - Crie uma rota `GET` com um parâmetro dinâmico `:id`.
   - Use `findMany` (ou `findUnique`, caso deseje um único registro) no Prisma para consultar a entidade filtrando pela chave estrangeira correspondente.
   - Converta o `id` para `Number` para assegurar a compatibilidade de tipo.

2. **No Frontend**:
   - Utilize `fetch` (ou `axios`) para fazer a requisição para a rota da API, passando o `id` necessário.
   - Armazene e manipule os dados recebidos com `useState` e `useEffect`.
   - Renderize os dados conforme necessário no componente.

Esse padrão ajuda a estruturar rotas e componentes de forma a serem reutilizáveis e adaptáveis para diferentes entidades e relações no seu sistema.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Adicionando Classe na Div Mãe

Aqui está um passo a passo para implementar a funcionalidade de adicionar e remover classes em uma `div` mãe e manipular diretamente o DOM em um componente React:

### Passo a Passo para Adicionar e Remover Classe em Componente Modal

1. **Importe `useEffect` do React**:
   Para manipular o DOM ao montar e desmontar o componente, importe o `useEffect` do React, pois ele permite executar código apenas em momentos específicos do ciclo de vida do componente.

2. **Configuração Inicial com `useEffect`**:
   Utilize o `useEffect` para adicionar a classe à `div` mãe no momento em que o componente é montado e garantir a remoção da classe quando o componente for desmontado.
   
3. **Selecionar o Elemento de Janela (`popupElement`)**:
   Dentro do `useEffect`, use `document.querySelector` para selecionar a `div` mãe ou elemento específico que deseja manipular. No exemplo, seleciona-se o elemento com a classe `fenestra-window-active`.

4. **Adicionar a Classe à `div` Mãe**:
   Verifique se o `popupElement` foi encontrado e, em seguida, utilize `classList.add` para adicionar uma nova classe. Aqui, a classe é chamada de `"popUpDeleteUser_" + id`, onde `id` é uma variável que torna a classe única para cada instância do componente.

5. **Limpar a Classe ao Desmontar o Componente**:
   Retorne uma função de "cleanup" dentro do `useEffect`. Essa função remove a classe do elemento `popupElement` ao desmontar o componente, garantindo que o DOM fique limpo ao sair do modal ou componente.

6. **Criar a Função `handleButtonNo` para Remover o Elemento**:
   Defina uma função chamada `handleButtonNo` que, ao ser chamada, seleciona a `div` com a classe específica (usando `querySelector` e a classe `popUpDeleteUser_` concatenada com `id`). Se o elemento for encontrado, remova-o do DOM com `remove()`.

### Exemplo de Aplicação

Utilize o código a seguir para adicionar e remover a classe dinamicamente:

```jsx
useEffect(() => {
    const popupElement = document.querySelector('.fenestra-window-active');
    
    if (popupElement) {
        popupElement.classList.add('popUpDeleteUser_' + id);
    }

    return () => {
        if (popupElement) {
            popupElement.classList.remove('popUpDeleteUser_' + id);
        }
    };
}, []);

function handleButtonNo() {
    const popupElement = document.querySelector('.popUpDeleteUser_' + id);
    
    if (popupElement) {
        popupElement.remove();
    }
}
```

### Resumo
1. **Importe `useEffect`**.
2. **Adicione a classe à `div` mãe no `useEffect`**.
3. **Remova a classe ao desmontar o componente**.
4. **Crie a função `handleButtonNo` para remover o elemento do DOM**.

Esses passos garantem uma manipulação de classe consistente em modais ou janelas personalizadas, como no caso do uso com a biblioteca "fenestra".

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
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
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Uso de Variáveis de Ambiente com Arquivo .env no React

O arquivo `.env` no React é usado para armazenar variáveis de ambiente, como chaves de API, URLs de backend e outras configurações sensíveis que você não quer hardcodar diretamente no código-fonte. Isso facilita o gerenciamento e aumenta a segurança, especialmente em ambientes de produção e desenvolvimento.

Aqui está um resumo de como o `.env` funciona no contexto de um projeto React criado com o Create React App (CRA):

### 1. Estrutura e Convenções
No React, as variáveis de ambiente precisam começar com `REACT_APP_` para serem reconhecidas pelo CRA. Isso é uma medida de segurança para evitar o uso indiscriminado de variáveis de ambiente.

Exemplo de um arquivo `.env`:
```env
REACT_APP_API_URL=https://minha-api.com
REACT_APP_GOOGLE_API_KEY=chave-do-google
```

[![Início](../../images/control/11280_control_up_icon.png)](#uso-de-vari%C3%A1veis-de-ambiente-com-arquivo-env-no-react "Conteúdo")

### 2. Utilização no Código
Após definir as variáveis no `.env`, você pode acessá-las no código usando `process.env.NOME_DA_VARIAVEL`.

Por exemplo:
```javascript
const apiUrl = process.env.REACT_APP_API_URL;
console.log("URL da API:", apiUrl);
```

Isso tornará a variável `REACT_APP_API_URL` acessível no código React, e o valor será substituído no processo de build.

[![Início](../../images/control/11280_control_up_icon.png)](#uso-de-vari%C3%A1veis-de-ambiente-com-arquivo-env-no-react "Conteúdo")

### 3. Adicionando o Arquivo ao `.gitignore`
O arquivo `.env` normalmente contém informações sensíveis e específicas do ambiente (como chaves e segredos). É uma boa prática adicioná-lo ao `.gitignore` para que ele não seja enviado ao repositório:
```
# Arquivo .gitignore
.env
```

[![Início](../../images/control/11280_control_up_icon.png)](#uso-de-vari%C3%A1veis-de-ambiente-com-arquivo-env-no-react "Conteúdo")

### 4. Variáveis Diferentes para Ambientes Diferentes
Para facilitar a configuração de ambientes, você pode criar arquivos `.env` específicos para cada ambiente:
- `.env.development` para variáveis de ambiente em desenvolvimento.
- `.env.production` para produção.
- `.env.test` para testes.

O Create React App carrega automaticamente as variáveis do arquivo correspondente ao ambiente atual (`NODE_ENV`).

[![Início](../../images/control/11280_control_up_icon.png)](#uso-de-vari%C3%A1veis-de-ambiente-com-arquivo-env-no-react "Conteúdo")

### 5. Limitações e Avisos
- **Somente em Build Time:** As variáveis são embutidas no bundle do React durante o build, ou seja, você não pode modificá-las em tempo de execução.
- **Exposição no Frontend:** Como o React é um projeto frontend, qualquer variável definida no `.env` estará acessível no código do cliente, mesmo que você tenha adicionado ao `.gitignore`. Portanto, **nunca coloque segredos críticos** (como credenciais de banco de dados) no `.env` do React.

### Exemplo Completo

Se você tem o seguinte `.env`:
```env
REACT_APP_API_URL=https://api.meusite.com
REACT_APP_GOOGLE_API_KEY=MINHA_CHAVE_GOOGLE
```

No seu componente React, pode usá-las assim:
```javascript
function App() {
  const apiUrl = process.env.REACT_APP_API_URL;
  const googleApiKey = process.env.REACT_APP_GOOGLE_API_KEY;

  useEffect(() => {
    console.log("URL da API:", apiUrl);
    // Use apiUrl em chamadas de fetch ou axios
  }, [apiUrl]);

  return (
    <div>
      <h1>Minha aplicação React</h1>
      <p>Chave da API do Google: {googleApiKey}</p>
    </div>
  );
}

export default App;
```

Assim, você consegue gerenciar as variáveis de forma prática e segura no React!

[![Início](../../images/control/11280_control_up_icon.png)](#uso-de-vari%C3%A1veis-de-ambiente-com-arquivo-env-no-react "Conteúdo")

### Gerenciamento de URLs de API por Ambiente com Variáveis de Ambiente no React

Para diferenciar as URLs de ambiente de desenvolvimento (localhost) e produção (online), você pode usar nomes de variáveis que indiquem o propósito de cada uma. Aqui estão algumas sugestões:

```env
# URL da API para o ambiente de produção
REACT_APP_API_URL_PROD=http://000.000.000.000:3333

# URL da API para o ambiente de desenvolvimento (localhost)
REACT_APP_API_URL_DEV=http://localhost:3333
```

Esses nomes deixam claro o propósito de cada URL. No código, você pode decidir qual utilizar com base no ambiente atual.

### Exemplo de Uso no Código

Para escolher a URL correta conforme o ambiente, você pode fazer algo assim:

```javascript
const apiUrl = process.env.NODE_ENV === 'production' 
  ? process.env.REACT_APP_API_URL_PROD 
  : process.env.REACT_APP_API_URL_DEV;

console.log("API URL:", apiUrl);
```

### Alternativa Usando Apenas uma Variável e Diferentes `.env`

Outra abordagem é criar dois arquivos `.env`, um para desenvolvimento (`.env.development`) e outro para produção (`.env.production`), cada um com a mesma variável `REACT_APP_API_URL`. Dessa forma, a variável muda automaticamente conforme o ambiente:

**.env.development**
```env
REACT_APP_API_URL=http://localhost:3333
```

**.env.production**
```env
REACT_APP_API_URL=http://000.000.000.000:3333
```

No código, você acessaria sempre `process.env.REACT_APP_API_URL`, e o valor correto seria carregado dependendo do ambiente de execução.

Para substituir `http://localhost:3333` pela variável `process.env.REACT_APP_API_URL`, basta concatenar a URL base com o caminho da rota (`/addAdmins`). Veja como fazer isso:

```jsx
// Construir a URL completa usando a variável de ambiente
const apiUrl = `${process.env.REACT_APP_API_URL}/addAdmins`;

// Fazer a solicitação POST para a API
const response = await fetch(apiUrl, {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json'
    },
    body: JSON.stringify(formData) // Enviar o objeto como JSON
});
```

### Passo a Passo
1. **Defina a URL base:** Use `process.env.REACT_APP_API_URL` para obter a URL configurada no seu arquivo `.env`.
2. **Concatenar o caminho da rota:** Combine a URL base com o caminho da API (`/addAdmins`), usando template literals (`` `${...}` ``) para criar a URL completa.

### Observação sobre Configuração do `.env`
Se estiver rodando em ambiente de desenvolvimento, certifique-se de que o arquivo `.env` contém a variável `REACT_APP_API_URL`:

```env
# Exemplo de configuração em desenvolvimento
REACT_APP_API_URL=http://localhost:3333
```

Assim, ao mudar para produção, você só precisa alterar o valor em `.env.production`, sem modificar o código da aplicação.

O arquivo `.env` deve ser colocado no diretório raiz do **Frontend** (ou seja, no mesmo nível de `package.json` do projeto React). É nesse ambiente que as variáveis `process.env.REACT_APP_*` serão acessadas, e o Create React App automaticamente carrega essas variáveis no processo de build.

### Estrutura de Diretório

Supondo uma estrutura de projeto como a seguinte:

```bash
/meu-projeto
├── /frontend
│   ├── .env               # Arquivo .env para o React (frontend)
│   ├── package.json
│   ├── src
│   └── ...
└── /backend
    ├── .env               # Arquivo .env para o backend (opcional, se o backend também precisar de variáveis de ambiente)
    ├── package.json
    └── ...
```

O `.env` do frontend estará dentro da pasta `frontend`, e as variáveis serão acessíveis para as requisições e configurações da aplicação React.

### Dicas Importantes

- **Evitar confusão entre variáveis de ambiente**: Certifique-se de que variáveis de ambiente específicas do frontend e backend estão separadas para evitar conflitos, especialmente se você também usa um arquivo `.env` no backend.
- **Atualizar o build após mudanças no `.env`**: Sempre que alterar o `.env`, reinicie o servidor de desenvolvimento do React para que as novas variáveis sejam carregadas.

Isso garante que o frontend acesse corretamente as variáveis definidas no `.env` para as requisições de API e outras configurações.

### Verifique se está usando Vite (ou Outro Bundler Diferente de CRA)

Se você está usando **Vite** ou outro bundler no lugar do Create React App, a configuração das variáveis de ambiente é diferente. Em Vite, por exemplo, as variáveis de ambiente precisam começar com `VITE_` em vez de `REACT_APP_`.

Exemplo para Vite:
```env
VITE_API_URL=http://localhost:3333
```

E no código, você acessaria como `import.meta.env.VITE_API_URL`.

### Resumo

- **CRA**: Use `REACT_APP_` e acesse como `process.env.REACT_APP_API_URL`.
- **Vite**: Use `VITE_` e acesse como `import.meta.env.VITE_API_URL`.

Essas dicas devem resolver problemas.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Guia: Como Acessar Dados do `localStorage` para Requisições API em Componentes React

Guia com instruções claras sobre como acessar dados do `localStorage` (como o `companyId`) e usá-los em requisições API dentro de um `useEffect`. Vou incluir também um exemplo genérico para facilitar a reutilização.

#### Objetivo
Carregar dados específicos armazenados no `localStorage`, como o `companyId` do usuário, e utilizá-los em chamadas de API dentro de componentes React.

![LocalStorage](./images/localStorage_1.png)

#### Passo a Passo

1. **Acessar o `localStorage`**: Obtenha e parse o valor necessário (por exemplo, `companyId`) diretamente do `localStorage` para uso dentro do componente.
   
2. **Configurar o `useEffect`**: Utilize o `useEffect` para realizar a chamada API assim que o componente for montado ou quando o dado necessário for obtido.

3. **Usar o Dado no `useEffect`**: Passar o valor recuperado do `localStorage` (como o `companyId`) na URL da API.

4. **Tratar a Resposta da API**: Atualize o estado do componente com a resposta da API para exibir ou manipular os dados conforme necessário.

### Exemplo Genérico

Aqui está um exemplo genérico que você pode seguir para outros componentes:

```jsx
import React, { useState, useEffect } from 'react';
import { Api } from 'caminho/para/api'; // Importe seu módulo de API.

export function MeuComponente() {
    const [dados, setDados] = useState([]);

    // 1. Obter o `companyId` (ou outro dado) do localStorage.
    const storedUser = JSON.parse(localStorage.getItem('user'));
    const companyId = storedUser?.company_id; // Substitua por outro dado, se necessário.

    // 2. Uso do `useEffect` para fazer a requisição API.
    useEffect(() => {
        if (companyId) { // Verificar o `companyId` está definido antes de fazer a requisição.
            Api.get(`/suaRotaApi/${companyId}`)
                .then((res) => {
                    // 3. Atualizar o estado com a resposta da API.
                    setDados(res.data);
                })
                .catch((error) => {
                    console.error("Erro ao buscar dados:", error);
                });
        }
    }, [companyId]); // Colocar do `companyId` como dependência, se necessário.

    return (
        <div>
            {/* Renderizar dos dados obtidos conforme necessário. */}
            {dados.length > 0 ? (
                <ul>
                    {dados.map((item) => (
                        <li key={item.id}>{item.nome}</li> // Adaptar conforme a estrutura de `dados`.
                    ))}
                </ul>
            ) : (
                <p>Nenhum dado disponível</p>
            )}
        </div>
    );
}
```

### Explicação do Exemplo

- **Obter `companyId`**: Utilizamos `JSON.parse(localStorage.getItem('user'))` para recuperar o objeto armazenado como string JSON. Em seguida, acessamos o campo `company_id` dentro de `storedUser`.

- **Chamada API Condicional**: No `useEffect`, verificamos se `companyId` está definido antes de fazer a requisição. Isso é importante para evitar erros, caso `companyId` seja `undefined` ou `null`.

- **Tratamento de Erros**: Sempre inclua um `catch` na chamada `Api.get` para capturar e tratar erros, facilitando a depuração e prevenindo falhas silenciosas.

- **Dependência do `useEffect`**: Adicione `companyId` como dependência no array de dependências do `useEffect`, caso o dado possa mudar durante o ciclo de vida do componente.

### Reutilização em Outros Componentes

1. **Repita a leitura do `localStorage`** para qualquer dado necessário, como `userId`, `companyId`, ou outros campos específicos.
2. **Substitua `/suaRotaApi/${companyId}`** com a rota apropriada para o componente atual.
3. **Atualize o estado e renderize os dados** conforme a estrutura de resposta da API e as necessidades do componente.

Seguindo essas instruções, você conseguirá acessar dados do `localStorage` e usá-los em requisições API em diferentes componentes de forma rápida e eficaz!

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

