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
     - Exemplo completo de um `CRUD` (Create, Read, Update, Delete)
       - [Rota de Criação de Registro (`Create`) com Prisma e Requisição no Frontend](#rota-de-cria%C3%A7%C3%A3o-de-registro-create-com-prisma-e-requisi%C3%A7%C3%A3o-no-frontend "Rota de Criação de Registro (Create) com Prisma e Requisição no Frontend")
       - [Rota de Leitura de Registros (`Read`) com Prisma e Requisição no Frontend](#rota-de-leitura-de-registros-read-com-prisma-e-requisi%C3%A7%C3%A3o-no-frontend "Rota de Leitura de Registros (Read) com Prisma e Requisição no Frontend")
       - [Rota de Atualização de Registro (`Update`) com Prisma e Requisição no Frontend](#rota-de-atualiza%C3%A7%C3%A3o-de-registro-update-com-prisma-e-requisi%C3%A7%C3%A3o-no-frontend "Rota de Atualização de Registro (Update) com Prisma e Requisição no Frontend")
       - [Rota de Exclusão de Registro (`Delete`) com Prisma e Requisição no Frontend](#rota-de-exclus%C3%A3o-de-registro-delete-com-prisma-e-requisi%C3%A7%C3%A3o-no-frontend "Rota de Exclusão de Registro (Delete) com Prisma e Requisição no Frontend")
     - Reutilização de componentes e lógica no frontend
     - Organização de rotas e `controllers` no backend
       - [Refatoração de rotas e uso de controllers](#refatora%C3%A7%C3%A3o-de-rotas-e-uso-de-controllers "Refatoração de rotas e uso de controllers")
       - [Como mover a lógica de rotas para controllers para melhor organização](#como-mover-a-l%C3%B3gica-de-rotas-para-controllers-para-melhor-organiza%C3%A7%C3%A3o "Como mover a lógica de rotas para controllers para melhor organização")
       - [Vantagens da modularização e manutenibilidade do código](#vantagens-da-modulariza%C3%A7%C3%A3o-e-manutenibilidade-do-c%C3%B3digo "Vantagens da modularização e manutenibilidade do código")
       - [Rota com Parâmetro Dinâmico e Filtragem por Chave Estrangeira no Prisma](#rota-com-par%C3%A2metro-din%C3%A2mico-e-filtragem-por-chave-estrangeira-no-prisma "Rota com Parâmetro Dinâmico e Filtragem por Chave Estrangeira no Prisma")
         - [Requisição da Rota no Componente React](#instru%C3%A7%C3%B5es-para-requisi%C3%A7%C3%A3o-da-rota-no-frontend-react "Requisição da Rota no Componente React")
     - [Função Genérica para Consultas e Operações CRUD com Prisma](#fun%C3%A7%C3%A3o-gen%C3%A9rica-para-consultas-e-opera%C3%A7%C3%B5es-crud-com-prisma "Função Genérica para Consultas e Operações CRUD com Prisma")
       - [1. Estrutura Básica da Função CRUD Genérica](#1-estrutura-b%C3%A1sica-da-fun%C3%A7%C3%A3o-crud-gen%C3%A9rica "1. Estrutura Básica da Função CRUD Genérica")
       - [2. Como Funciona](#2-como-funciona "2. Como Funciona")
       - [3. Exemplo de Uso](#3-exemplo-de-uso "3. Exemplo de Uso")
         - [Busca de um item específico (findUnique)](#busca-de-um-item-espec%C3%ADfico-findunique "Busca de um item específico (findUnique)")
         - [Criação de um novo item (create)](#cria%C3%A7%C3%A3o-de-um-novo-item-create "Criação de um novo item (create)")
         - [Atualização de um item (update)](#atualiza%C3%A7%C3%A3o-de-um-item-update "Atualização de um item (update)")
         - [Exclusão de um item (delete)](#exclus%C3%A3o-de-um-item-delete "Exclusão de um item (delete)")
       - [4. Considerações Importantes](#4-considera%C3%A7%C3%B5es-importantes "4. Considerações Importantes")
       - [5. Extensão para Outros Parâmetros](#5-extens%C3%A3o-para-outros-par%C3%A2metros "5. Extensão para Outros Parâmetros")
2. **Paginação de Listas com React e Prisma**
   - [Componente de Paginação Genérico para Listas](#componente-de-pagina%C3%A7%C3%A3o-gen%C3%A9rico-para-listas "Componente de Paginação Genérico para Listas")
     - [Arquivo de Rota: `routes.ts`](#arquivo-routests "Arquivo de Rota: `routes.ts`")
     - [Componente de Paginação: `index.jsx`](#arquivo-indexjsx "Componente de Paginação: `index.jsx`")
   - [Outro exemplo genérico com botões ilimitados com Reticências (...)](#outro-exemplo-gen%C3%A9rico-com-bot%C3%B5es-ilimitados-com-retic%C3%AAncias- "Outro exemplo genérico com botões ilimitados com Reticências (...)")
     - [Passo 1: Criar a Função de Geração de Páginas](#passo-1-criar-a-fun%C3%A7%C3%A3o-de-gera%C3%A7%C3%A3o-de-p%C3%A1ginas "Passo 1: Criar a Função de Geração de Páginas")
     - [Passo 2: Implementar a Exibição de Botões de Paginação](#passo-2-implementar-a-exibi%C3%A7%C3%A3o-de-bot%C3%B5es-de-pagina%C3%A7%C3%A3o "Passo 2: Implementar a Exibição de Botões de Paginação")
3. **Trabalhando Fenestra, API de janelas para react/redux**
   - **Corrigindo problemas**
     - Formulário simples de cadastro com validação de campos
   - **Manipulação de Estilos e Classes em Componentes Modais**
     - [Adicionando Classe na Div Mãe](#adicionando-classe-na-div-m%C3%A3e "Adicionando Classe na Div Mãe")
4. **Testes e Simulações de Interface**
   - **Preenchimento Automático de Formulários com JavaScript Nativo**
     - [Preencher diferentes tipos de campos usando o console do navegador](#preencher-diferentes-tipos-de-campos-usando-o-console-do-navegador "Preencher diferentes tipos de campos usando o console do navegador")
5. **Configuração e Segurança em Projetos React**
   - **Uso de Variáveis de Ambiente com Arquivo .env no React**
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
6. **Manipulação de Arrays em JavaScript**
   - [Obter dados de um `Array` com o `map()`](#obter-dados-de-um-array-com-map "Obter dados de um Array com map()")
   - [Executar Array dentro do retorno de um componente](#executar-array-dentro-do-retorno-de-um-componente "Executar Array dentro do retorno de um componente")
   - [Mapeamento direto no map()](#mapeamento-direto-no-map "Mapeamento direto no map()")
   - [Pequenos macetes de Array](#pequenos-macetes-de-array "Pequenos macetes de Array")
      - [Filtrar itens mistos de um array](#filtrar-itens-mistos-de-um-array "Filtrar itens mistos de um array")
      - [Filtrar os números ímpares de um array](#filtrar-os-n%C3%BAmeros-%C3%ADmpares-de-um-array "Filtrar os números ímpares de um array")
      - [Retornar o index da idade maior que 30 anos](#retornar-o-index-da-idade-maior-que-30-anos "Retornar o index da idade maior que 30 anos")
   - [Array `map()`, `filter()` e `reduce()`](#array-map-filter-e-reduce "Array map(), filter() e reduce()")
      - [Array map()](#array-map "Array map()")
      - [Array filter()](#array-filter "Array filter()")
      - [Array reduce()](#array-reduce "Array reduce()")
7. **Resolução de Problemas e Manutenção do Projeto**
   - [Reinstalar Dependências para Resolver Problemas de Configuração ou Conflitos de CORS](#reinstalar-depend%C3%AAncias-para-resolver-problemas-de-configura%C3%A7%C3%A3o-ou-conflitos-de-cors "Reinstalar Dependências para Resolver Problemas de Configuração ou Conflitos de CORS")
8. **Estrutura e Implementação de Componentes**
   - **Abas com Props para Componentes**
     - [Implementação de Componente com Abas no React-Bootstrap e Props para Identificação Única](#implementa%C3%A7%C3%A3o-de-abas-com-props-para-componentes "Implementação de Componente com Abas no React-Bootstrap e Props para Identificação Única")
     - [Passagem de Props e Uso de Hooks em Componentes Filhos de Abas](#componentes-filhos---exemplo-com-systemsettings_backgroundcategory "Passagem de Props e Uso de Hooks em Componentes Filhos de Abas")
9. **Envio de Emails e Comunicação Backend**
   - **Envio de Emails com Nodemailer**
     - [Estrutura de Diretórios para Projeto de Envio de Emails](#estrutura-de-diret%C3%B3rios-para-projeto-de-envio-de-emails "Estrutura de Diretórios para Projeto de Envio de Emails")
     - [Configuração do Servidor com Express e Nodemailer](#configura%C3%A7%C3%A3o-do-servidor-com-express-e-nodemailer "Configuração do Servidor com Express e Nodemailer")
     - [Criação da Rota para Envio de Email com Nodemailer](#cria%C3%A7%C3%A3o-da-rota-para-envio-de-email-com-nodemailer "Criação da Rota para Envio de Email com Nodemailer")
     - [Integração com o Frontend (React)](#integra%C3%A7%C3%A3o-com-o-frontend-react "Integração com o Frontend (React)")
     - [Uso de Arquivo `.env` para Configurações Sensíveis](#uso-de-arquivo-env-para-configura%C3%A7%C3%B5es-sens%C3%ADveis "Uso de Arquivo .env para Configurações Sensíveis")
     - [Instruções para Executar o Projeto](#instru%C3%A7%C3%B5es-para-executar-o-projeto "Instruções para Executar o Projeto")

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

Aqui está uma forma genérica para que você possa utilizá-la em outros componentes, com adaptações necessárias.

Para formatar os dados retornados pela consulta em um array com a estrutura desejada em JSON, siga os passos abaixo:

```jsx
// Realizar a chamada à API para buscar dados e formatá-los conforme o necessário.
const [dataList, setDataList] = useState([]);
useEffect(() => {
  Api.get(`/entityEndpoint/${parameter}`).then((res) => {
    const formattedData = res.data.map((item) => ({
      image: `/img/entities/${item.imageField}`, // Exemplo: ajuste conforme necessário
      title: item.titleField,                    // Exemplo: ajuste conforme necessário
      category: item.categoryField,              // Exemplo: ajuste conforme necessário
      date: item.dateField,                      // Exemplo: ajuste conforme necessário
    }));
    setDataList(formattedData);
  });
}, [parameter]);

console.log(dataList); // Exibe os dados formatados no console.
```

> **Nota:** A chamada à API deve ser realizada dentro do componente React.

### Explicação do Código

1. **Chamada à API**: Usamos `Api.get()` para realizar a requisição, passando o `parameter` dinâmico para a URL do endpoint. O `parameter` pode ser um ID ou categoria, dependendo da aplicação.
2. **Formatação dos Dados**: O método `map()` percorre cada item da resposta da API, criando um novo array `formattedData` com a estrutura desejada.
3. **Definindo o Estado**: Usamos `setDataList` para atualizar o estado `dataList` com o array `formattedData`, que contém os dados formatados.
4. **Exibindo no Console**: O `console.log(dataList)` permite verificar os dados formatados, facilitando a depuração.

### Observações Importantes

- **Campos da API**: Certifique-se de que os campos `imageField`, `titleField`, `categoryField` e `dateField` correspondem aos nomes corretos na resposta da API. Substitua-os conforme necessário.
- **Hooks React**: Este código usa `useState` para armazenar os dados e `useEffect` para executar a chamada à API. O `useEffect` é configurado para ser executado apenas uma vez ou quando `parameter` é alterado.
- **Atualização Condicional**: Adicione `parameter` como dependência no `useEffect` para refazer a consulta quando o valor de `parameter` mudar.

### Exemplo Completo

> Este código realiza uma requisição para buscar dados da API, formata os dados e os armazena em um estado do componente. É útil para exibir listas, catálogos ou outras coleções com uma estrutura específica.



Você pode adaptar essa estrutura para qualquer componente que precise buscar, formatar e exibir dados!

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

## Rota de Leitura de Registros (Read) com Prisma e Requisição no Frontend

### Rota Backend: Listagem de Registros (Read)

Essa rota `GET` buscará todos os registros de uma tabela no banco de dados e retornará os dados em formato JSON.

#### **Exemplo da Rota no Backend (Node.js/Express)**

```ts
// Rota genérica para listar todos os registros
routes.get('/getEntities', async (req, res) => {
    try {
        // Buscar todos os registros na tabela especificada
        const entities = await prisma.entity.findMany({
            orderBy: { createdAt: 'desc' } // Ordena por data de criação, adapte conforme necessário
        });

        return res.status(200).json(entities);
    } catch (error) {
        console.error('Erro ao buscar registros:', error);
        return res.status(500).json({ error: 'Erro ao buscar registros' });
    }
});
```

#### **Instruções para Adaptação**:
- **Nome da Rota**: Substitua `'/getEntities'` pelo endpoint desejado, como `'/getUsers'` ou `'/getProducts'`.
- **Tabela (Entidade)**: Substitua `entity` pelo nome da tabela real no seu `schema.prisma` (ex.: `users`, `products`).
- **Ordenação**: Ajuste `orderBy` conforme necessário (ex.: ordenação por `id`, `title`, etc.).

---

### Requisição no Frontend (React)

No frontend, criaremos uma função que realiza uma requisição `GET` para buscar os registros e exibi-los em uma lista.

#### **Exemplo de Requisição para Listar Registros**

```jsx
import React, { useEffect, useState } from 'react';

function EntityList() {
    const [entities, setEntities] = useState([]);
    const [error, setError] = useState(null);

    useEffect(() => {
        async function fetchData() {
            try {
                const response = await fetch('http://localhost:5000/getEntities');
                if (!response.ok) throw new Error('Erro ao buscar registros');

                const data = await response.json();
                setEntities(data);
            } catch (error) {
                console.error('Erro de rede ou servidor:', error);
                setError('Erro ao buscar registros. Tente novamente mais tarde.');
            }
        }

        fetchData();
    }, []);

    if (error) return <p>{error}</p>;

    return (
        <div>
            <h2>Lista de Registros</h2>
            <ul>
                {entities.map((entity) => (
                    <li key={entity.id}>
                        <h3>{entity.title}</h3> {/* Exemplo: ajuste conforme os campos */}
                        <p>{entity.description}</p> {/* Exemplo: ajuste conforme os campos */}
                    </li>
                ))}
            </ul>
        </div>
    );
}

export default EntityList;
```

#### **Instruções para Adaptação**:
- **URL da Requisição**: Substitua `'http://localhost:5000/getEntities'` pela URL correta do endpoint.
- **Campos do Item**: Ajuste `entity.title` e `entity.description` para os campos reais da resposta da API.

#### **Resumo das Etapas**:
1. **Backend**: Configure a rota `GET /getEntities` para retornar todos os registros da tabela.
2. **Frontend**: Use `useEffect` para realizar a requisição `GET` ao montar o componente.
3. **Exibição**: Mapeie o array `entities` para exibir os dados no frontend.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Rota de Atualização de Registro (Update) com Prisma e Requisição no Frontend

### Rota Backend: Atualização de Registro (Update)

Essa rota `PUT` permite atualizar um registro específico com base em seu `ID`.

#### **Exemplo da Rota no Backend (Node.js/Express)**

```ts
// Rota genérica para atualizar um registro pelo ID
routes.put('/updateEntity/:id', async (req, res) => {
    const { id } = req.params;
    const { title, description } = req.body; // Adapte os campos conforme necessário

    try {
        // Verificar se o registro existe antes de atualizar
        const entityExists = await prisma.entity.findUnique({
            where: { id: parseInt(id) },
        });

        if (!entityExists) {
            return res.status(404).json({ error: 'Registro não encontrado' });
        }

        // Atualizar o registro no banco de dados
        const updatedEntity = await prisma.entity.update({
            where: { id: parseInt(id) },
            data: {
                title,
                description,
            }
        });

        return res.status(200).json(updatedEntity);
    } catch (error) {
        console.error('Erro ao atualizar registro:', error);
        return res.status(500).json({ error: 'Erro ao atualizar registro' });
    }
});
```

#### **Instruções para Adaptação**:
- **Nome da Rota**: Substitua `'/updateEntity/:id'` pelo endpoint desejado, como `'/updateUser/:id'`.
- **Tabela (Entidade)**: Substitua `entity` pelo nome real da tabela no `schema.prisma` (ex.: `users`, `products`).
- **Campos**: Ajuste `title` e `description` para os campos da tabela que deseja atualizar.

---

### Requisição no Frontend (React)

No frontend, criaremos uma função para enviar uma requisição `PUT` com os dados atualizados para essa rota.

#### **Exemplo de Requisição para Atualizar um Registro**

```jsx
import React, { useState, useEffect } from 'react';

function UpdateEntityForm({ entityId }) {
    const [title, setTitle] = useState('');
    const [description, setDescription] = useState('');
    const [message, setMessage] = useState('');

    useEffect(() => {
        // Busca os dados atuais para preenchimento inicial do formulário
        async function fetchEntityData() {
            try {
                const response = await fetch(`http://localhost:5000/getEntity/${entityId}`);
                if (response.ok) {
                    const data = await response.json();
                    setTitle(data.title);
                    setDescription(data.description);
                }
            } catch (error) {
                console.error('Erro ao buscar registro:', error);
            }
        }

        fetchEntityData();
    }, [entityId]);

    async function handleSubmit(event) {
        event.preventDefault();

        const updatedData = {
            title,
            description,
        };

        try {
            const response = await fetch(`http://localhost:5000/updateEntity/${entityId}`, {
                method: 'PUT',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify(updatedData)
            });

            if (response.ok) {
                const data = await response.json();
                setMessage('Registro atualizado com sucesso!');
                console.log('Registro atualizado:', data);
            } else {
                const errorData = await response.json();
                console.error('Erro ao atualizar registro:', errorData);
                setMessage('Erro ao atualizar registro. Tente novamente.');
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
                <button type="submit">Atualizar Registro</button>
            </form>
            {message && <p>{message}</p>}
        </div>
    );
}

export default UpdateEntityForm;
```

#### **Instruções para Adaptação**:
- **URL da Requisição**: Substitua `'http://localhost:5000/updateEntity/${entityId}'` com a URL correta da API.
- **Campos do Formulário**: Ajuste `title` e `description` para os campos que deseja atualizar no formulário.

#### **Resumo das Etapas**:
1. **Backend**: Crie a rota `PUT /updateEntity/:id` para atualizar os dados de um registro específico com base no `ID`.
2. **Frontend**: Use um formulário em React com os valores iniciais preenchidos. Submeta os dados atualizados para a rota `PUT`.
3. **Requisição e Feedback**: Trate a resposta da requisição e exiba uma mensagem de sucesso ou erro.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Rota de Exclusão de Registro (Delete) com Prisma e Requisição no Frontend

### Rota Backend: Exclusão de Registro (Delete)

Essa rota `DELETE` permite excluir um registro específico com base em seu `ID`.

#### **Exemplo da Rota no Backend (Node.js/Express)**

```ts
// Rota genérica para excluir um registro pelo ID
routes.delete('/deleteEntity/:id', async (req, res) => {
    const { id } = req.params;

    try {
        // Verificar se o registro existe antes de excluir
        const entityExists = await prisma.entity.findUnique({
            where: { id: parseInt(id) },
        });

        if (!entityExists) {
            return res.status(404).json({ error: 'Registro não encontrado' });
        }

        // Excluir o registro no banco de dados
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
- **Nome da Rota**: Substitua `'/deleteEntity/:id'` pelo endpoint desejado, como `'/deleteUser/:id'`.
- **Tabela (Entidade)**: Substitua `entity` pelo nome real da tabela no `schema.prisma` (ex.: `users`, `products`).
- **Verificação de Existência**: A verificação `findUnique` garante que o registro existe antes de tentar excluí-lo, evitando erros.

---

### Requisição no Frontend (React)

No frontend, criaremos uma função que faz uma requisição `DELETE` para essa rota com o ID do registro que queremos excluir.

#### **Exemplo de Requisição para Excluir um Registro**

```jsx
import React, { useState } from 'react';

function DeleteEntityButton({ entityId, onDelete }) {
    const [message, setMessage] = useState('');

    async function handleDelete() {
        try {
            const response = await fetch(`http://localhost:5000/deleteEntity/${entityId}`, {
                method: 'DELETE',
                headers: {
                    'Content-Type': 'application/json'
                }
            });

            if (response.ok) {
                setMessage('Registro excluído com sucesso!');
                console.log('Registro excluído:', entityId);

                // Acionar a função callback para atualizar a lista
                if (onDelete) onDelete(entityId);
            } else {
                const errorData = await response.json();
                console.error('Erro ao excluir registro:', errorData);
                setMessage('Erro ao excluir registro. Tente novamente.');
            }
        } catch (error) {
            console.error('Erro de rede ou servidor:', error);
            setMessage('Erro de rede ou servidor. Tente novamente mais tarde.');
        }
    }

    return (
        <div>
            <button onClick={handleDelete}>Excluir Registro</button>
            {message && <p>{message}</p>}
        </div>
    );
}

export default DeleteEntityButton;
```

#### **Instruções para Adaptação**:
- **URL da Requisição**: Substitua `'http://localhost:5000/deleteEntity/${entityId}'` pelo endpoint correto da API.
- **Callback `onDelete`**: Utilize `onDelete` para atualizar a lista de registros no frontend após a exclusão, se necessário.
- **Mensagens**: Personalize as mensagens de sucesso ou erro exibidas ao usuário.

#### **Resumo das Etapas**:
1. **Backend**: Configure a rota `DELETE /deleteEntity/:id` para excluir o registro com o ID fornecido.
2. **Frontend**: Use um botão em React que chama a função `handleDelete` para realizar a exclusão.
3. **Callback para Atualização**: Opcionalmente, use `onDelete` para atualizar a lista de registros no frontend após a exclusão.

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

## Como mover a lógica de rotas para controllers para melhor organização

Organizar as rotas em controllers ajuda a manter o código do backend mais modular e fácil de manter. Veja exemplos genéricos de controllers para cada parte do CRUD (Create, Read, Update, Delete) e uma estrutura para as rotas no Express que pode ser facilmente adaptada.

---

## Estrutura Geral dos Controllers no Backend

### Organização de Pastas

Organize seu projeto em pastas para separar as rotas e controllers:

```
./project-root
├─ ./controllers/
│   └─ ./entityController.js
│
├─ ./routes/
│   └─ ./entityRoutes.js
│
├─ ./prisma/
│   └─ ./schema.prisma
│
├─ ./app.js
└─ ./server.js
```

1. **controllers/**: Contém todos os arquivos de controllers, cada um com a lógica de CRUD para uma entidade.
2. **routes/**: Contém os arquivos de rotas, onde associamos as rotas às funções do controller.
3. **app.js/server.js**: Arquivos de configuração do Express, onde as rotas são importadas e registradas.

---

## Exemplo Genérico de Controller (entityController.js)

No arquivo `entityController.js`, criamos as funções para cada operação CRUD. Essas funções serão chamadas pelas rotas.

```javascript
// controllers/entityController.js

const { PrismaClient } = require('@prisma/client');
const prisma = new PrismaClient();

// Função para criar um novo registro (Create)
exports.createEntity = async (req, res) => {
    const { title, description } = req.body;

    try {
        const newEntity = await prisma.entity.create({
            data: { title, description }
        });
        res.status(201).json(newEntity);
    } catch (error) {
        console.error('Erro ao criar registro:', error);
        res.status(500).json({ error: 'Erro ao criar registro' });
    }
};

// Função para listar todos os registros (Read)
exports.getEntities = async (req, res) => {
    try {
        const entities = await prisma.entity.findMany({
            orderBy: { createdAt: 'desc' }
        });
        res.status(200).json(entities);
    } catch (error) {
        console.error('Erro ao buscar registros:', error);
        res.status(500).json({ error: 'Erro ao buscar registros' });
    }
};

// Função para buscar um registro por ID (Read)
exports.getEntityById = async (req, res) => {
    const { id } = req.params;

    try {
        const entity = await prisma.entity.findUnique({
            where: { id: parseInt(id) }
        });
        if (!entity) {
            return res.status(404).json({ error: 'Registro não encontrado' });
        }
        res.status(200).json(entity);
    } catch (error) {
        console.error('Erro ao buscar registro:', error);
        res.status(500).json({ error: 'Erro ao buscar registro' });
    }
};

// Função para atualizar um registro por ID (Update)
exports.updateEntity = async (req, res) => {
    const { id } = req.params;
    const { title, description } = req.body;

    try {
        const updatedEntity = await prisma.entity.update({
            where: { id: parseInt(id) },
            data: { title, description }
        });
        res.status(200).json(updatedEntity);
    } catch (error) {
        console.error('Erro ao atualizar registro:', error);
        res.status(500).json({ error: 'Erro ao atualizar registro' });
    }
};

// Função para excluir um registro por ID (Delete)
exports.deleteEntity = async (req, res) => {
    const { id } = req.params;

    try {
        await prisma.entity.delete({
            where: { id: parseInt(id) }
        });
        res.status(200).json({ message: 'Registro excluído com sucesso' });
    } catch (error) {
        console.error('Erro ao excluir registro:', error);
        res.status(500).json({ error: 'Erro ao excluir registro' });
    }
};
```

### Explicação

- **CRUD**: Cada função realiza uma operação CRUD (Create, Read, Update, Delete).
- **Prisma**: Conexão com o banco de dados Prisma usando o modelo genérico `entity`. Substitua `entity` pelo nome específico da tabela, como `user` ou `product`.

---

## Exemplo Genérico de Rotas (entityRoutes.js)

No arquivo `entityRoutes.js`, definimos as rotas e associamos cada uma a uma função do controller.

```javascript
// routes/entityRoutes.js

const express = require('express');
const router = express.Router();
const entityController = require('../controllers/entityController');

// Rota para criar um novo registro (Create)
router.post('/createEntity', entityController.createEntity);

// Rota para listar todos os registros (Read)
router.get('/getEntities', entityController.getEntities);

// Rota para buscar um registro por ID (Read)
router.get('/getEntity/:id', entityController.getEntityById);

// Rota para atualizar um registro por ID (Update)
router.put('/updateEntity/:id', entityController.updateEntity);

// Rota para excluir um registro por ID (Delete)
router.delete('/deleteEntity/:id', entityController.deleteEntity);

module.exports = router;
```

### Explicação

- **Router do Express**: Cria uma instância de roteamento para associar as rotas às funções do controller.
- **Controller**: As funções do controller são importadas e associadas a cada rota.

---

## Registro das Rotas no Express (app.js)

No arquivo `app.js`, registre as rotas do `entityRoutes.js`.

```javascript
// app.js

const express = require('express');
const app = express();
const entityRoutes = require('./routes/entityRoutes');

app.use(express.json());

// Registrar as rotas
app.use('/api', entityRoutes);

app.listen(5000, () => {
    console.log('Servidor rodando na porta 5000');
});

module.exports = app;
```

### Explicação

- **Express JSON Middleware**: `app.use(express.json())` habilita o Express para processar JSON no corpo das requisições.
- **Rota Base**: `app.use('/api', entityRoutes)` registra todas as rotas do arquivo `entityRoutes` sob o caminho base `/api`. Assim, a rota `'/api/createEntity'` estará disponível.

---

### Resumo das Etapas

1. **Crie o Controller**: No arquivo `entityController.js`, defina as funções para cada operação CRUD.
2. **Defina as Rotas**: No arquivo `entityRoutes.js`, crie as rotas e associe cada uma à função correspondente do controller.
3. **Registre as Rotas**: No `app.js`, registre as rotas no Express.

Esse modelo genérico ajuda a manter a organização do backend e facilita a reutilização de código para diferentes entidades!

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Vantagens da modularização e manutenibilidade do código

A modularização e a manutenibilidade são princípios essenciais para manter um código organizado, fácil de entender e de modificar. Aqui estão algumas das principais vantagens de modularizar e manter o código com boas práticas:

### 1. **Facilidade de Leitura e Compreensão**
   - **Código Organizado**: Ao modularizar o código, cada arquivo e módulo é responsável por uma função específica. Isso facilita a leitura e a compreensão, pois o desenvolvedor sabe onde procurar uma funcionalidade específica.
   - **Divisão por Responsabilidade**: Cada módulo ou função tem uma responsabilidade única (princípio de responsabilidade única), tornando o propósito de cada parte mais claro.

### 2. **Reutilização de Código**
   - **Redução de Código Duplicado**: Com controllers, rotas e middlewares em arquivos separados, você evita a duplicação, reutilizando o mesmo código em diferentes partes da aplicação.
   - **Componentes Reutilizáveis**: Com módulos bem definidos, é possível reutilizar partes do sistema em outros projetos ou áreas do sistema, economizando tempo e esforço.

### 3. **Facilidade na Manutenção e Expansão**
   - **Atualizações Simplificadas**: Com a modularização, é fácil atualizar, corrigir ou substituir uma parte do sistema sem impactar o restante do código. Alterações em um módulo raramente afetam os outros, se as interfaces estiverem bem definidas.
   - **Facilidade em Adicionar Novas Funcionalidades**: Adicionar novas funcionalidades torna-se mais fácil, pois cada nova funcionalidade pode ser desenvolvida como um novo módulo, integrando-se facilmente ao sistema existente.

### 4. **Colaboração Eficiente em Equipe**
   - **Trabalho Paralelo**: Em um sistema modular, diferentes membros da equipe podem trabalhar em módulos diferentes sem conflitar. Por exemplo, um desenvolvedor pode trabalhar nos controllers enquanto outro trabalha nas rotas.
   - **Comunicação de Mudanças**: Mudanças em um módulo são mais previsíveis e podem ser comunicadas mais facilmente aos membros da equipe.

### 5. **Depuração e Testes Simplificados**
   - **Testes Modulares**: Testar cada módulo individualmente é muito mais fácil do que testar uma aplicação monolítica. Com a modularização, você pode criar testes unitários para cada controller ou função.
   - **Isolamento de Erros**: Ao modularizar o código, erros ficam isolados em um módulo específico, facilitando o rastreamento e a correção.

### 6. **Escalabilidade do Projeto**
   - **Suporte a Projetos Maiores**: Sistemas modulados suportam melhor o crescimento da aplicação. É possível adicionar novos módulos sem comprometer a arquitetura inicial.
   - **Estrutura Adaptável**: Em sistemas modulares, você pode adotar e integrar novas tecnologias em módulos específicos sem reescrever a base do sistema.

### 7. **Organização da Estrutura de Pastas**
   - **Padronização**: Ter uma estrutura de pastas organizada por módulos ou responsabilidades (como `controllers`, `routes`, `models`) torna o projeto mais fácil de navegar e reduz o tempo de desenvolvimento.
   - **Separação de Preocupações**: Com módulos separados para cada responsabilidade (ex.: controllers para lógica de negócios, routes para definir endpoints), cada camada do sistema fica clara e bem definida.

### Exemplos no Contexto de Controllers e Rotas

1. **Separação de Controllers e Rotas**:
   - A lógica de negócio é mantida nos controllers, enquanto as rotas ficam responsáveis apenas pelo roteamento. Isso permite que a lógica do backend seja testada e modificada independentemente das rotas.

2. **Modularização por Funcionalidade**:
   - Um sistema de e-commerce pode ter módulos como `usersController`, `productsController` e `ordersController`, cada um responsável por suas entidades e suas regras específicas, facilitando a expansão de funcionalidades em cada módulo.

3. **Facilidade na Atualização de Endpoints**:
   - Em um projeto modularizado, mudar a URL de um endpoint ou adicionar novos parâmetros em uma rota específica pode ser feito no módulo de rotas sem impactar o restante do código, mantendo a consistência.

Essas vantagens tornam a modularização uma prática essencial para qualquer projeto de desenvolvimento de software, especialmente à medida que o projeto cresce em complexidade e equipe.

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

## Função Genérica para Consultas e Operações CRUD com Prisma

### Implementando um CRUD Genérico com TypeScript e Prisma para Consultas Dinâmicas

Funções genéricas que realizam consultas ao banco de dados de forma dinâmica, utilizando parâmetros para definir as instruções da consulta. Esse CRUD a seguir é totalmente genérico e dinâmico em uma aplicação backend (especialmente com Prisma) precisa ser feita com cuidado para garantir segurança e boa organização.

Vou explicar o conceito de uma função genérica de CRUD usando **TypeScript** e **Prisma ORM**, onde você pode passar os parâmetros como nome da tabela (ou modelo do Prisma), tipo de operação (CRUD), filtros e outros parâmetros adicionais. Vou incluir um exemplo básico abaixo para ilustrar como isso pode ser feito.

### 1. Estrutura Básica da Função CRUD Genérica

Você pode criar um arquivo como `databaseService.ts` onde vai definir essa função. O objetivo é que ela receba os parâmetros, identifique o tipo de operação e faça a chamada adequada ao Prisma. Vou incluir um exemplo da estrutura:

```typescript
import { PrismaClient, Prisma } from '@prisma/client';

const prisma = new PrismaClient();

interface CrudParams {
  model: keyof PrismaClient; // Nome do modelo Prisma (tabela)
  action: 'findUnique' | 'findMany' | 'create' | 'update' | 'delete';
  data?: any; // Dados para criação/atualização
  where?: any; // Condições de busca
  select?: any; // Seleção de campos
  include?: any; // Relacionamentos a serem incluídos
}

async function genericCrud<T>({ model, action, data, where, select, include }: CrudParams): Promise<T | T[]> {
  try {
    const result = await (prisma[model] as any)[action]({
      ...(data && { data }),
      ...(where && { where }),
      ...(select && { select }),
      ...(include && { include }),
    });

    return result;
  } catch (error) {
    console.error(`Erro ao executar ${action} no modelo ${model}:`, error);
    throw error;
  }
}

export default genericCrud;
```

### 2. Como Funciona

A função `genericCrud` é uma função genérica que recebe um objeto `CrudParams` com as seguintes propriedades:

- `model`: Define o modelo Prisma (tabela) em que a operação será realizada.
- `action`: Define a ação CRUD a ser executada (`findUnique`, `findMany`, `create`, `update`, `delete`).
- `data`: Dados para criação ou atualização.
- `where`: Condições de filtro (equivalente ao `WHERE` em SQL).
- `select`: Permite selecionar campos específicos para retorno.
- `include`: Define os relacionamentos a serem carregados no retorno.

A função então utiliza o modelo e a ação passados para chamar a operação Prisma correspondente.

### 3. Exemplo de Uso

Para utilizar a função, você pode chamá-la passando os parâmetros específicos de cada operação. Por exemplo:

#### Busca de um item específico (`findUnique`)

```typescript
const user = await genericCrud({
  model: 'user', // Nome do modelo Prisma
  action: 'findUnique',
  where: { id: 1 }, // Condição para buscar o usuário de ID 1
});
```

#### Criação de um novo item (`create`)

```typescript
const newUser = await genericCrud({
  model: 'user',
  action: 'create',
  data: {
    name: 'John Doe',
    email: 'johndoe@example.com',
  },
});
```

#### Atualização de um item (`update`)

```typescript
const updatedUser = await genericCrud({
  model: 'user',
  action: 'update',
  where: { id: 1 },
  data: {
    email: 'newemail@example.com',
  },
});
```

#### Exclusão de um item (`delete`)

```typescript
const deletedUser = await genericCrud({
  model: 'user',
  action: 'delete',
  where: { id: 1 },
});
```

### 4. Considerações Importantes

1. **Segurança**: Um CRUD genérico assim é flexível, mas também pode ser arriscado se o acesso for exposto sem controle. Verifique sempre a autenticação e a autorização antes de permitir que qualquer usuário faça operações diretamente na base de dados.
  
2. **Validação**: Esse exemplo permite uma entrada bastante dinâmica, então você precisa validar bem os parâmetros para evitar erros e garantir que apenas operações seguras sejam permitidas.

3. **Tipos Genéricos**: A função usa `<T>` para indicar que o tipo de retorno é genérico, então ela pode retornar qualquer tipo de dado baseado no modelo usado. Isso facilita no TypeScript, pois o retorno sempre será tipado.

### 5. Extensão para Outros Parâmetros

Caso você queira incluir outros tipos de comportamento, como passar o tipo de retorno e condições adicionais, considere expandir o `CrudParams` para incluir essas opções, sempre com validações para manter o código seguro.

Essa estrutura dá flexibilidade para um CRUD genérico usando Prisma e TypeScript, além de ser escalável e fácil de adaptar.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Componente de Paginação Genérico para Listas

Esse componente genérico permite a paginação de listas grandes no frontend sem a necessidade de carregar todos os dados de uma vez. Ele funciona com chamadas ao servidor para carregar apenas os itens necessários para a página atual, reduzindo o uso de memória e melhorando o desempenho. Esse exemplo utiliza uma lista simples de itens, renderizados como parágrafos (`<p>...</p>`).

#### Arquivo: `routes.ts`
```typescript
// Rota para buscar itens com paginação
routes.get('/items/:companyId', async (req, res) => {
    const { companyId } = req.params;
    const page = parseInt(req.query.page as string) || 1; // Página atual (1 por padrão)
    const limit = parseInt(req.query.limit as string) || 10; // Limite de itens por página (10 por padrão)
    const skip = (page - 1) * limit; // Calcular quantos registros pular com base na página

    try {
        const items = await prisma.items.findMany({
            where: { company_id: Number(companyId) },
            orderBy: { id: 'desc' },
            skip: skip,
            take: limit
        });

        const totalItems = await prisma.items.count({
            where: { company_id: Number(companyId) }
        });

        res.status(200).json({
            data: items,
            totalPages: Math.ceil(totalItems / limit),
            currentPage: page
        });
    } catch (error) {
        console.error('Erro ao buscar itens:', error);
        res.status(500).json({ error: 'Erro ao buscar itens' });
    }
});
```

**Explicação da rota:**

Essa rota implementa a paginação no servidor usando Prisma. Ela recebe o `companyId` como parâmetro e os parâmetros de consulta `page` e `limit` para determinar a página atual e o número de itens por página. A rota:
- **Filtra pelos registros** do `company_id` correspondente.
- **Ordena** os registros por `id` em ordem decrescente.
- **Aplica paginação** usando `skip` e `take` para definir o intervalo de itens a serem retornados.
- **Retorna a página de itens** e o número total de páginas (`totalPages`), permitindo que o frontend saiba quantas páginas existem para navegação.

#### Arquivo: `index.jsx`
```javascript
import React, { useEffect, useState } from 'react';
import { Button } from 'react-bootstrap';
import { Api } from '../../server/api';

export function PaginatedList() {
    const [items, setItems] = useState([]); // Itens a serem exibidos
    const [page, setPage] = useState(1); // Página atual
    const [totalPages, setTotalPages] = useState(1); // Total de páginas
    const limit = 10; // Número de itens por página

    // Função para buscar itens paginados
    const fetchItems = async (currentPage) => {
        try {
            const storedUser = JSON.parse(localStorage.getItem('user'));
            const companyId = storedUser?.company_id;
            const response = await Api.get(`/items/${companyId}?page=${currentPage}&limit=${limit}`);
            
            setItems(response.data.data); // Define os itens para a página atual
            setTotalPages(response.data.totalPages); // Define o total de páginas
            setPage(response.data.currentPage); // Define a página atual
        } catch (error) {
            console.error("Erro ao carregar itens:", error);
        }
    };

    useEffect(() => {
        fetchItems(page); // Carrega os itens ao montar o componente e ao mudar de página
    }, [page]);

    // Funções de navegação
    const handlePreviousPage = () => {
        if (page > 1) setPage(page - 1);
    };

    const handleNextPage = () => {
        if (page < totalPages) setPage(page + 1);
    };

    return (
        <div>
            <div>
                {items.map((item, index) => (
                    <p key={index}>{item.name}</p> // Renderiza cada item como um parágrafo
                ))}
            </div>
            <div className="pagination-controls">
                <Button onClick={handlePreviousPage} disabled={page === 1}>Anterior</Button>
                <span>Página {page} de {totalPages}</span>
                <Button onClick={handleNextPage} disabled={page === totalPages}>Próxima</Button>
            </div>
        </div>
    );
}
```

**Explicação da chamada:**

1. **Estados do componente**:
   - `items`: Armazena os itens da página atual, recebidos do backend.
   - `page`: Controla a página atual.
   - `totalPages`: Armazena o número total de páginas, permitindo controlar a navegação.

2. **Função `fetchItems`**:
   - Chama a API para buscar os itens paginados, passando `page` e `limit` como parâmetros para controlar a quantidade de dados recebida.
   - Usa o `companyId` do usuário armazenado no `localStorage` para buscar apenas os itens da empresa correspondente.

3. **Navegação entre páginas**:
   - `handlePreviousPage` e `handleNextPage` atualizam o estado `page` para a página anterior ou próxima, respeitando os limites (primeira e última página).
   
4. **Renderização**:
   - Cada item é renderizado como um parágrafo (`<p>`).
   - Os botões de navegação permitem ao usuário mudar de página, com uma indicação visual da página atual e do total de páginas.

Esse modelo pode ser usado para qualquer lista, bastando modificar o layout dos itens em `items.map(...)`.

***A exemplo de teste, crie uma tabela com o nome `test_table` e execute os INSERTs abaixo***

![Tabela para testes](./images/Table_for_tests.png "Crie a tabela e faça testes!")

Aqui está o código SQL para criar a tabela conforme a estrutura mostrada na imagem:

```sql
CREATE TABLE test_table (
    id INT(10) UNSIGNED NOT NULL AUTO_INCREMENT,
    item_description VARCHAR(255),
    registration_date DATE,
    registration_time TIME,
    company_id INT(11),
    PRIMARY KEY (id)
);
```

### Explicação:
- `id`: Chave primária da tabela, com incremento automático e tipo inteiro não assinado.
- `item_description`: Campo de texto de até 255 caracteres.
- `registration_date`: Armazena apenas a data.
- `registration_time`: Armazena apenas o horário.
- `company_id`: Campo do tipo inteiro.

Este código criará a tabela exatamente como descrita na imagem.

**Abaixo segue os `INSERTs` para inserir dados para teste:**

```sql
INSERT INTO test_table (item_description, registration_date, registration_time, company_id) VALUES
                       ('Item Demo',      '2024-12-30',      '21:49:38',        1),
                       ('Item Demo',      '2024-12-30',      '21:49:38',        1),
                       ('Item Demo',      '2024-12-30',      '21:49:38',        1),
                       ('Item Demo',      '2024-12-30',      '21:49:38',        1),
                       ('Item Demo',      '2024-12-30',      '21:49:38',        1),
                       ('Item Demo',      '2024-12-30',      '21:49:38',        1),
                       ('Item Demo',      '2024-12-30',      '21:49:38',        1),
                       ('Item Demo',      '2024-12-30',      '21:49:38',        1),
                       ('Item Demo',      '2024-12-30',      '21:49:38',        1),
                       ('Item Demo',      '2024-12-30',      '21:49:38',        1);
```

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Outro exemplo genérico com botões ilimitados com Reticências (...)

Para implementar uma paginação customizada no estilo da imagem, podemos criar uma lógica que gera os botões de página com "..." quando há muitas páginas. Essa abordagem melhora a experiência do usuário ao permitir a navegação direta para as primeiras e últimas páginas, além de exibir a página atual e algumas páginas ao redor.

|  <   |  1   |  2   |  3   | ...  |  10  |  11  |  12  | ...  |  18  |  19  |  20  |  >   |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |

> Exemplo com Bootstrap

[![Início](./images/Pagination_Example.png)](# "Exemplo de paginação com o Bootstrap")

Abaixo está uma modificação no código de paginação, que adiciona essa lógica e gera os botões conforme o layout solicitado.

### ( i ) A rota é a da diga anterior, [clique aqui](#arquivo-routests "clique aqui").

### Passo 1: Criar a Função de Geração de Páginas

Essa função gera os números de página, adicionando "..." quando necessário, para manter o design mais compacto.

> ( ! ) Esta função já está incrementada no código seguinte fora do componente na parte inferior, não repita!

```javascript
// Função para gerar números de página com "..."
function generatePageNumbers(currentPage, totalPages) {
    const pageNumbers = [];

    if (totalPages <= 10) {
        // Caso total de páginas seja 10 ou menos, exibir todas as páginas
        for (let i = 1; i <= totalPages; i++) {
            pageNumbers.push(i);
        }
    } else {
        // Exibir as três primeiras, três últimas e três ao redor da página atual
        pageNumbers.push(1, 2, 3);

        if (currentPage > 5) {
            pageNumbers.push("..."); // Adiciona "..." após as primeiras páginas
        }

        const start = Math.max(4, currentPage - 1);
        const end = Math.min(totalPages - 3, currentPage + 1);

        for (let i = start; i <= end; i++) {
            pageNumbers.push(i);
        }

        if (currentPage < totalPages - 4) {
            pageNumbers.push("..."); // Adiciona "..." antes das últimas páginas
        }

        pageNumbers.push(totalPages - 2, totalPages - 1, totalPages);
    }

    return pageNumbers;
}
```

### Passo 2: Implementar a Exibição de Botões de Paginação

No componente principal, modifique o bloco de paginação para usar a função `generatePageNumbers` e renderizar os botões conforme o layout desejado.

```javascript
import React, { useEffect, useState } from 'react';
import { Button } from 'react-bootstrap';
import { Api } from '../../server/api';

export function PaginatedList() {
    const [items, setItems] = useState([]);
    const [page, setPage] = useState(1);
    const [totalPages, setTotalPages] = useState(1);
    const limit = 10;

    const fetchItems = async (currentPage) => {
        try {
            // (!) As variáveis 'storedUser' e 'companyId' recuperam uma informação no 'localStorage',
            // se não forem necessárias, pode removê-las daqui e na rota!
            const storedUser = JSON.parse(localStorage.getItem('user'));
            const companyId = storedUser?.company_id;

            const response = await Api.get(`/items/${companyId}?page=${currentPage}&limit=${limit}`);
            
            setItems(response.data.data);
            setTotalPages(response.data.totalPages);
            setPage(response.data.currentPage);
        } catch (error) {
            console.error("Erro ao carregar itens:", error);
        }
    };

    useEffect(() => {
        fetchItems(page);
    }, [page]);

    const handlePreviousPage = () => {
        if (page > 1) setPage(page - 1);
    };

    const handleNextPage = () => {
        if (page < totalPages) setPage(page + 1);
    };

    // Função que gera o layout de botões com "..."
    const renderPageButtons = () => {
        const pageNumbers = generatePageNumbers(page, totalPages);

        return pageNumbers.map((pageNum, index) => (
            <Button
                key={index}
                variant={pageNum === page ? "secondary" : "primary"}
                onClick={() => typeof pageNum === "number" && setPage(pageNum)}
                disabled={pageNum === "..."}
            >
                {pageNum}
            </Button>
        ));
    };

    return (
        <div>
            <div>
                {items.map((item, index) => (
                    <p key={index}>{item.name}</p>
                ))}
            </div>
            <div className="pagination-controls" style={{ display: 'flex', gap: '4px', alignItems: 'center' }}>
                <Button onClick={handlePreviousPage} disabled={page === 1}>{"<"}</Button>
                    {renderPageButtons()}
                <Button onClick={handleNextPage} disabled={page === totalPages}>{">"}</Button>
            </div>
        </div>
    );
}

// Função para gerar números de página com "..."
function generatePageNumbers(currentPage, totalPages) {
    const pageNumbers = [];

    if (totalPages <= 10) {
        for (let i = 1; i <= totalPages; i++) {
            pageNumbers.push(i);
        }
    } else {
        pageNumbers.push(1, 2, 3);

        if (currentPage > 5) {
            pageNumbers.push("...");
        }

        const start = Math.max(4, currentPage - 1);
        const end = Math.min(totalPages - 3, currentPage + 1);

        for (let i = start; i <= end; i++) {
            pageNumbers.push(i);
        }

        if (currentPage < totalPages - 4) {
            pageNumbers.push("...");
        }

        pageNumbers.push(totalPages - 2, totalPages - 1, totalPages);
    }

    return pageNumbers;
}
```

### Explicação da Lógica

1. **Função `generatePageNumbers`**:
   - Gera os números de página a serem exibidos, adicionando "..." quando há muitas páginas.
   - Quando o total de páginas é 10 ou menos, exibe todos os números.
   - Quando o total é maior, exibe as três primeiras, três últimas e três páginas ao redor da página atual.

2. **Função `renderPageButtons`**:
   - Usa `generatePageNumbers` para gerar o layout de botões.
   - Adiciona a classe `primary` no botão da página atual e `secondary` nos outros.

3. **Navegação**:
   - Botões de navegação `"<"` e `">"` permitem avançar e retroceder nas páginas, e estão desativados quando atingem o início ou o final.

### Resultado Esperado

A exibição dos botões de paginação deve ficar parecida com o modelo solicitado:
- Exibindo as três primeiras páginas, a página atual com duas ao redor dela, e as três últimas páginas.
- Exibindo "..." para indicar páginas intermediárias quando aplicável.

Esse layout otimiza a navegação para listas extensas, mantendo a interface simples e acessível.

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

## Obter dados de um Array com `map()`

Crie um arquivo como por exemplo `data.js`:

```jsx
export default [
    { id:1, option: 'Opção 1' },
    { id:2, option: 'Opção 2' },
    { id:3, option: 'Opção 3' },
    { id:4, option: 'Opção 4' },
    { id:5, option: 'Opção 5' },
    { id:6, option: 'Opção 6' },
    { id:7, option: 'Opção 7' },
    { id:8, option: 'Opção 8' }
]
```

> Cada linha entre as chaves, vamos fazer de conta que é um registro!

Importe o arquivo no componente:

```jsx
// Arquivo de dados onde estão os Itens
import YourItems from './data.js';
```

No componente (dentro da função que carrega o conteúdo) coloque a função antes do retorna, o `map()` com os itens do Array:

```jsx
// Função que faz o laço em busca dos itens do Array
function List_YourItems() {
    return YourItems.map(YourItems => {
        return (
            <option value={YourItems.id}>{YourItems.option}</option>
        )
    })
}
```

No `retorno` de seu componente onde deve ser listados os itens do Array, vamos interpolar a função:

```jsx
return (
    <>
        <select>
            {List_YourItems()}
        </select>
    </>
);
```

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Executar Array dentro do retorno de um componente

Para mapear o array dentro do retorno de um componente em um select por exemplo, você pode fazer o seguinte:

```jsx
function MeuComponente() {
    const dataTableRecords = [
        { value: 'valor 1', label: 'Opção 1' },
        { value: 'valor 2', label: 'Opção 2' },
        { value: 'valor 3', label: 'Opção 3' }
    ];
    return (
        <select>
            {dataTableRecords.map(item => (
                <option key={item.value} value={item.value}>{item.label}</option>
            ))}
        </select>
    );
}
```

Nesse exemplo, criamos um array `dataTableRecords` com três objetos que representam as opções do select. Em seguida, utilizamos o método `map()` para criar um array de elementos `<option>` com base nos objetos do array `dataTableRecords`. Cada elemento `<option>` tem o atributo value com o valor do objeto e o texto da opção com o atributo label. Note que é importante incluir a propriedade `key` em cada elemento gerado pelo `map()` para ajudar o React a identificar qual item deve ser atualizado em caso de mudanças na lista. Por fim, o array de elementos `<option>` é renderizado dentro do elemento `<select>`.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Mapeamento direto no map()

Colocar o array diretamente no `map()`.

```jsx
function MeuComponente() {
    return (
        <Container>
            {[
                { link: 'https://www.google.com/', name: 'Google', title: 'Ir para o Google' },
                { link: 'https://www.youtube.com/', name: 'YouTube', title: 'Ir para o YouTube' },
                { link: 'https://www.bing.com/', name: 'Bing', title: 'Ir para o Bing' }
            ].map(item => (
                <>
                   <p><a href={item.link} target="_blank" title={item.title}>{item.name}</a></p>
                </>
            ))}
        </Container>
    );
}
```

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

# Pequenos macetes de Array

## Filtrar itens mistos de um array

Imagina que você tem um array e ele contenha informações mistas, números e strings, mas você quer filtrar para obter apenas os números. Veja o código exemplo:

```jsx
const array = ['1', 2, 'three', 7];

console.log(array.filter(Number.isInteger));

// Resultado: Array [ 2, 7 ]
```

> Entre todos os itens dentro do array, será filtrado apenas os números deixando de fora do novo array as strings.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Filtrar os números ímpares de um array

Você tem um array contendo números e você precisa filtrar apenas os ímpares, veja abaixo:

```jsx
const array2 = [1, 2, 3, 4, 5, 6, 7]; 

console.log(array2.filter((number) => number % 2 !== 0));

// Resultado: Array(4) [ 1, 3, 5, 7 ]
```

> O método `filter` retornou um novo array com os elementos que passaram no teste implantados na função fornecida.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Retornar o index da idade maior que 30 anos

No exemplo, tratasse de obter apenas o index maior que 30 anos:

```jsx
const ages = [18, 20, 32, 23, 18, 17, 68];

ages.findIndex((n) => n > 30)

// Resultado: 2
```

> Analisando que no array, o 18 está na posição "0" e o 68 na "6", o `findIndex()` está obtendo o primeiro da lista que é maior que 30, no caso é o valor que está na posição 2 que é o "32". Obs.: O 68 também é maior que 30, mas não é o primeiro no caso.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

# Array map(), filter() e reduce()

Quem é que nunca precisou manipular arrays? Extrair somente os IDs de uma lista de produtos, ou obter dessa lista, somente os produtos de uma determinada categoria, ou então calcular o valor total dos produtos dessa lista. Nesse exemplo veremos três funções que resolvem esses problemas de forma simples.

## Array map()

O map() permite que você crie um novo array utilizando informações de um array já existente. No nosso caso, o nosso array já existente é o "produtos", e o novo array que será criado será o "ids":

```jsx
const produtos = [
  { id: 1, name: 'detergente', valor: 2.00, categoria: 'limpeza' },
  { id: 2, name: 'amaciante', valor: 6.50, categoria: 'limpeza' },
  { id: 3, name: 'pão', valor: 2.00, categoria: 'alimento' },
  { id: 4, name: 'queijo', valor: 7.00, categoria: 'alimento' },
  { id: 5, name: 'leite', valor: 2.20, categoria: 'alimento' }
];

// Passando a função de callback.
const ids = produtos.map(produto => produto.id);
const nomes = produtos.map(produto => produto.name);

// Teste 1.
console.log(ids); // Retornando [1, 2, 3, 4, 5].

// Teste 2.
console.log(nomes); // Retornando ["detergente", "amaciante", "pão", "queijo", "leite"]
```

Para o map() funcionar, foi passado para o map() uma função callback, essa função recebe cada produto retornando o resultado, o valor que vai no novo array.

> Utilizando o map(), você consegue criar um novo array a partir do array original contendo informações ou transformações dessas informações.

Dicamos que você tem um array de números e que você quer duplicá-los criando um novo array com os resultados.

```jsx
const numeros = [1, 2, 3, 4, 5];

// Duplicar.
const duplicados = numeros.map(x => x * 2);

// Teste.
console.log(duplicados); // Retornando [2, 4, 6, 8, 10].
```

> Os valores do primeiro array foram transformados e seu resultado foi para um novo array criado pelo map(). Então, o callback que é passado para o map() recebe cada item e retorna o valor que você quer no array final.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

## Array filter()

O array filter() é um conceito um pouco mais simples de entender. Você cria um novo array a partir de outro array filtrando fora alguns itens. Será imposta uma regra para o map() e sendo respeitada determinado parâmetro.

Dado o array `produtos`, e queremos que vá para o novo array apenas os alimentos. Veja o código abaixo:

```jsx
const produtos = [
  { id: 1, name: 'detergente', valor: 2.00, categoria: 'limpeza' },
  { id: 2, name: 'amaciante', valor: 6.50, categoria: 'limpeza' },
  { id: 3, name: 'pão', valor: 2.00, categoria: 'alimento' },
  { id: 4, name: 'queijo', valor: 7.00, categoria: 'alimento' },
  { id: 5, name: 'leite', valor: 2.20, categoria: 'alimento' }
];

const alimentos = produtos.filter(p => p.categoria === 'alimento');

// Teste 1.
console.log(alimentos); // Retornando [Object, Object, Object].

/* Teste 1 retornando os objetos completos de cada um.
[Object, Object, Object]
  0: Object
    id: 3
    name: "pão"
    valur: 2
    categoria: "alimento"
  1: Object
    id: 4
    name: "queijo"
    valur: 7
    categoria: "alimento"
  2: Object
    id: 3
    name: "leite"
    valur: 2.2
    categoria: "alimento"
*/

// Teste 2.
console.log(alimentos.map(a => a.nome)); // Retornando ["pão", "queijo", "leite"].
```

No "Teste 1" `console.log(alimentos)` Foi declarada a constante `alimentos` com a função que filtra `p` (digamos que `p` é produtos), no caso, algo que tenha um valor que seja convertido em boleano (`true` ou `false`). O retorno do console.log é `[Object, Object, Object]`.

No "Teste 2" `console.log(alimentos.map(a => a.nome))` é combinado um array com o outro array. Digamos que você queira apenas os nomes dos alimentos ao invés do objeto completo. O retorno do console.log é `["pão", "queijo", "leite"]`.

No "Teste 3" `` se você quiser combinar o `filter()` com o `map()` é possível, basta colocar o map() na declaração da constante como no exemplo abaixo:

```jsx
const alimentos = produtos
    .filter(p => p.categoria === 'alimento');
    .map(a => a.nome);
```

> Isso é interessante, você pode combinar uma função com a outra e cada uma faz uma coisa específica. Os métodos podem ser colocados um abaixo do outro.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

## Array Reduce

Com o Reduce você pode gerar um único valor atravéz de uma coleção (uma lista, um array ...).

Digamos que você tenha um array de números, e que você quer somar todos os valores de uma coluna no array obtendo um valor total. Com o Reduce isso é possível.

Veja código abaixo, como o Reduce funciona:

```jsx
// Definida a constante com o seguinte array:
const numeros = [1, 2, 3, 4];

// Vamos somar todos os números dentro do array:
const total = numeros.reduce((acc, numero) => acc + numero, 0);

// Teste.
console.log(total); // Retornando "10".
```

> O reduce, na primeira vez que ele intera com o array, ele pega o "1" e o "2" do array, o primeiro elemento vai ser o acumulado e o segundo vai se chamar "numero", ele retorna o acumulado mais o numero, no retorno do acumulado mais o numero ele soma o primeiro e o segundo elemento que no caso é o "1" e o "2" retornando "3", após isso, ele busca o próximo item do array que é o "3", o resultado da rodada anterior é "6", soma com o próximo trazendo o resultado "10". O zero "0" no final da linha na constante "total", é uma opção de passar um valor inicial para o array para ser o primeiro valor acumulado e o numero vai ser o primeiro item do array.

Agora utilizando o array de "produtos" para somar o valor total deles:

```jsx
const produtos = [
  { id: 1, name: 'detergente', valor: 2.00, categoria: 'limpeza' },
  { id: 2, name: 'amaciante', valor: 6.50, categoria: 'limpeza' },
  { id: 3, name: 'pão', valor: 2.00, categoria: 'alimento' },
  { id: 4, name: 'queijo', valor: 7.00, categoria: 'alimento' },
  { id: 5, name: 'leite', valor: 2.20, categoria: 'alimento' }
];

const total = produtos.reduce((acc, p) => acc + p.valor, 0);

// Teste.
console.log(total); // Retornando "39.2".
```

> Sempre a cada rodada que acontece do reduce, o valor que você está retornando vai se tornar o próximo acumulado e ele pega o próximo do array.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Reinstalar Dependências para Resolver Problemas de Configuração ou Conflitos de CORS

Quando o problema persiste e nenhuma das soluções comuns resolve, uma última alternativa é reinstalar as dependências do projeto. Esse processo remove possíveis conflitos, arquivos corrompidos ou versões inconsistentes.

### Passos para Reinstalação Completa

1. **Excluir as pastas `node_modules` e o arquivo `package-lock.json`**:
   
   - `node_modules` contém todas as dependências e bibliotecas instaladas no projeto.
   - `package-lock.json` define versões exatas das dependências. Ao removê-lo, será recriado com versões atualizadas.

   Execute o comando abaixo no terminal, na raiz do projeto:
   
   ```bash
   rm -rf node_modules package-lock.json
   ```

2. **Reinstalar todas as dependências**:
   
   Após excluir os arquivos, execute o seguinte comando para reinstalar:

   ```bash
   npm install
   ```

3. **Reiniciar o Servidor e o Frontend**:

   Depois da reinstalação, reinicie o servidor e qualquer ambiente de desenvolvimento do frontend para garantir que as alterações entrem em vigor.

### Por Que Isso Funciona?

Esse procedimento pode corrigir problemas de CORS e outros conflitos, eliminando bibliotecas duplicadas, versões incompatíveis ou arquivos temporários que o Node.js pode ter armazenado. É especialmente útil quando configurações e soluções prévias não surtiram efeito.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Implementação de Abas com Props para Componentes

#### **Objetivo**
Implementar um sistema de abas no React usando o componente `Tabs` do `react-bootstrap` e passar um valor único para cada componente de aba usando props.

---

#### **Componente Principal - SystemSettings_Background**

##### Descrição
O componente `SystemSettings_Background` utiliza o componente `Tabs` para organizar cinco componentes (`SystemSettings_BackgroundOfNature`, `SystemSettings_BackgroundGradient`, etc.) em diferentes abas. Cada componente recebe um número único via props, que pode ser usado para lógica específica em cada um.

##### Código
```jsx
import { Tab, Tabs } from 'react-bootstrap';
import { SystemSettings_BackgroundCategory } from './BackgroundCategory/';

export function SystemSettings_Backgrounds() {
    return (
        <Tabs
            defaultActiveKey="NatureBackgrounds"
            id="uncontrolled-tab-example"
            className="mb-3"
        >
            <Tab eventKey="NatureBackgrounds" title="Natureza">
                <SystemSettings_BackgroundCategory number={6} />
            </Tab>
            <Tab eventKey="GradientBackgrounds" title="Gradiente">
                <SystemSettings_BackgroundCategory number={2} />
            </Tab>
            <Tab eventKey="BackgroundMaterialDesign" title="Design">
                <SystemSettings_BackgroundCategory number={3} />
            </Tab>
            <Tab eventKey="WebBackgrounds" title="Da Web">
                <SystemSettings_BackgroundCategory number={4} />
            </Tab>
            <Tab eventKey="OtherBackgrounds" title="Outros">
                <SystemSettings_BackgroundCategory number={5} />
            </Tab>
        </Tabs>
    );
}
```

---

#### **Componentes Filhos - Exemplo com SystemSettings_BackgroundCategory**

##### Descrição
Cada componente de aba, como `SystemSettings_BackgroundCategory`, recebe uma prop `number` que contém um valor único. Essa prop é usada para lógica interna do componente e para renderização condicional.

##### Código
```jsx
export function SystemSettings_BackgroundCategory({ number }) {
    useEffect(() => {
        console.log(`Número recebido: ${number}`);
        // Utilize o número conforme necessário
    }, [number]);

    return (
        <div>
            <h1>Plano de Fundo da Aba {number}</h1>
            <p>Número recebido: {number}</p>
        </div>
    );
}
```

##### Notas
- **Props**: As props permitem passar dados e configurações personalizadas para cada componente.
- **Hooks**: `useEffect` pode ser usado para acionar efeitos colaterais com base no valor recebido.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

