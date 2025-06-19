> ### QuickSnip

# Scripts Prontos: Backend e Frontend

---

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
<!-- /Botões de navegação -->

Exemplos de CRUD (Create, Read, Update, Delete) com integração de frontend e backend, utilizando React.JS no frontend e Prisma no backend.

## Conteúdo
1. **Iniciando projetos**
   - **NodeJS**
     - [Guia de Inicialização de Backend Node.js com TypeScript e Prisma](#-guia-de-inicializa%C3%A7%C3%A3o-de-backend-nodejs-com-typescript-e-prisma "Guia de Inicialização de Backend Node.js com TypeScript e Prisma")
       - [Parte 1: Inicialização do Frontend com React.js (em ./LotManager/frontend/)](#-parte-1-inicializa%C3%A7%C3%A3o-do-frontend-com-reactjs-em-lotmanagerfrontend "Parte 1: Inicialização do Frontend com React.js (em ./LotManager/frontend/)")
       - [Organização inicial de diretórios (frontend)](#-organiza%C3%A7%C3%A3o-inicial-de-diret%C3%B3rios-frontend "Organização inicial de diretórios (frontend)")
       - [Parte 2: Modularização do Backend (Node.js + TS + Prisma)](#-parte-2-modulariza%C3%A7%C3%A3o-do-backend-nodejs--ts--prisma "Parte 2: Modularização do Backend (Node.js + TS + Prisma)")
   - **Com o Vite**
     - [Iniciar projeto React com Vite (JavaScript Puro)](#-iniciar-projeto-react-com-vite-javascript-puro "Iniciar projeto React com Vite (JavaScript Puro)")
       - [Instalar e Importar Bootstrap em Projeto Vite + React](# "Instalar e Importar Bootstrap em Projeto Vite + React")
2. **Exemplos CRUD com React e Prisma**
   - **Formulário de Cadastro (Create)**
     - Formulário simples de cadastro com validação de campos
     - Envio de dados para o backend via API (fetch ou Axios)
     - Armazenamento de dados no banco usando Prisma
     - [`Gravando` dados do formulário na tabela usando o `ORM Prisma`](#gravando-dados-do-formul%C3%A1rio-na-tabela-usando-o-orm-prisma "Gravando dados do formulário na tabela usando o ORM Prisma")
   - **Validação de Formulários**
     - [Validação Simples de Campos com Mensagens de Erro](#exemplo-de-formul%C3%A1rio-com-valida%C3%A7%C3%A3o-e-intercepta%C3%A7%C3%A3o-de-submit "Validação Simples de Campos com Mensagens de Erro")
   - **Listagem de Itens com DataTable (Read)**
     - Integração com biblioteca DataTable (React Table, Material UI, etc.)
     - Consulta de dados no backend (Prisma findMany)
     - [Implementação de Indicador de Carregamento Centralizado para DataTable com React e CSS](#implementa%C3%A7%C3%A3o-de-indicador-de-carregamento-centralizado-para-datatable-com-react-e-css "Implementação de Indicador de Carregamento Centralizado para DataTable com React e CSS")
     - Paginação e filtros de dados
     - [Formatação de Dados da API em um Array no Formato Específico (`JSON`)](#formata%C3%A7%C3%A3o-de-dados-da-api-em-um-array-no-formato-espec%C3%ADfico-json "Formatação de Dados da API em um Array no Formato Específico (JSON)")
   - **Consulta de Registro Único (Single)**
     - [Rota Genérica para Consulta de Registro Único por ID](#rota-gen%C3%A9rica-para-consulta-de-registro-%C3%BAnico-por-id "Rota Genérica para Consulta de Registro Único por ID")
     - [Exemplo de Componente React para Exibir Detalhes de um Registro](#exemplo-gen%C3%A9rico-de-requisi%C3%A7%C3%A3o-no-frontend "Exemplo de Componente React para Exibir Detalhes de um Registro")
     - [Rota para Obter o ID do Último Registro Criado](#rota-para-obter-o-id-do-%C3%BAltimo-registro-criado "Rota para Obter o ID do Último Registro Criado")
   - **Edição de Registro (Update)**
     - [Edição de registros com formulário polimorfo](#edi%C3%A7%C3%A3o-de-registros-com-formul%C3%A1rio-polimorfo "Edição de registros com formulário polimorfo")
     - [Edição de itens com dados predefinidos no formulário](#exemplo-gen%C3%A9rico-sincronizando-valores-do-formul%C3%A1rio-com-dados-da-api "Edição de itens com dados predefinidos no formulário")
     - [`Editar` dados de um registro `no formulário`](#editar-dados-de-um-registro-no-formul%C3%A1rio "Editar dados de um registro no formulário")
     - [Modelo Genérico para Formulários com Modo de Edição e Registro](#modelo-gen%C3%A9rico-para-formul%C3%A1rios-com-modo-de-edi%C3%A7%C3%A3o-e-registro "Modelo Genérico para Formulários com Modo de Edição e Registro")
     - Atualização dos registros no backend via API
     - Validação de dados antes da atualização
     - [Utilizando o Operador Spread para Inserção Condicional de Propriedades](#utilizando-o-operador-spread-para-inser%C3%A7%C3%A3o-condicional-de-propriedades "Utilizando o Operador Spread para Inserção Condicional de Propriedades")
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
     - Organização de `rotas` e `controllers` no backend
       - [`Refatoração` de rotas e uso de controllers](#refatora%C3%A7%C3%A3o-de-rotas-e-uso-de-controllers "Refatoração de rotas e uso de controllers")
         - [`Exemplo Genérico` de Organização de `Rotas` e `Controllers`](#exemplo-gen%C3%A9rico-de-organiza%C3%A7%C3%A3o-de-rotas-e-controllers "Exemplo Genérico de Organização de Rotas e Controllers")
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
3. **Paginação de Listas com React e Prisma**
   - [Componente de Paginação Genérico para Listas](#componente-de-pagina%C3%A7%C3%A3o-gen%C3%A9rico-para-listas "Componente de Paginação Genérico para Listas")
     - [Arquivo de Rota: `routes.ts`](#arquivo-routests "Arquivo de Rota: `routes.ts`")
     - [Componente de Paginação: `index.jsx`](#arquivo-indexjsx "Componente de Paginação: `index.jsx`")
   - [Outro exemplo genérico com botões ilimitados com Reticências (...)](#outro-exemplo-gen%C3%A9rico-com-bot%C3%B5es-ilimitados-com-retic%C3%AAncias- "Outro exemplo genérico com botões ilimitados com Reticências (...)")
     - [Passo 1: Criar a Função de Geração de Páginas](#passo-1-criar-a-fun%C3%A7%C3%A3o-de-gera%C3%A7%C3%A3o-de-p%C3%A1ginas "Passo 1: Criar a Função de Geração de Páginas")
     - [Passo 2: Implementar a Exibição de Botões de Paginação](#passo-2-implementar-a-exibi%C3%A7%C3%A3o-de-bot%C3%B5es-de-pagina%C3%A7%C3%A3o "Passo 2: Implementar a Exibição de Botões de Paginação")
4. **Notificações no Frontend com React**
   - [Notificação de `Conexão` de `Internet`](#notifica%C3%A7%C3%A3o-de-conex%C3%A3o-de-internet "Notificação de Conexão de Internet")
   - [Modificação para substituir o `alert()` por uma mensagem estilizada](#modifica%C3%A7%C3%A3o-para-substituir-o-alert-por-uma-mensagem-estilizada "Modificação para substituir o alert() por uma mensagem estilizada")
   - [Exemplo de Reutilização de Notificações com `Diferentes Tipos`](#exemplo-de-reutiliza%C3%A7%C3%A3o-de-notifica%C3%A7%C3%B5es-com-diferentes-tipos "Exemplo de Reutilização de Notificações com Diferentes Tipos")
   - [Usar as notificações com `CSS Modules`](#usar-as-notifica%C3%A7%C3%B5es-com-css-modules "Usar as notificações com 'CSS Modules'")
5. **Trabalhando Fenestra, API de janelas para react/redux**
   - **Corrigindo problemas**
     - Formulário simples de cadastro com validação de campos
   - **Manipulação de Estilos e Classes em Componentes Modais**
     - [Adicionando Classe na Div Mãe](#adicionando-classe-na-div-m%C3%A3e "Adicionando Classe na Div Mãe")
   - [Usando Imagens PNG como Ícones em Componentes React](#usando-imagens-png-como-%C3%ADcones-em-componentes-react "Usando Imagens PNG como Ícones em Componentes React")
     - [Uso de URLs Externas para Imagens em Componentes React](#uso-de-urls-externas-para-imagens-em-componentes-react "Uso de URLs Externas para Imagens em Componentes React")
6. **Testes e Simulações de Interface**
   - **Preenchimento Automático de Formulários com JavaScript Nativo**
     - [Preencher diferentes tipos de campos usando o console do navegador](#preencher-diferentes-tipos-de-campos-usando-o-console-do-navegador "Preencher diferentes tipos de campos usando o console do navegador")
7. **Configuração e Segurança em Projetos React**
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
8. **Manipulação de Arrays em JavaScript**
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
9. **Resolução de Problemas e Manutenção do Projeto**
   - [Reinstalar Dependências para Resolver Problemas de Configuração ou Conflitos de CORS](#reinstalar-depend%C3%AAncias-para-resolver-problemas-de-configura%C3%A7%C3%A3o-ou-conflitos-de-cors "Reinstalar Dependências para Resolver Problemas de Configuração ou Conflitos de CORS")
10. **Estrutura e Implementação de Componentes**
   - **Ícones e Componentes Visuais**
     - [Implementação de Ícones Font-Awesome em Componentes React](#como-implementar-%C3%ADcones-font-awesome-em-componentes-react "Implementação de Ícones Font-Awesome em Componentes React")
   - **Abas com Props para Componentes**
     - [Componente de Ping React com Histórico de Respostas](#componente-de-ping-react-com-hist%C3%B3rico-de-respostas "Componente de Ping React com Histórico de Respostas")
     - [Implementação de Componente com Abas no React-Bootstrap e Props para Identificação Única](#implementa%C3%A7%C3%A3o-de-abas-com-props-para-componentes "Implementação de Componente com Abas no React-Bootstrap e Props para Identificação Única")
     - [Passagem de Props e Uso de Hooks em Componentes Filhos de Abas](#componentes-filhos---exemplo-com-systemsettings_backgroundcategory "Passagem de Props e Uso de Hooks em Componentes Filhos de Abas")
   - [Renderização Condicional de Elementos com Base na Largura da Tela em React.js](#renderiza%C3%A7%C3%A3o-condicional-de-elementos-com-base-na-largura-da-tela-em-reactjs "Renderização Condicional de Elementos com Base na Largura da Tela em React.js")
   - [Navegação Dinâmica com React Router para Redirecionamento](#navega%C3%A7%C3%A3o-din%C3%A2mica-com-react-router-redirecionando-para-componentes-em-uma-spa "Navegação Dinâmica com React Router para Redirecionamento")
11. **Envio de Emails e Comunicação Backend**
   - **Envio de Emails com Nodemailer**
     - [Estrutura de Diretórios para Projeto de Envio de Emails](#estrutura-de-diret%C3%B3rios "Estrutura de Diretórios para Projeto de Envio de Emails")
     - [Configuração do Servidor com Express e Nodemailer](#configura%C3%A7%C3%A3o-do-backend "Configuração do Servidor com Express e Nodemailer")
     - [Criação da Rota para Envio de Email com Nodemailer](#3-criar-rota-para-envio-de-email "Criação da Rota para Envio de Email com Nodemailer")
     - [Uso de Arquivo `.env` para Configurações Sensíveis](#4-configura%C3%A7%C3%A3o-do-env "Uso de Arquivo .env para Configurações Sensíveis")
     - [Integração com o Frontend (React)](#configura%C3%A7%C3%A3o-do-frontend "Integração com o Frontend (React)")
     - [Instruções para Executar o Projeto](#executar-o-projeto "Instruções para Executar o Projeto")
12. **Manipulação de Objetos no DOM com JavaScript**
   - [Remover um Elemento Específico pelo ID](#remover-um-elemento-espec%C3%ADfico-pelo-id "Remover um Elemento Específico pelo ID")
   - [Adicionar um Elemento Antes de Outro no DOM](#adicionar-um-elemento-antes-de-outro-no-dom "Adicionar um Elemento Antes de Outro no DOM")
   - [Adicionar um Elemento Depois de Outro no DOM](#adicionar-um-elemento-depois-de-outro-no-dom "Adicionar um Elemento Depois de Outro no DOM")
     > **Substituição de conteúdo**
     > - [Substituir um Elemento por Outro no DOM](#substituir-um-elemento-por-outro-no-dom "Substituir um Elemento por Outro no DOM")
     > - [`Substituir` um `Elemento` do DOM por um elemento com `Componente React`](#substituir-um-elemento-do-dom-por-um-elemento-com-componente-react "Substituir um Elemento do DOM por um elemento com Componente React")
     > - [Exemplo Genérico para Substituir Elemento do DOM por Componente React](#exemplo-gen%C3%A9rico-para-substituir-elemento-do-dom-por-componente-react "Exemplo Genérico para Substituir Elemento do DOM por Componente React")
   - [Adicionar um Novo Elemento como Filho de Outro](#adicionar-um-novo-elemento-como-filho-de-outro "Adicionar um Novo Elemento como Filho de Outro")
   - [Adicionar uma Linha Depois de Outra Linha em uma Tabela](#exemplo-de-uso-para-estruturas-de-tabela "Adicionar uma Linha Depois de Outra Linha em uma Tabela")
   - [Manipulação Dinâmica do Título da Página com JavaScript](#manipula%C3%A7%C3%A3o-din%C3%A2mica-do-t%C3%ADtulo-da-p%C3%A1gina-com-javascript "Manipulação Dinâmica do Título da Página com JavaScript")
13. **Funções Utilitárias e Automatizações**
   - [Função simples](#fun%C3%A7%C3%A3o-simples "Função simples")
     - [Preenchimento Automático de Formulários com React: Manipulação de Campos de Texto, Select, Radiobutton e Checkbox](#preenchimento-autom%C3%A1tico-de-formul%C3%A1rios-com-react-manipula%C3%A7%C3%A3o-de-campos-de-texto-select-radiobutton-e-checkbox "Preenchimento Automático de Formulários com React: Manipulação de Campos de Texto, Select, Radiobutton e Checkbox")
     - [Modularização de Funções de Preenchimento Automático de Formulários em React com Importação Externa](#modulariza%C3%A7%C3%A3o-de-fun%C3%A7%C3%B5es-de-preenchimento-autom%C3%A1tico-de-formul%C3%A1rios-em-react-com-importa%C3%A7%C3%A3o-externa "Modularização de Funções de Preenchimento Automático de Formulários em React com Importação Externa")
   - [Exemplo de Adição de Evento de Clique em JavaScript](#exemplo-de-adi%C3%A7%C3%A3o-de-evento-de-clique-em-javascript "Exemplo de Adição de Evento de Clique em JavaScript")
   - [Passar uma propriedade de um elemento para uma arrow function](#passar-uma-propriedade-de-um-elemento-para-uma-arrow-function "Passar uma propriedade de um elemento para uma arrow function")
   - [PopUp com uma determinada URL passada via parâmetro](#popup-com-uma-determinada-url-passada-via-par%C3%A2metro "Popup com uma determinada URL passada via parâmetro")
   - [PopUp passando além de uma URL, dimensões e centralizada](#popup-passando-al%C3%A9m-de-uma-url-dimens%C3%B5es-e-centralizada "PopUp passando além de uma URL, dimensões e centralizada")
   - [Contar número de caracteres de uma string](#contar-n%C3%BAmero-de-caracteres-de-uma-string "Contar número de caracteres de uma string")
   - [Capitalizar nomes (ótimo para cadastro de pessoas)](#capitalizar-nomes-%C3%B3timo-para-cadastro-de-pessoas "Capitalizar nomes (ótimo para cadastro de pessoas)")
   - [Capitalizar a primeira palavra de um parágrafo com exceções em ReactJS](#capitalizar-a-primeira-palavra-de-um-par%C3%A1grafo-com-exce%C3%A7%C3%B5es-em-reactjs "Capitalizar a primeira palavra de um parágrafo com exceções em ReactJS")
   - [Transformando meses de 01 a 12 em Janeiro a Dezembro](#transformando-meses-de-01-a-12-em-janeiro-a-dezembro "Transformando meses de 01 a 12 em Janeiro a Dezembro")
   - [Como `Rolar` a Barra de Rotação `para o Topo` de uma Página ao Carregá-la com JavaScript](#como-rolar-a-barra-de-rota%C3%A7%C3%A3o-para-o-topo-de-uma-p%C3%A1gina-ao-carreg%C3%A1-la-com-javascript "Como Rolar a Barra de Rotação para o Topo de uma Página ao Carregá-la com JavaScript")
   - [Removendo Tags HTML em ReactJS: Uma Abordagem Simples e Segura](#removendo-tags-html-em-reactjs-uma-abordagem-simples-e-segura "Removendo Tags HTML em ReactJS: Uma Abordagem Simples e Segura")
   - [Removendo Tags HTML com ReactJS: Uma Abordagem Simples e Elegante](#removendo-tags-html-com-reactjs-uma-abordagem-simples-e-elegante "Removendo Tags HTML com ReactJS: Uma Abordagem Simples e Elegante")
   - [Função de Formatação de Data e Hora com Ajuste de Horas](#fun%C3%A7%C3%A3o-de-formata%C3%A7%C3%A3o-de-data-e-hora-com-ajuste-de-horas "Função de Formatação de Data e Hora com Ajuste de Horas")
14. **Incorporando Serviços Externos em Aplicações React**
   - **Google Maps**
     - [Componente React para Exibição de Localização com Google Maps](#componente-react-para-exibi%C3%A7%C3%A3o-de-localiza%C3%A7%C3%A3o-com-google-maps "Componente React para Exibição de Localização com Google Maps")
15. **CSS e Layouts em React**
   - [Componentes Fixos e Posicionados no Layout com CSS](#componentes-fixos-e-posicionados-no-layout-com-css "Componentes Fixos e Posicionados no Layout com CSS")
     - [Implementação de Quadros no Canto Inferior Direito](#estrutura-do-componente-react "Implementação de Quadros no Canto Inferior Direito")
     - [Estilização de Componentes com Altura Flexível](#estilos-css-floatingboxescss "Estilização de Componentes com Altura Flexível")
16. **Meu Fluxo de Trabalho e Boas Práticas**
   - **Organização Pessoal e Produtividade**
     - Como organizo meus ambientes de trabalho e softwares abertos
     - [Organização de Terminais: Fluxo de Trabalho Produtivo](#organiza%C3%A7%C3%A3o-de-terminais-fluxo-de-trabalho-produtivo "Organização de Terminais: Fluxo de Trabalho Produtivo")
   - **Estilo de Programação**
     - Regras pessoais para manter o código limpo
   - **Processo de Desenvolvimento**
     - Exemplo de Planejamento de Funcionalidades
   - **Testes e Melhoria Contínua**
     - Ferramentas para Automação de Testes
   - **Boas Práticas**
     - Boas Práticas de Colaboração em Projetos Git
17. **Recebendo e Usando Propriedades (`props`) em Componentes React**
   - [Modelo Genérico para Receber e Usar Props em Componentes React](#recebendo-e-usando-propriedades-props-em-componentes-react "Modelo Genérico para Receber e Usar Props em Componentes React")
     - [Exemplo para Componentes Funcionais](#componente-funcional "Exemplo para Componentes Funcionais")
     - [Exemplo para Componentes de Classe](#componente-de-classe "Exemplo para Componentes de Classe")
     - [Boas Práticas com PropTypes e TypeScript](#boas-pr%C3%A1ticas-tipagem-e-valida%C3%A7%C3%A3o "Boas Práticas com PropTypes e TypeScript")
18. **Modelos e Automatizações com Prisma**
   - [Uso de ENUMs no Prisma ORM](#uso-de-enums-no-prisma-orm "Uso de ENUMs no Prisma ORM")
   - [Integração de ENUM do Prisma com TypeScript](#integra%C3%A7%C3%A3o-de-enum-do-prisma-com-typescript "Integração de ENUM do Prisma com TypeScript")
   - [Geração automática de enums Prisma para uso no frontend](#gera%C3%A7%C3%A3o-autom%C3%A1tica-de-enums-prisma-para-uso-no-frontend "Geração automática de enums Prisma para uso no frontend")
   - [Versão Avançada do Script de Geração de Enums](#vers%C3%A3o-avan%C3%A7ada-do-script-de-gera%C3%A7%C3%A3o-de-enums "Versão Avançada do Script de Geração de Enums")
   - [Como consumir enums do Prisma no frontend](#como-consumir-enums-do-prisma-no-frontend "Como consumir enums do Prisma no frontend")

---

Este item "Scripts Prontos: Backend e Frontend" contém scripts prontos para diversos cenários, como formulários com integração completa entre frontend e backend, listagem de itens, edição, e exclusão com DataTables e outras funcionalidades. A ideia é que essa seção funcione como um guia rápido para montar um CRUD completo ou mesmo pacotes prontos que você pode adaptar e reutilizar facilmente.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

Perfeito, Marcos! Aqui está o conteúdo formatado para seu **Codex**, com título, instruções passo a passo e blocos de código organizados para reutilização futura:

---

## 🚀 Guia de Inicialização de Backend Node.js com TypeScript e Prisma

Este guia ensina como estruturar um projeto backend moderno utilizando **Node.js**, **TypeScript**, **Express** e **Prisma ORM**, pronto para ser integrado a um frontend em React ou outros serviços.

### 🧱 Estrutura Inicial de Diretórios

```
./LotManager/
├── backend/
│   └── src/
└── frontend/
```

### 1. Inicializar o Projeto Node.js

No terminal, acesse o diretório do backend e inicialize com `npm`:

```bash
cd LotManager/backend
npm init -y
```

### 2. Instalar e Configurar TypeScript

```bash
npm install typescript ts-node-dev @types/node --save-dev
npx tsc --init
```

Edite o `tsconfig.json` com:

```json
{
  "compilerOptions": {
    "target": "es2019",
    "module": "commonjs",
    "rootDir": "src",
    "outDir": "dist",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true
  }
}
```

Crie o diretório de origem:

```bash
mkdir src
touch src/index.ts
```

### 3. Instalar e Configurar o Express

```bash
npm install express
npm install @types/express --save-dev
```

No `package.json`, adicione o script de desenvolvimento:

```json
"scripts": {
  "dev": "ts-node-dev --respawn --transpile-only src/index.ts"
}
```

Exemplo básico de `src/index.ts`:

```ts
import express from 'express';

const app = express();
const PORT = process.env.PORT || 3000;

app.use(express.json());

app.get('/', (req, res) => {
  res.send('Backend LotManager está rodando 🚀');
});

app.listen(PORT, () => {
  console.log(`Servidor rodando na porta ${PORT}`);
});
```

### 4. Instalar e Configurar o Prisma

```bash
npm install prisma --save-dev
npm install @prisma/client
npx prisma init
```

No `.env`, configure a URL do banco (exemplo com SQLite):

```env
DATABASE_URL="file:./dev.db"
```

Exemplo de modelo no `prisma/schema.prisma`:

```prisma
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "sqlite"
  url      = env("DATABASE_URL")
}

model Lot {
  id        Int      @id @default(autoincrement())
  name      String
  createdAt DateTime @default(now())
}
```

Rodar migração e gerar client:

```bash
npx prisma generate
npx prisma migrate dev --name init
```

### 5. Usar o Prisma Client

No `src/index.ts`:

```ts
import { PrismaClient } from '@prisma/client';

const prisma = new PrismaClient();

app.get('/lotes', async (req, res) => {
  const lotes = await prisma.lot.findMany();
  res.json(lotes);
});
```

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## 🎯 Parte 1: Inicialização do Frontend com React.js (em `./LotManager/frontend/`)

### 1. Criar o projeto com Vite + TypeScript

```bash
cd LotManager/frontend
npm create vite@latest . -- --template react-ts
```

Ou, se quiser nomear fora da pasta atual:

```bash
npm create vite@latest frontend -- --template react-ts
```

Siga as instruções e depois instale as dependências:

```bash
cd frontend
npm install
```

### 2. Rodar o projeto

```bash
npm run dev
```

Acesse `http://localhost:5173` para ver a aplicação rodando.

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## 🎨 Organização inicial de diretórios (frontend)

Estrutura sugerida:

```
frontend/
├── public/
├── src/
│   ├── assets/
│   ├── components/
│   ├── pages/
│   ├── services/     ← para consumo de API com axios
│   ├── hooks/
│   ├── routes/
│   ├── App.tsx
│   └── main.tsx
├── index.html
└── vite.config.ts
```

### 3. Instalar Axios para integração com backend

```bash
npm install axios
```

Criar um serviço em `src/services/api.ts`:

```ts
import axios from 'axios';

export const api = axios.create({
  baseURL: 'http://localhost:3000', // backend
});
```

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## 🔧 Parte 2: Modularização do Backend (Node.js + TS + Prisma)

### Organização recomendada

```
backend/
├── src/
│   ├── controllers/
│   │   └── lot.controller.ts
│   ├── routes/
│   │   └── lot.routes.ts
│   ├── middlewares/
│   │   └── error.middleware.ts
│   ├── prisma/
│   │   └── client.ts
│   ├── index.ts
│   └── app.ts
├── prisma/
│   └── schema.prisma
├── .env
├── tsconfig.json
└── package.json
```

---

### `src/prisma/client.ts`

```ts
import { PrismaClient } from '@prisma/client';
export const prisma = new PrismaClient();
```

---

### `src/controllers/lot.controller.ts`

```ts
import { Request, Response } from 'express';
import { prisma } from '../prisma/client';

export const getAllLots = async (req: Request, res: Response) => {
  const lots = await prisma.lot.findMany();
  res.json(lots);
};
```

---

### `src/routes/lot.routes.ts`

```ts
import { Router } from 'express';
import { getAllLots } from '../controllers/lot.controller';

const router = Router();

router.get('/', getAllLots);

export default router;
```

---

### `src/middlewares/error.middleware.ts`

```ts
import { Request, Response, NextFunction } from 'express';

export function errorHandler(err: any, req: Request, res: Response, next: NextFunction) {
  console.error(err);
  res.status(500).json({ error: 'Erro interno do servidor' });
}
```

---

### `src/app.ts`

```ts
import express from 'express';
import lotRoutes from './routes/lot.routes';
import { errorHandler } from './middlewares/error.middleware';

const app = express();

app.use(express.json());

app.use('/lotes', lotRoutes);

app.use(errorHandler);

export default app;
```

---

### `src/index.ts`

```ts
import app from './app';

const PORT = process.env.PORT || 3000;

app.listen(PORT, () => {
  console.log(`Servidor rodando na porta ${PORT}`);
});
```

Pronto! Agora você tem o backend modularizado e o frontend inicializado com Vite + React + TypeScript, prontos para evoluir com sua aplicação LotManager.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## 🧪 Iniciar projeto React com Vite (JavaScript Puro)

Aqui está um modelo de instrução, explicando como iniciar um projeto frontend com **Vite + React** utilizando **JavaScript puro (sem TypeScript)**. Você pode adaptá-lo conforme seus padrões futuros.

### 🎯 Objetivo

Criar um novo projeto React utilizando o **Vite** como bundler e **JavaScript puro**, ideal para aplicações SPA modernas e com tempo de build rápido.

### 🧱 Estrutura de exemplo esperada

```
/LotManager/
└── frontend/
    ├── index.html
    ├── package.json
    ├── vite.config.js
    └── src/
        ├── main.jsx
        └── App.jsx
```

### 🚀 Passos para inicialização

#### 1. Acesse o diretório onde ficará o projeto

```bash
cd ~/Projetos/LotManager/frontend
```

#### 2. Crie o projeto com Vite

```bash
npm create vite@latest .
```

> Durante o prompt:

* Nome do projeto: `.` (ou o nome atual do diretório)
* Framework: `React`
* Variant: `JavaScript`

#### 3. Instale as dependências

```bash
npm install
```

#### 4. Inicie o servidor de desenvolvimento

```bash
npm run dev
```

### 📂 Estrutura inicial gerada pelo Vite

* `index.html`: ponto de entrada HTML da aplicação.
* `main.jsx`: arquivo onde o React é iniciado.
* `App.jsx`: componente principal do projeto.
* `vite.config.js`: configurações do Vite.

### 🔄 Scripts disponíveis

```json
// package.json
"scripts": {
  "dev": "vite",
  "build": "vite build",
  "preview": "vite preview"
}
```

### ✅ Observações

* Esse setup é indicado para projetos onde não se deseja usar TypeScript inicialmente.
* Pode-se futuramente migrar para TypeScript com `npm install --save-dev typescript @types/react @types/react-dom`.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

Perfeito, Marcos. Aqui está um **modelo genérico e complementar** para adicionar **Bootstrap (via React-Bootstrap)** em um projeto **Vite já criado com React + JavaScript**.

---

## Instalar e Importar Bootstrap em Projeto Vite + React

> 📌 **Cenário**: Projeto Vite com React + JavaScript **já criado**
> 🎯 Objetivo: Instalar o Bootstrap (via React-Bootstrap) e importar corretamente o CSS

### 1. Instalar Bootstrap e React-Bootstrap

Execute no terminal na raiz do projeto:

```bash
npm install bootstrap react-bootstrap
```

> Se for usar componentes que exigem posicionamento dinâmico (como `Dropdown`, `Popover`, `Tooltip`), também instale o Popper.js:

```bash
npm install @popperjs/core
```

### 2. Importar o CSS do Bootstrap

No arquivo `src/main.jsx`, adicione a seguinte linha **antes de renderizar o React**:

```jsx
import 'bootstrap/dist/css/bootstrap.min.css';
```

### 3. Usar Componentes Bootstrap no JSX

Agora você pode importar componentes direto do `react-bootstrap` e usá-los normalmente.

**Exemplo básico (`src/App.jsx`):**

```jsx
import Button from 'react-bootstrap/Button';

function App() {
  return (
    <div className="container py-4">
      <h1>Integração React-Bootstrap com Vite</h1>
      <Button variant="primary">Clique aqui</Button>
    </div>
  );
}

export default App;
```

### 4. Pronto para uso

* Nenhuma configuração extra no `vite.config.js` é necessária.
* O Vite lida com os módulos e CSS do Bootstrap automaticamente.
* O React-Bootstrap cuida da lógica e estilos dos componentes para você.

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

## Exemplo de Formulário com Validação e Interceptação de Submit

Abaixo está o exemplo atualizado, incluindo validação dos campos para garantir que o usuário não envie o formulário com campos vazios.

---

### Passo 1: Configure os estados e os valores iniciais

Declare os estados que armazenarão os valores de cada campo e um estado para os erros:

```jsx
import React, { useState } from "react";

export function ExampleFormWithValidation() {
    const [campo1, setCampo1] = useState("");
    const [campo2, setCampo2] = useState("");
    const [campo3, setCampo3] = useState("");
    const [errors, setErrors] = useState({});

// ... outras linhas ...
```

---

### Passo 2: Crie uma função de validação

Essa função verifica se os campos estão preenchidos e retorna um objeto com os erros encontrados:

```jsx
    const validateFields = () => {
        const newErrors = {};
        if (!campo1.trim()) newErrors.campo1 = "Campo1 é obrigatório.";
        if (!campo2.trim()) newErrors.campo2 = "Campo2 é obrigatório.";
        if (!campo3.trim()) newErrors.campo3 = "Campo3 é obrigatório.";
        return newErrors;
    };
```

---

### Passo 3: Intercepte o envio do formulário e aplique validação

Adicione uma lógica para validar os campos antes de enviar os dados:

```jsx
    // Interceptar o envio padrão.
    const handleSubmit = (e) => {
        e.preventDefault();

        const validationErrors = validateFields();
        if (Object.keys(validationErrors).length > 0) {
            setErrors(validationErrors); // Atualiza os erros no estado
            return;
        }

        // Limpar os erros e exibe os valores no console.
        setErrors({});
        console.log("Valores do formulário:", { campo1, campo2, campo3 });
    };
```

---

### Passo 4: Renderize o formulário com exibição de mensagens de erro

Exiba mensagens de erro abaixo dos campos, caso eles estejam inválidos:

```jsx
    return (
        <form onSubmit={handleSubmit}>
            <div>
                <label>
                    Campo1:
                    <input
                        type="text"
                        value={campo1}
                        onChange={(e) => setCampo1(e.target.value)}
                    />
                </label>
                {errors.campo1 && <p style={{ color: "red" }}>{errors.campo1}</p>}
            </div>
            <div>
                <label>
                    Campo2:
                    <input
                        type="text"
                        value={campo2}
                        onChange={(e) => setCampo2(e.target.value)}
                    />
                </label>
                {errors.campo2 && <p style={{ color: "red" }}>{errors.campo2}</p>}
            </div>
            <div>
                <label>
                    Campo3:
                    <input
                        type="text"
                        value={campo3}
                        onChange={(e) => setCampo3(e.target.value)}
                    />
                </label>
                {errors.campo3 && <p style={{ color: "red" }}>{errors.campo3}</p>}
            </div>
            <button type="submit">Enviar</button>
        </form>
    );
}
```

---

### Passo 5: Teste e ajuste

1. **Preencha os campos e clique em enviar**:
   - Se os campos estiverem vazios, mensagens de erro em vermelho serão exibidas abaixo de cada campo.
   - Caso estejam preenchidos, os valores serão exibidos no console.

2. **Exemplo de saída no console**:
```json
{
    "campo1": "Valor preenchido no Campo1",
    "campo2": "Valor preenchido no Campo2",
    "campo3": "Valor preenchido no Campo3"
}
```

3. **Mensagem de erro exibida** (se o Campo1 estiver vazio):
```
Campo1 é obrigatório.
```

---

### Resultado Final:

Um formulário funcional e validado, que impede o envio de campos vazios e exibe mensagens claras de erro para o usuário.

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

### Saída de dados no formato JSON

Os dados abaixo, são expostos no formato `json`:

```json
{
  "data": [
    {
      "id": 5,
      "image": "https://www.site.com/images/image5.jpg",
      "title": "Título 5",
      "category": "category-5",
      "date": "2024-12-10T00:00:00.000Z"
    },
    {
      "id": 4,
      "image": "https://www.site.com/images/image4.jpg",
      "title": "Título 4",
      "category": "category-4",
      "date": "2024-12-11T00:00:00.000Z"
    },
    {
      "id": 3,
      "image": "https://www.site.com/images/image3.jpg",
      "title": "Título 3",
      "category": "category-3",
      "date": "2024-12-12T00:00:00.000Z"
    },
    {
      "id": 2,
      "image": "https://www.site.com/images/image2.jpg",
      "title": "Título 2",
      "category": "category-2",
      "date": "2024-12-13T00:00:00.000Z"
    },
    {
      "id": 1,
      "image": "https://www.site.com/images/image1.jpg",
      "title": "Título 1",
      "category": "category-1",
      "date": "2024-12-14T00:00:00.000Z"
    }
  ]
}
```

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

## Rota para Obter o ID do Último Registro Criado

Para retornar apenas o ID do último registro, você pode usar o Prisma para buscar um único registro ordenado de forma decrescente pela data de criação (`createdAt`). Aqui está a rota ajustada:

```ts
// Rota para buscar o ID do último registro
routes.get('/getLastEntityId', async (req, res) => {
    try {
        // Buscar o último registro na tabela especificada
        const lastEntity = await prisma.entity.findFirst({
            orderBy: { createdAt: 'desc' }, // Ordena por data de criação em ordem decrescente
            select: { id: true }, // Seleciona apenas o campo "id"
        });

        if (!lastEntity) {
            return res.status(404).json({ error: 'Nenhum registro encontrado' });
        }

        return res.status(200).json(lastEntity);
    } catch (error) {
        console.error('Erro ao buscar o último ID:', error);
        return res.status(500).json({ error: 'Erro ao buscar o último ID' });
    }
});
```

### Explicação:
1. **`findFirst`**: Busca o primeiro registro que corresponde à consulta, ordenado por `createdAt` em ordem decrescente. Isso garante que você obtenha o registro mais recente.
2. **`select: { id: true }`**: Especifica que apenas o campo `id` será retornado, reduzindo a quantidade de dados transferidos.
3. **Verificação de existência**: Caso não existam registros, retorna um erro 404 indicando que nenhum registro foi encontrado.

Essa rota é eficiente e atende ao seu caso de uso específico.

---

Segue um exemplo de como você pode fazer a requisição à rota `/getLastEntityId` utilizando o `fetch` no frontend ou em um script Node.js:

### Exemplo com `fetch` no Frontend:
```ts
async function fetchLastEntityId() {
    try {
        const response = await fetch('/getLastEntityId'); // Ajuste a URL conforme necessário
        if (!response.ok) {
            throw new Error(`Erro na requisição: ${response.statusText}`);
        }
        const data = await response.json();
        console.log('Último ID:', data.id);
    } catch (error) {
        console.error('Erro ao buscar o último ID:', error);
    }
}

fetchLastEntityId();
```

### Exemplo com Axios (Frontend ou Node.js):
```ts
import axios from 'axios';

async function fetchLastEntityId() {
    try {
        const response = await axios.get('/getLastEntityId'); // Ajuste a URL conforme necessário
        console.log('Último ID:', response.data.id);
    } catch (error) {
        console.error('Erro ao buscar o último ID:', error.response?.data || error.message);
    }
}

fetchLastEntityId();
```

### Explicação:
1. **`fetch`**: É uma API nativa para requisições HTTP no navegador, simples e eficiente.
2. **`axios`**: Uma biblioteca mais avançada que facilita o tratamento de respostas HTTP e erros.
3. **Ajuste de URL**: Certifique-se de que a URL da API está correta. Se você está em um ambiente local, pode ser algo como `http://localhost:3000/getLastEntityId`.

Adapte o código de acordo com seu ambiente (ex.: inclusão de headers, autenticação, etc.).

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

## Exemplo Genérico: Sincronizando Valores do Formulário com Dados da API

Este exemplo demonstra como criar um formulário React onde os valores iniciais vêm de uma API e podem ser atualizados dinamicamente pelos usuários. Ele resolve problemas comuns ao lidar com `defaultValue` substituindo-o por `value` vinculado ao estado.

### Código

```jsx
import React, { useState, useEffect } from 'react';
import { Container, Button, Col, Form, Row } from 'react-bootstrap';

export function GenericFormExample() {
    // Estados para armazenar os valores do formulário
    const [field1, setField1] = useState(""); // Campo 1
    const [field2, setField2] = useState(""); // Campo 2
    const [errors, setErrors] = useState({}); // Armazena os erros de validação

    // Obtém o ID da empresa do localStorage (ou substitua por outra lógica)
    const storedUser = JSON.parse(localStorage.getItem('user'));
    const companyId = storedUser?.company_id;

    // Função para validar os campos
    const validateFields = () => {
        const newErrors = {};
        if (!field1.trim()) newErrors.field1 = "Campo 1 é obrigatório!";
        if (!field2.trim()) newErrors.field2 = "Campo 2 é obrigatório!";
        return newErrors;
    };

    // Função para enviar o formulário
    const handleSubmit = (e) => {
        e.preventDefault();

        const validationErrors = validateFields();
        if (Object.keys(validationErrors).length > 0) {
            setErrors(validationErrors);
            return;
        }

        // Se não houver erros, exibe os valores no console
        setErrors({});
        console.log("Valores do formulário:", { field1, field2 });
    };

    // Requisição para buscar dados da API e preencher os estados
    useEffect(() => {
        fetch(`/api/company/${companyId}`)
            .then((response) => response.json())
            .then((data) => {
                // Atualize os estados com os valores da API
                setField1(data.field1 || ""); // Modifique o nome do campo conforme necessário
                setField2(data.field2 || ""); // Modifique o nome do campo conforme necessário
            });
    }, [companyId]); // Executa apenas quando `companyId` muda

    return (
        <Container>
            <Form onSubmit={handleSubmit}>
                <Row>
                    <Col sm={6}>
                        <Form.Group controlId="formField1">
                            <Form.Label>Campo 1</Form.Label>
                            <Form.Control
                                type="text"
                                value={field1} // Substitua `defaultValue` por `value`
                                placeholder="Digite algo no campo 1"
                                onChange={(e) => setField1(e.target.value)} // Atualiza o estado com o valor inserido
                            />
                            {errors.field1 && (
                                <p style={{ color: "red" }}>{errors.field1}</p> // Exibe mensagem de erro, se necessário
                            )}
                        </Form.Group>
                    </Col>
                    <Col sm={6}>
                        <Form.Group controlId="formField2">
                            <Form.Label>Campo 2</Form.Label>
                            <Form.Control
                                type="text"
                                value={field2} // Substitua `defaultValue` por `value`
                                placeholder="Digite algo no campo 2"
                                onChange={(e) => setField2(e.target.value)} // Atualiza o estado com o valor inserido
                            />
                            {errors.field2 && (
                                <p style={{ color: "red" }}>{errors.field2}</p> // Exibe mensagem de erro, se necessário
                            )}
                        </Form.Group>
                    </Col>
                </Row>
                <Button variant="primary" type="submit">
                    Salvar
                </Button>
            </Form>
        </Container>
    );
}
```

---

### Notas Importantes

1. **Modificação Principal**:
   - Substitua `defaultValue` por `value` para vincular o valor do campo ao estado.
   - Use `onChange` para atualizar o estado com os valores inseridos pelo usuário.

2. **Carregamento de Dados**:
   - Utilize o `useEffect` para buscar dados da API ao montar o componente e preencha os estados com os valores retornados.
   - Garanta que os valores iniciais dos estados sejam strings vazias (`""`) para evitar erros ao tentar acessar dados indefinidos.

3. **Validação**:
   - Adicione validação ao formulário para garantir que os campos sejam preenchidos antes do envio.
   - Mostre mensagens de erro ao lado dos campos inválidos.

4. **API e Campos Personalizados**:
   - Altere a URL `/api/company/${companyId}` e os campos `field1` e `field2` conforme a estrutura dos dados da sua API.

---

### Resultado Esperado

- **Ao carregar o formulário**: Os campos serão preenchidos automaticamente com os dados obtidos da API.
- **Ao editar os campos**: O estado será atualizado dinamicamente.
- **Ao enviar o formulário**: Se houver erros, mensagens serão exibidas; caso contrário, os valores serão exibidos no console.

### Exemplo de Saída no Console

```json
{
    "field1": "Valor do Campo 1",
    "field2": "Valor do Campo 2"
}
```

Exemplo referência para lidar com formulários dinâmicos em React!

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Editar dados de um registro no formulário

### Implementação Ajustada

Aplicar as mudanças:

1. O `useEffect` inicializa o estado `admin` ao carregar os dados.
2. Um `useEffect` separado atualiza os campos com os valores do `admin` apenas no modo de edição.
3. O formulário utiliza apenas os valores de estado (`fullUsername`, `email`, etc.) nos campos, garantindo consistência.

As partes do código ficarão assim:

```jsx
useEffect(() => {
    const fetchAdminData = async () => {
        try {
            const response = await fetch(`${apiUrl}/singleAdmin/${companyId}/${id}`);
            if (!response.ok) throw new Error('Erro ao buscar administrador');
            const data = await response.json();
            setAdmin(data);
        } catch (error) {
            setError(error.message);
        } finally {
            setLoading(false);
        }
    };
    if (polymorphic === 2) {
        fetchAdminData();
    }
}, [id, apiUrl, companyId, polymorphic]);

useEffect(() => {
    if (admin) {
        setFullUsername(admin.full_name || "");
        setEmail(admin.email || "");
        setBiologicalSex(admin.biological_sex || "");
        setUserName(admin.username || "");
        setLevel(admin.level !== undefined ? String(admin.level) : "");
    }
}, [admin]);
```

E no JSX dos campos:

```jsx
<Form.Control
    type="text"
    size="sm"
    placeholder=""
    value={fullUsername}
    onChange={(e) => setFullUsername(e.target.value)}
    ref={fullUsernameInputRef}
/>
```

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Modelo Genérico para Formulários com Modo de Edição e Registro

Este exemplo ilustra como implementar um formulário genérico em React, suportando os modos de registro e edição. O modelo utiliza `useState` para gerenciar os valores dos campos e `useEffect` para inicializar os valores no modo de edição.

```jsx
import React, { useState, useEffect, useRef } from 'react';

export function GenericForm({ id, apiUrl }) {
    // Estados dos campos do formulário
    const [field1, setField1] = useState('');
    const [field2, setField2] = useState('');
    const [loading, setLoading] = useState(false);
    const [error, setError] = useState(null);

    // Referência ao formulário
    const formRef = useRef();

    // Variável que define o modo (1 = Registro, 2 = Edição)
    const isEditMode = Boolean(id);

    // Estado para armazenar dados no modo de edição
    const [formData, setFormData] = useState(null);

    // Buscar dados no modo de edição
    useEffect(() => {
        if (isEditMode) {
            const fetchData = async () => {
                setLoading(true);
                try {
                    const response = await fetch(`${apiUrl}/${id}`);
                    if (!response.ok) throw new Error('Erro ao buscar dados.');
                    const data = await response.json();
                    setFormData(data);
                } catch (err) {
                    setError(err.message);
                } finally {
                    setLoading(false);
                }
            };
            fetchData();
        }
    }, [id, apiUrl]);

    // Inicializar os campos com os dados recuperados
    useEffect(() => {
        if (formData) {
            setField1(formData.field1 || '');
            setField2(formData.field2 || '');
        }
    }, [formData]);

    // Função para interceptar o envio do formulário
    const handleSubmit = async (e) => {
        e.preventDefault();
        const payload = {
            field1,
            field2,
        };

        try {
            const response = await fetch(`${apiUrl}${isEditMode ? `/${id}` : ''}`, {
                method: isEditMode ? 'PUT' : 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(payload),
            });
            if (!response.ok) throw new Error('Erro ao enviar formulário.');
            alert(isEditMode ? 'Dados atualizados!' : 'Dados registrados!');
        } catch (err) {
            alert(err.message);
        }
    };

    // Função para resetar os campos
    const handleReset = () => {
        formRef.current.reset();
        setField1('');
        setField2('');
    };

    return (
        <form ref={formRef} onSubmit={handleSubmit}>
            {loading ? (
                <p>Carregando...</p>
            ) : (
                <>
                    {error && <p style={{ color: 'red' }}>{error}</p>}
                    <div>
                        <label>
                            Campo 1:
                            <input
                                type="text"
                                value={field1}
                                onChange={(e) => setField1(e.target.value)}
                            />
                        </label>
                    </div>
                    <div>
                        <label>
                            Campo 2:
                            <input
                                type="text"
                                value={field2}
                                onChange={(e) => setField2(e.target.value)}
                            />
                        </label>
                    </div>
                    <button type="submit">{isEditMode ? 'Atualizar' : 'Registrar'}</button>
                    <button type="button" onClick={handleReset}>
                        Resetar
                    </button>
                </>
            )}
        </form>
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

## Utilizando o Operador Spread para Inserção Condicional de Propriedades

O operador *spread* (reticências: `...`) pode ser usado para “espalhar” as propriedades de um objeto ou os elementos de um array dentro de um novo objeto ou array. Ele é útil, por exemplo, para criar cópias ou mesclar dados, sem modificar o original. 

### Exemplo com objetos

```js
const pessoa = {
  nome: 'João',
  idade: 25,
};

// Aqui, usamos spread para copiar todas as propriedades de `pessoa`
// e adicionar `cidade` no novo objeto:
const novaPessoa = {
  ...pessoa,
  cidade: 'São Paulo',
};

console.log(novaPessoa);
// {
//   nome: 'João',
//   idade: 25,
//   cidade: 'São Paulo',
// }
```

### Exemplo com arrays

```js
const numeros1 = [1, 2, 3];
const numeros2 = [4, 5, 6];

// Aqui, usamos spread para juntar os elementos de duas listas em uma só
const numerosCombinados = [...numeros1, ...numeros2];

console.log(numerosCombinados);
// [1, 2, 3, 4, 5, 6]
```

### Exemplo de uso condicional

```js
function criarUsuario(dados) {
  const { nome, idade, senha } = dados;

  // O operador spread pode ser usado de forma condicional
  // (da mesma forma discutida anteriormente com password).
  // Se 'senha' estiver presente, ela é adicionada ao objeto.
  return {
    nome,
    idade,
    ...(senha && { senha }),
  };
}

console.log(criarUsuario({ nome: 'Ana', idade: 30 }));
// { nome: 'Ana', idade: 30 }

console.log(criarUsuario({ nome: 'Ana', idade: 30, senha: '1234' }));
// { nome: 'Ana', idade: 30, senha: '1234' }
```

Em todos esses exemplos, o operador *spread* nos permite “espalhar” ou copiar os valores de objetos/arrays existentes para novos, facilitando a manipulação e composição de dados.

> Exemplo utilizado para editar usuários, quando o formulário for o de editar, a senha poderá não ser informada e manterá a senha atual.

Em resumo, aquele trecho:

```ts
...(password && { password: hashedPassword }),
```

serve para **incluir condicionalmente** a propriedade `password` no objeto `data`. A expressão `(password && { password: hashedPassword })` funciona assim:

- Se `password` for **falsy** (por exemplo, `null`, `undefined` ou `''`), a expressão resulta em `false`. Como não dá para “espalhar” (`...`) algo que não é um objeto (no caso `false`), nenhuma propriedade é adicionada ao objeto `data`.
- Se `password` for **truthy** (por exemplo, uma string não vazia), a expressão resulta em `{ password: hashedPassword }`. Então o operador de espalhamento (`...`) adiciona a chave `password` com o valor `hashedPassword` ao objeto `data`.

Ou seja, você só adiciona a propriedade `password` ao objeto final se de fato houver uma nova senha definida. Se não houver, a propriedade simplesmente não é incluída.

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
    const {
        title,
        description
    } = req.body; // Adapte os campos conforme a tabela

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
// Rota selecionar e recuperar os dados da tabela "entity".
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
    > ( i ) Dica! Você pode definir a URL Base da sua API no arquivo `.env`, [clique aqui](#uso-de-vari%C3%A1veis-de-ambiente-com-arquivo-env-no-react "clique aqui") para ver exemplos!
- **Campos do Item**: Ajuste `entity.title` e `entity.description` para os campos reais da resposta da API.

#### **Resumo das Etapas**:
1. **Backend**: Configure a rota `GET /getEntities` para retornar todos os registros da tabela.
2. **Frontend**: Use `useEffect` para realizar a requisição `GET` ao montar o componente.
3. **Exibição**: Mapeie o array `entities` para exibir os dados no frontend.

#### **Implementação de Filtros Dinâmicos em Rotas com Parâmetros URL**

Para adaptar a sua rota de modo que ela receba um parâmetro, como um `id` na URL, você precisa utilizar o objeto `req.params`. Este parâmetro será capturado na rota e poderá ser utilizado na consulta para filtrar os registros com base no valor fornecido.

Aqui está como fazer isso de forma criativa:

1. **Defina o parâmetro na rota**: Adicione o parâmetro à definição da URL, por exemplo: `/getEntities/:id`.

2. **Capture o parâmetro na requisição**: Utilize `req.params` para acessar o valor do parâmetro fornecido na URL.

3. **Ajuste a consulta no Prisma**: Use o valor capturado no campo `where` da consulta, convertendo-o para o tipo apropriado, se necessário.

O código ficaria algo assim:

```ts
const { id } = req.params; // Extraia o parâmetro da URL

const entity = await prisma.entity.findMany({
    where: { id: parseInt(id) }, // Filtre os registros com base no ID fornecido
    orderBy: { createdAt: 'desc' } // Continue ordenando, se necessário
});
```

Agora, quando você fizer uma requisição para uma URL como `/getEntities/123`, o `id` será capturado como `"123"`, convertido para um número com `parseInt(id)` e usado para filtrar os registros no banco de dados.

### Como funciona `entities[0]?.title`

1. **`entities[0]`**: Acessa o primeiro item do array retornado pela consulta. Isso assume que `entities` contém pelo menos um registro.
2. **`?.` (Optional Chaining)**: Verifica se `entities[0]` não é `undefined` ou `null` antes de tentar acessar a propriedade `title`. Caso seja, o resultado será `undefined` ao invés de um erro.

### Instrução Complementada

Se você quiser refinar o código e lidar com arrays vazios de forma mais clara, pode adicionar uma verificação extra para tratar a ausência de registros explicitamente. Por exemplo:

```jsx
const firstEntityName = entities[0]?.title || 'Registro não encontrado';
```

Neste exemplo:
- Se `entities[0]` existir, retorna o valor de `title`.
- Caso contrário, retorna a string `'Registro não encontrado'`.

Essa abordagem permite que a rota seja dinâmica e atenda a diferentes IDs fornecidos, tornando-a mais versátil e útil em cenários de consultas específicas!

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
    const {
        title,
        description
    } = req.body; // Adapte os campos conforme necessário

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

## Exemplo Genérico de Organização de Rotas e Controllers

Este guia ilustra como organizar rotas em uma aplicação **Node.js** separando a lógica de negócios em **controllers**. A estrutura sugerida facilita a manutenção e padroniza o desenvolvimento de aplicações com **Express** e **Prisma**.

### Estrutura de Pastas

```
/api
  └── /src
        ├── prisma.ts
        ├── routes.ts
        ├── server.ts
        ├── ...
        └── /controllers
            ├── admins.controller.ts
            └── companySystem.controller.ts
            // ... demais arquivos de controller
```

### 1. Criar Controllers

Crie arquivos de controller na pasta `/controllers`. Cada arquivo representará um conjunto de rotas relacionadas. Por exemplo, no arquivo `/api/src/controllers/admins.controller.ts`:

```ts
import { Request, Response } from "express";
import prisma from "../prisma";

// Listar todos os administradores
export async function getAdmins(req: Request, res: Response) {
    // Lógica de sua rota
}

// Adicionar administrador
export async function addAdmins(req: Request, res: Response) {
    // Lógica de sua rota
}

// Atualizar administrador
export async function updateAdmin(req: Request, res: Response) {
    // Lógica de sua rota
}

// Deletar administrador
export async function deleteAdmin(req: Request, res: Response) {
    // Lógica de sua rota
}
```

> A mesma lógica se aplica a outros “módulos” de rotas, cada qual em seu próprio arquivo controller (ex: `companySystem.controller.ts`, etc.).

### 2. Ajustar o Arquivo de Rotas

No arquivo `/api/src/routes.ts`, basta importar e vincular as funções do controller:

```ts
import express from "express";
export const routes = express.Router();

// -------------------Controllers-------------------
// Import controllers
import { getAdmins, addAdmins, updateAdmin, deleteAdmin } from "./controllers/admins.controller";
import { getCompanySystem } from "./controllers/companySystem.controller";
// ... demais arquivos importações de outros controlleres

// Controller de "admins"
routes.get("/admins/:companyId", getAdmins); // Listar
routes.post("/addAdmins/:companyId", addAdmins); // Adicionar
routes.put("/updateAdmin/:companyId/:id", updateAdmin); // Atualizar
routes.delete("/deleteAdmin/:companyId/:id", deleteAdmin); // Deletar

// Controller de "companySystem"
routes.get("/companySystem/:companyId", getCompanySystem); // Listar
// ... demais arquivos de controllers
// ------------------/Controllers-------------------
```

Dessa forma, cada rota referencia uma função específica do seu controller, mantendo o arquivo de rotas limpo e fácil de gerenciar.

### 3. Adicionar (Opcional) Middlewares

Crie uma pasta `/api/src/middleware` para funções que serão executadas antes dos controllers (exemplo: autenticação, logger, etc.):

```ts
// /api/src/middleware/auth.middleware.ts
import { Request, Response, NextFunction } from "express";

export function authMiddleware(req: Request, res: Response, next: NextFunction) {
  // Lógica de autenticação
  // Se autorizado: next()
  // Se não autorizado: return res.status(401).json({ error: "Acesso negado" });
  return next();
}
```

Em seguida, utilize o middleware em `routes.ts` ou `server.ts`:

```ts
// ...
import { authMiddleware } from "./middleware/auth.middleware";

// Aplica o middleware a todas as rotas:
routes.use(authMiddleware);
```

### Resumo Geral

1. **Criar pastas**: `/controllers` e, opcionalmente, `/middleware`.
2. **Mover lógica de cada rota** para funções em **controllers**.
3. **Importar** essas funções no arquivo de rotas (`routes.ts`) e utilizá-las como callbacks.
4. (Opcional) **Adicionar middlewares** para pré-processar requisições (ex.: autenticação).

Este modelo genérico pode ser adaptado para qualquer aplicação com **Node.js**, **Express** e **Prisma**, garantindo boa **organização** de código e **manutenção** mais simples ao longo do tempo.

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

## Notificação de Conexão de Internet

Este exemplo implementa uma notificação simples que alerta o usuário quando a conexão com a internet é perdida. Ele utiliza **React hooks** e **event listeners** para monitorar o status de conexão (`online` e `offline`).

### Componente React: `ConnectionNotification.jsx`

```jsx
import React, { useEffect, useState } from 'react';

export function ConnectionNotification() {
    const [isOffline, setIsOffline] = useState(false);

    useEffect(() => {
        function updateOnlineStatus() {
            setIsOffline(!navigator.onLine);
        }

        // Adiciona listeners para conexão e desconexão
        window.addEventListener('online', updateOnlineStatus);
        window.addEventListener('offline', updateOnlineStatus);

        // Verifica o status da conexão ao montar o componente
        updateOnlineStatus();

        // Remove listeners ao desmontar o componente
        return () => {
            window.removeEventListener('online', updateOnlineStatus);
            window.removeEventListener('offline', updateOnlineStatus);
        };
    }, []);

    return (
        <div style={{
            position: 'fixed',
            top: 10,
            right: 10,
            backgroundColor: 'red',
            color: 'white',
            padding: '10px',
            borderRadius: '5px',
            display: isOffline ? 'block' : 'none',
            zIndex: 1000,
        }}>
            Internet desconectada!
        </div>
    );
}
```

### Como Usar:

1. **Importe o componente onde será utilizado:**

```jsx
import { ConnectionNotification } from './ConnectionNotification';
```

2. **Adicione ao seu JSX:**

```jsx
function App() {
    return (
        <div>
            <ConnectionNotification />
            <h1>Minha Aplicação</h1>
        </div>
    );
}
```

### Explicação:

1. **Estado `isOffline`**: Controla a visibilidade da notificação com base no status de conexão.
2. **Hook `useEffect`**:
   - Adiciona event listeners para os eventos `online` e `offline`.
   - Atualiza o estado sempre que o status de conexão mudar.
   - Remove os listeners ao desmontar o componente para evitar vazamento de memória.
3. **Estilo Inline**:
   - O estilo do componente é configurado inline, mas pode ser movido para um arquivo CSS, se necessário.

### Centralizar a notificação no centro da tela

```jsx

<div style={{
    position: 'fixed',
    top: '50%',
    left: '50%',
    transform: 'translate(-50%, -50%)', // Centraliza no eixo X e Y
    backgroundColor: 'red',
    color: 'white',
    padding: '10px',
    borderRadius: '5px',
    display: isOffline ? 'block' : 'none',
    zIndex: 1000,
    textAlign: 'center', // Centraliza o texto no conteúdo
}}>
    Sem conexão com a internet!
</div>
```

Este exemplo pode ser usado como base para adicionar notificações de status de conexão em qualquer projeto React.

---

É possível implementar uma funcionalidade que verifica se o dispositivo tem acesso à internet, independentemente de estar conectado via cabo ou Wi-Fi. Para isso, é necessário realizar requisições periódicas a um servidor confiável (como `https://google.com` ou outro domínio de alta disponibilidade). Caso a requisição falhe, podemos considerar que não há conexão com a internet.

Segue um exemplo atualizado do componente:

### Componente Atualizado: **ConnectionNotification.jsx**

```jsx
import React, { useEffect, useState } from 'react';

export function ConnectionNotification() {
    const [isOffline, setIsOffline] = useState(false);

    useEffect(() => {
        let intervalId;

        // Função para verificar conexão com a internet
        async function checkInternetConnection() {
            try {
                // Faz uma requisição simples para um endpoint confiável
                const response = await fetch('https://www.google.com', { mode: 'no-cors' });
                setIsOffline(false); // Se houver resposta, está online
            } catch (error) {
                setIsOffline(true); // Qualquer erro indica offline
            }
        }

        // Verifica a conexão ao montar o componente
        checkInternetConnection();

        // Configura intervalos para verificar a conexão
        intervalId = setInterval(checkInternetConnection, 5000); // Verifica a cada 5 segundos

        // Remove o intervalo ao desmontar o componente
        return () => clearInterval(intervalId);
    }, []);

    return (
        <div style={{
            position: 'fixed',
            top: '50%',
            left: '50%',
            transform: 'translate(-50%, -50%)', // Centraliza no eixo X e Y
            backgroundColor: 'red',
            color: 'white',
            padding: '10px',
            borderRadius: '5px',
            display: isOffline ? 'block' : 'none',
            zIndex: 1000,
            textAlign: 'center', // Centraliza o texto no conteúdo
        }}>
            Internet desconectada!
        </div>
    );
}
```

### Explicação das alterações:

1. **Verificação ativa de conexão:**
   - A função `checkInternetConnection` realiza uma requisição HTTP simples para verificar a conectividade com a internet. O `fetch` tenta acessar um recurso confiável.
   - O cabeçalho `mode: 'no-cors'` é usado para evitar bloqueios de CORS em requisições básicas, onde não nos importamos com a resposta, apenas se a requisição falhou ou não.

2. **Intervalo de Verificação:**
   - Configuramos um intervalo de 5 segundos (ou o valor desejado) para verificar a conexão regularmente.
   - Essa abordagem é útil para detectar quedas de internet mesmo em situações onde o Wi-Fi ou cabo permanece conectado, mas a conexão externa está indisponível.

3. **Remoção do Intervalo:**
   - Ao desmontar o componente, o intervalo configurado é limpo para evitar vazamento de memória.

### Vantagens:
- Detecta queda de conexão externa.
- Atualiza em tempo real.
- Pode ser adaptado para incluir notificações visuais ou sonoras.

### Observação:
Se necessário, um servidor de backend pode ser configurado para responder a essas requisições, minimizando dependências externas. Usar um domínio como `google.com` é apenas uma sugestão prática. 

### Como usar:
Substitua o código antigo pelo novo componente e mantenha o mesmo fluxo de integração no projeto (`<ConnectionNotification />`).

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Modificação para substituir o alert() por uma mensagem estilizada

Aqui está a modificação para substituir o `alert()` por uma mensagem estilizada exibida no canto inferior esquerdo. A mensagem desaparecerá suavemente após 5 segundos.

### Passo 1: Adicione um Estado para Controlar a Exibição da Mensagem
No início do seu componente, adicione este estado:
```jsx
const [successMessage, setSuccessMessage] = useState("");
```

### Passo 2: Atualize a Função `handleSubmit`
Modifique o trecho onde o `alert()` é chamado para usar a mensagem personalizada:
```jsx
if (response.status === 200) {
    const data = response.data;
    setSuccessMessage("Registro atualizado com sucesso!");
    console.log("Registro atualizado:", data);
    setTimeout(() => setSuccessMessage(""), 5000); // Remove a mensagem após 5 segundos
}
```

### Passo 3: Adicione a Div para Mostrar a Mensagem
No retorno (`return`) do seu componente, adicione este código logo acima do `Container`:
```jsx
{successMessage && (
    <div className="successMessage">
        {successMessage}
    </div>
)}
```

### Passo 4: Estilo da Mensagem (CSS)
Adicione o seguinte CSS para estilizar a mensagem. Você pode colocar isso no arquivo CSS correspondente (`styles.module.css` ou qualquer outro arquivo CSS importado no componente):

```css
.successMessage {
    position: fixed;
    top: 10px;
    right: 10px;
    background-color: green;
    color: white;
    padding: 10px 20px;
    border-radius: 2.5px;
    font-size: 14px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    animation: fadeOut 1s ease-in-out forwards;
    z-index: 1000; /* Certifique-se de que está acima de outros elementos */
}

@keyframes fadeOut {
    0% {
        opacity: 1;
    }
    90% {
        opacity: 1;
    }
    100% {
        opacity: 0;
    }
}
```

### Funcionamento Completo:
1. Quando a atualização for bem-sucedida, a mensagem "Registro atualizado com sucesso!" será exibida no canto inferior esquerdo.
2. A mensagem desaparecerá suavemente após 5 segundos, graças à função `setTimeout` e à animação CSS `fadeOut`.

### Resultado
Este método é mais amigável do que o `alert` padrão e oferece uma experiência visual melhor para o usuário.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Exemplo de Reutilização de Notificações com Diferentes Tipos

Aqui está o exemplo genérico para criar notificações de sucesso, alerta e erro com estilos personalizados:

```jsx
import React, { useState } from 'react';
import './Notification.css'; // Certifique-se de importar o CSS

export function NotificationExample() {
    const [notification, setNotification] = useState({ message: "", type: "" });

    // Função para exibir notificações
    const showNotification = (message, type) => {
        setNotification({ message, type }); // Define a mensagem e o tipo
        setTimeout(() => setNotification({ message: "", type: "" }), 5000); // Remove após 5 segundos
    };

    return (
        <div>
            {/* Botões de exemplo para disparar notificações */}
            <button onClick={() => showNotification("Operação realizada com sucesso!", "success")}>
                Notificação de Sucesso
            </button>
            <button onClick={() => showNotification("Algo pode estar errado!", "warning")}>
                Notificação de Alerta
            </button>
            <button onClick={() => showNotification("Erro ao processar a operação!", "error")}>
                Notificação de Erro
            </button>

            {/* Div da notificação */}
            {notification.message && (
                <div className={`notification ${notification.type}`}>
                    {notification.message}
                </div>
            )}
        </div>
    );
}
```

---

### CSS para Estilização
Crie um arquivo `Notification.css` ou adicione ao seu arquivo de estilo global:

```css
/* Estilo base para notificações */
.notification {
    position: fixed;
    top: 10px;
    right: 10px;
    padding: 10px 20px;
    border-radius: 2.5px;
    font-size: 14px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    z-index: 1000;
    color: white;
    opacity: 1;
    animation: fadeOut 5s ease-in-out forwards;
}

/* Notificação de sucesso */
.notification.success {
    background-color: green;
}

/* Notificação de alerta */
.notification.warning {
    background-color: orange;
}

/* Notificação de erro */
.notification.error {
    background-color: red;
}

/* Animação para desaparecer suavemente */
@keyframes fadeOut {
    0% {
        opacity: 1;
    }
    90% {
        opacity: 1;
    }
    100% {
        opacity: 0;
    }
}
```

---

### Funcionamento
1. **Tipos de Notificação:**
   - `success` (verde): Para sucesso.
   - `warning` (laranja): Para alertas.
   - `error` (vermelho): Para erros.
2. **Função `showNotification`:** Aceita dois argumentos:
   - `message`: Texto a ser exibido.
   - `type`: Define a classe CSS para estilização (`success`, `warning`, `error`).
3. **Mensagem Desaparece:** A mensagem desaparece suavemente após 5 segundos.

---

### Resultado
- **Sucesso:** Mostra uma notificação verde com texto branco.
- **Alerta:** Mostra uma notificação laranja com texto branco.
- **Erro:** Mostra uma notificação vermelha com texto branco.

---

### Reutilização
Este exemplo genérico pode ser facilmente reutilizado em qualquer projeto. Você pode passar mensagens personalizadas e o tipo de notificação desejado (`success`, `warning`, ou `error`) para criar uma experiência de notificação rica e dinâmica.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Usar as notificações com 'CSS Modules'

Para usar "CSS Modules" no trecho que contém a notificação, você precisa importar o módulo CSS no componente e substituir as classes CSS padrão pelas propriedades do objeto `styles` fornecido pelo "CSS Module". Aqui está como fazer:

### Passo 1: Certifique-se de Importar o CSS Module
No topo do seu componente, importe o módulo CSS como você já faz em outras partes do código:
```jsx
import styles from './Notification.module.css'; // Substitua pelo nome correto do seu arquivo
```

---

### Passo 2: Ajuste a Classe da Notificação
Substitua o trecho abaixo:
```jsx
<div className={`notification ${notification.type}`}>
```

Por este, que utiliza as classes do CSS Module:
```jsx
<div className={`${styles.notification} ${styles[notification.type]}`}>
```

Aqui, usamos `styles.notification` para a classe base e `styles[notification.type]` para adicionar a classe específica (`success`, `warning`, ou `error`), de acordo com o tipo de notificação.

---

### Passo 3: Atualize o CSS Module
No arquivo CSS Module (`Notification.module.css`), ajuste as classes com nomes adequados para refletir os tipos de notificação. Exemplo:

```css
.notification {
    position: fixed;
    top: 10px;
    right: 10px;
    padding: 10px 20px;
    border-radius: 2.5px;
    font-size: 14px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    z-index: 1000;
    color: white;
    opacity: 1;
    animation: fadeOut 5s ease-in-out forwards;
}

/* Notificação de sucesso */
.success {
    background-color: green;
}

/* Notificação de alerta */
.warning {
    background-color: orange;
}

/* Notificação de erro */
.error {
    background-color: red;
}

/* Animação para desaparecer suavemente */
@keyframes fadeOut {
    0% {
        opacity: 1;
    }
    90% {
        opacity: 1;
    }
    100% {
        opacity: 0;
    }
}
```

---

### Resultado Final do JSX
O JSX atualizado ficará assim:
```jsx
{/* Div da notificação */}
{notification.message && (
    <div className={`${styles.notification} ${styles[notification.type]}`}>
        {notification.message}
    </div>
)}
```

Com isso, o "CSS Module" será aplicado corretamente para cada tipo de notificação (sucesso, alerta ou erro).

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

## Renderização Condicional de Elementos com Base na Largura da Tela em React.js

Você pode usar o hook `useState` e o evento `resize` para criar essa funcionalidade. O exemplo abaixo mostra como você pode implementar isso:

### Código:

```jsx
import React, { useState, useEffect } from "react";

const ResponsiveDiv = () => {
  const [isLargeScreen, setIsLargeScreen] = useState(window.innerWidth > 600);

  useEffect(() => {
    const handleResize = () => {
      setIsLargeScreen(window.innerWidth > 600);
    };

    window.addEventListener("resize", handleResize);
    // Limpar o evento ao desmontar o componente
    return () => {
      window.removeEventListener("resize", handleResize);
    };
  }, []);

  return (
    <div>
      {isLargeScreen && <div>Esta é uma tela maior que 600px.</div>}
    </div>
  );
};

export default ResponsiveDiv;
```

### Explicação:
1. **Hook `useState`**:
   - Usamos `useState` para controlar se a tela é maior que 600px (`isLargeScreen`).

2. **Verificar a largura inicial**:
   - O estado inicial é definido com base na largura da janela (`window.innerWidth`).

3. **Evento `resize`**:
   - Dentro de um `useEffect`, adicionamos um listener para o evento `resize`, que é acionado sempre que a janela é redimensionada.
   - Quando isso acontece, a função `handleResize` atualiza o estado com base na largura atual da janela.

4. **Limpeza do evento**:
   - O retorno do `useEffect` remove o listener quando o componente é desmontado, evitando possíveis vazamentos de memória.

5. **Renderização condicional**:
   - Usamos uma expressão condicional para exibir o `<div>` apenas quando a largura for maior que 600px.

Esse componente é funcional e reutilizável. É só importar e usar no seu projeto React. 😊

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Navegação Dinâmica com React Router: Redirecionando para Componentes em uma SPA

Para redirecionar para o componente `<RegisterSegment />` ao clicar no link, você pode usar o roteamento do React com a biblioteca **React Router**. Isso permitirá que você navegue para diferentes componentes ou páginas em sua aplicação.

### Passos para implementar:

1. **Configure o roteamento na sua aplicação**:
   Se ainda não tiver o roteamento configurado, instale o **React Router**:
   ```bash
   npm install react-router-dom
   ```

2. **Defina as rotas no seu aplicativo**:
   No seu arquivo principal, por exemplo, `App.js` ou `index.js`, adicione as rotas para `<Login />` e `<RegisterSegment />`.

   ```jsx
   import React from 'react';
   import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';
   import Login from './Login';
   import RegisterSegment from './RegisterSegment';
   
   function App() {
       return (
           <Router>
               <Routes>
                   <Route path="/" element={<Login />} />
                   <Route path="/register" element={<RegisterSegment />} />
               </Routes>
           </Router>
       );
   }
   
   export default App;
   ```

3. **Atualize o link na seção de login**:
   No componente de login, substitua o `href="#"` pelo componente `<Link />` do **React Router**:

   ```jsx
   import { Link } from 'react-router-dom';
   ...
   return (
       ...
       <p className={styles.forget}>
           Não tem uma conta? 
           <Link to="/register" title="Clique para criar uma nova conta">Inscrever-se</Link>
       </p>
       ...
   );
   ```

4. **Implemente o componente `<RegisterSegment />`**:
   Certifique-se de que o componente `<RegisterSegment />` está definido e pronto para ser exibido.

   ```jsx
   import React from 'react';
   
   function RegisterSegment() {
       return (
           <section>
               <h2>Crie sua Conta</h2>
               <form>
                   {/* Formulário de registro */}
               </form>
           </section>
       );
   }
   
   export default RegisterSegment;
   ```

### Resultado esperado:
Agora, ao clicar no link "Inscrever-se", o usuário será redirecionado para o caminho `/register`, e o componente `<RegisterSegment />` será exibido.

Essa abordagem também mantém a navegação gerenciada pelo React Router, sem recarregar a página.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Usando Imagens PNG como Ícones em Componentes React

### Descrição
Este exemplo mostra como substituir ícones de bibliotecas como Font Awesome por imagens PNG em um componente React. Usamos o elemento `<img />` para exibir o ícone, garantindo flexibilidade para personalizar o tamanho e o caminho da imagem.

### Exemplo de Implementação
Aqui está um exemplo genérico que pode ser adaptado para diferentes contextos no seu projeto:

```jsx
import React from 'react';

const MyComponent = ({ onClick }) => {
  return (
    <div className="icon-container">
      <button onClick={onClick} title="Ação do Ícone">
        <img 
          src="/path/to/your-icon.png" 
          alt="Ícone Descritivo" 
          style={{ width: '48px', height: '48px' }} 
        />
      </button>
    </div>
  );
};

export default MyComponent;
```

### Explicação do Código
1. **Elemento `<img />`**:
   - O atributo `src` especifica o caminho para o arquivo PNG.
   - O atributo `alt` descreve a imagem para melhorar a acessibilidade.
   - O estilo inline (`style={{ width: '48px', height: '48px' }}`) define o tamanho do ícone. Você pode ajustá-lo ou usar classes CSS.

2. **Botão Envolvendo o Ícone**:
   - O ícone está dentro de um elemento `<button>` para torná-lo clicável.
   - O atributo `title` adiciona uma dica visual ao passar o mouse sobre o botão.

3. **Callback para Clique**:
   - O atributo `onClick` está configurado para executar uma função quando o ícone é clicado.

### Estrutura de Diretórios
Certifique-se de organizar os arquivos corretamente:
```
src/
├── components/
│   └── MyComponent.jsx
├── assets/
│   └── icons/
│       └── your-icon.png
```

### Dica Extra: Importar a Imagem
Para setups com Webpack, Vite ou Create React App, importe o ícone diretamente no arquivo do componente:

```jsx
import yourIcon from '../assets/icons/your-icon.png';

const MyComponent = ({ onClick }) => {
  return (
    <div className="icon-container">
      <button onClick={onClick} title="Ação do Ícone">
        <img 
          src={yourIcon} 
          alt="Ícone Descritivo" 
          style={{ width: '48px', height: '48px' }} 
        />
      </button>
    </div>
  );
};
```

Com isso, o caminho para a imagem é resolvido automaticamente pelo bundler, garantindo que os assets sejam processados corretamente.

### Estilização Opcional
Adicione classes CSS para controlar o estilo da imagem e do botão:

```css
.icon-container button {
  background: none;
  border: none;
  cursor: pointer;
}

.icon-container img {
  display: block;
  width: 48px;
  height: 48px;
}
```

Este exemplo pode ser facilmente adaptado para outros componentes e cenários no seu projeto.

### Veja o código adaptado no React-Fenestra

Para usar uma imagem PNG como ícone no seu componente, você pode substituir o uso do componente `<FontAwesomeIcon />` por um elemento `<img />`. O elemento `<img />` permite especificar a fonte da imagem (o caminho para o arquivo PNG) diretamente no atributo `src`. Aqui está como você pode fazer a adaptação:

### Código adaptado
```jsx
... outras linhas ...
  return (
    <Desktop
      icons={[

        ({ fenestra }) =>
          <Icon title="Configurações"
            icon={
              <img 
                src="/path/to/config-icon.png" 
                alt="Ícone Configurações" 
                style={{ width: '48px', height: '48px' }} 
              />
            }
            onClick={() => fenestra.open({
              title: "Configurações",
              left: (window.innerWidth - 990) / 2,
              top: (window.innerHeight - 510) / 2,
              width: 990,
              height: 510,
              content: ({ fenestra }) =>
                <SettingsForTheSystem fenestra={fenestra} />
            })}
          />,
... outras linhas ...
```

### Explicação das mudanças
1. **Substituir `<FontAwesomeIcon />` por `<img />`**:
   - Usei o elemento `<img />` para exibir a imagem PNG. O caminho para a imagem foi passado no atributo `src`.
   - O atributo `alt` adiciona um texto descritivo para acessibilidade e para casos em que a imagem não é carregada.

2. **Adicionando estilo para o tamanho da imagem**:
   - Defini as dimensões da imagem diretamente no `style`. Ajuste os valores de `width` e `height` conforme necessário para alinhar o tamanho do ícone com o design.

3. **Caminho para a imagem**:
   - Substitua `"/path/to/config-icon.png"` pelo caminho correto para o seu arquivo PNG. Ele pode estar em um diretório público, como `public/icons/`, ou ser importado diretamente como módulo (veja a seção **Dica Extra**).

---

### Dica Extra: Importar o arquivo PNG
Se você estiver usando uma configuração como o Create React App, Next.js ou outra ferramenta de build que suporte Webpack, pode importar a imagem diretamente no JavaScript:

```jsx
import configIcon from '/path/to/config-icon.png';

... outras linhas ...

<Icon title="Configurações"
  icon={
    <img 
      src={configIcon} 
      alt="Ícone Configurações" 
      style={{ width: '48px', height: '48px' }} 
    />
  }
  onClick={...}
/>
```

Com isso, você pode organizar melhor seus assets e garantir que o caminho da imagem seja resolvido corretamente pelo bundler.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Uso de URLs Externas para Imagens em Componentes React

A importação direta de uma URL externa não funciona no JavaScript padrão ou no Webpack porque a importação espera arquivos locais que possam ser processados no build. No entanto, você pode usar imagens externas no React diretamente no atributo `src` do elemento `<img />`.

### Como Resolver
Em vez de tentar importar a URL externa, use-a diretamente no `src` do elemento `<img />`. Veja como:

```jsx
... outras linhas ...
<Icon 
  title="Configurações"
  icon={
    <img 
      src="https://github.com/systemboys/SiSFloatBase_image/blob/main/Settings_icon.png?raw=true"
      alt="Ícone Configurações"
      style={{ width: '48px', height: '48px' }}
    />
  }
  onClick={...}
/>
... outras linhas ...
```

### Explicação
1. **Uso de URL no `src`**:
   - A URL externa pode ser passada diretamente para o atributo `src` no elemento `<img />`. Certifique-se de que a URL seja acessível e permita o carregamento da imagem.

2. **Sem Importação Necessária**:
   - Não é necessário importar a imagem porque você está usando o caminho absoluto diretamente.

---

### Por Que Importar Não Funciona?
- O método `import` processa os arquivos localmente (normalmente no momento do build) e não suporta URLs externas.
- URLs externas devem ser usadas como valores de string, atribuídas diretamente no código.

Se você realmente precisa de um método programático para carregar imagens externas em diferentes partes do código, considere usar uma função que encapsule a URL e retorne o elemento:

```jsx
const ExternalIcon = ({ src, alt, size = 48 }) => (
  <img 
    src={src} 
    alt={alt} 
    style={{ width: size, height: size }} 
  />
);

... outras linhas ...

<Icon 
  title="Configurações"
  icon={
    <ExternalIcon 
      src="https://github.com/systemboys/SiSFloatBase_image/blob/main/Settings_icon.png?raw=true"
      alt="Ícone Configurações"
    />
  }
  onClick={...}
/>
```

Com essa abordagem, você pode reutilizar o componente `ExternalIcon` para carregar imagens externas em qualquer lugar do seu projeto.

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

## Como implementar Ícones Font-Awesome em componentes React

Para utilizar ícones da biblioteca **Font-Awesome** em componentes React, siga os passos abaixo:

### 1. Instalação da biblioteca

Primeiro, instale os pacotes necessários do **Font-Awesome**:

```bash
npm install @fortawesome/react-fontawesome @fortawesome/free-solid-svg-icons
```

Caso precise de outros estilos, como **regular** ou **brand icons**, instale os pacotes correspondentes:

```bash
npm install @fortawesome/free-regular-svg-icons @fortawesome/free-brands-svg-icons
```

---

### 2. Importação dos ícones no componente

No arquivo do componente, importe o `FontAwesomeIcon` e os ícones desejados:

```jsx
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome';
import { faCheck, faTimes } from '@fortawesome/free-solid-svg-icons';
```

---

### 3. Uso dos ícones no JSX

Os ícones podem ser adicionados no JSX utilizando a tag `<FontAwesomeIcon>` com a propriedade `icon`. Veja um exemplo:

```jsx
import React from 'react';
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome';
import { faCheck, faTimes } from '@fortawesome/free-solid-svg-icons';

const IconExample = () => {
    return (
        <div>
            <h2>Exemplo de Ícones Font-Awesome</h2>
            <div>
                <FontAwesomeIcon icon={faCheck} style={{ color: 'green', marginRight: '10px' }} />
                <span>Sucesso</span>
            </div>
            <div>
                <FontAwesomeIcon icon={faTimes} style={{ color: 'red', marginRight: '10px' }} />
                <span>Erro</span>
            </div>
        </div>
    );
};

export default IconExample;
```

---

### 4. Adicionando classes e estilos personalizados

Você também pode adicionar classes do CSS ou aplicar estilos inline aos ícones:

#### Exemplo com `className`:

```jsx
<FontAwesomeIcon icon={faCheck} className="icon-success" />
```

```css
/* Estilo no CSS */
.icon-success {
    color: green;
    font-size: 24px;
}
```

#### Exemplo com `style` inline:

```jsx
<FontAwesomeIcon icon={faTimes} style={{ color: 'red', fontSize: '20px' }} />
```

---

### 5. Trabalhando com outros estilos de ícones

Além dos ícones sólidos (**solid**), você pode importar outros estilos:

- **Regular**:

```jsx
import { faSmile } from '@fortawesome/free-regular-svg-icons';

<FontAwesomeIcon icon={faSmile} />
```

- **Brands** (marcas, como GitHub, Facebook, etc.):

```jsx
import { faGithub } from '@fortawesome/free-brands-svg-icons';

<FontAwesomeIcon icon={faGithub} />
```

---

### 6. Exemplo completo com múltiplos estilos

Aqui está um exemplo com **ícones sólidos, regulares e de marca**:

```jsx
import React from 'react';
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome';
import { faCheck, faTimes } from '@fortawesome/free-solid-svg-icons';
import { faSmile } from '@fortawesome/free-regular-svg-icons';
import { faGithub } from '@fortawesome/free-brands-svg-icons';

const FullIconExample = () => {
    return (
        <div>
            <h2>Exemplo Completo de Ícones</h2>
            <div>
                <FontAwesomeIcon icon={faCheck} style={{ color: 'green', marginRight: '10px' }} />
                Ícone Sólido - Check
            </div>
            <div>
                <FontAwesomeIcon icon={faSmile} style={{ color: 'blue', marginRight: '10px' }} />
                Ícone Regular - Smile
            </div>
            <div>
                <FontAwesomeIcon icon={faGithub} style={{ color: 'black', marginRight: '10px' }} />
                Ícone Brand - GitHub
            </div>
            <div>
                <FontAwesomeIcon icon={faTimes} style={{ color: 'red', marginRight: '10px' }} />
                Ícone Sólido - Times
            </div>
        </div>
    );
};

export default FullIconExample;
```

---

### Observações

1. **Organização**: Mantenha os ícones importados no topo do arquivo para melhor organização.
2. **Reutilização**: Considere criar um componente separado para ícones reutilizáveis.
3. **Performance**: Importe apenas os ícones necessários para evitar sobrecarregar o bundle.

---

Com essas instruções, você pode facilmente implementar e personalizar ícones do **Font-Awesome** em projetos React! 🚀

### Visualizar e escolher os ícones do Font-Awesome

Para visualizar e escolher os ícones do **Font-Awesome**, você pode acessar o site oficial onde está disponível a **lista completa de ícones**:

### Link para a lista de ícones do Font-Awesome:
- [Font-Awesome Icons](https://fontawesome.com/icons)

---

### **Como encontrar ícones específicos?**

1. **Pesquisar por nome ou palavra-chave**:
   - No campo de busca do site, digite palavras-chave relacionadas ao ícone desejado, como "check", "home", "user", "arrow", etc.

2. **Filtrar por estilo de ícones**:
   - Você pode alternar entre os estilos:
     - **Solid**: Ícones preenchidos.
     - **Regular**: Ícones com contornos mais finos.
     - **Brands**: Ícones de marcas (como Facebook, GitHub, etc.).

3. **Visualizar e copiar o nome do ícone**:
   - Ao selecionar um ícone, o site exibe o nome correspondente, que pode ser usado na sua aplicação, por exemplo:
     ```jsx
     import { faCheck, faTimes } from '@fortawesome/free-solid-svg-icons';
     ```

---

### Dica Extra:
- Você também pode usar diretamente a busca do Google para achar ícones rapidamente com termos como:
  - **"Font Awesome check icon"**
  - **"Font Awesome github brand icon"**

Com essas informações, será fácil navegar pelo site e selecionar os ícones que você deseja utilizar no projeto! 🚀

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Componente de Ping React com Histórico de Respostas

Este componente em React realiza pings periódicos em um servidor ou URL especificado, exibindo os tempos de resposta no formato de um histórico limitado por uma quantidade configurável de linhas. Ideal para aplicações que precisam monitorar o tempo de resposta de serviços web.

### Código do Componente

```jsx
import React, { useEffect, useState } from 'react';

const PingComponent = () => {
    const [pingHistory, setPingHistory] = useState([]);
    const shootPingAgainst = "https://www.google.com"; // URL de destino do ping
    const targetName = "Google"; // Nome amigável do alvo
    const quantityOfLines = 14; // Quantidade máxima de linhas no histórico

    const pingHost = async () => {
        try {
            const startTime = performance.now();
            await fetch(shootPingAgainst, { mode: 'no-cors' });
            const endTime = performance.now();
            const time = (endTime - startTime).toFixed(1);
            const newPing = `64 bytes : time=${time} ms`;

            // Atualiza o histórico, limitando o número de linhas
            setPingHistory((prevHistory) => {
                const updatedHistory = [...prevHistory, newPing];
                return updatedHistory.length > quantityOfLines
                    ? updatedHistory.slice(1)
                    : updatedHistory;
            });
        } catch (error) {
            const errorPing = 'Error: Ping failed';
            setPingHistory((prevHistory) => {
                const updatedHistory = [...prevHistory, errorPing];
                return updatedHistory.length > quantityOfLines
                    ? updatedHistory.slice(1)
                    : updatedHistory;
            });
        }
    };

    useEffect(() => {
        const interval = setInterval(() => {
            pingHost();
        }, 1000); // Realiza o ping a cada 1 segundo

        return () => clearInterval(interval); // Limpa o intervalo ao desmontar o componente
    }, []);

    return (
        <div
            style={{
                width: '165px',
                height: '200px',
                backgroundColor: '#000',
                borderRadius: '2.5px',
                color: '#689F38',
                fontFamily: 'monospace',
                overflow: 'hidden',
                padding: '10px',
                boxSizing: 'border-box',
                border: '1px solid #689F38',
            }}
        >
            <div
                style={{
                    display: 'flex',
                    flexDirection: 'column',
                    alignItems: 'flex-start',
                    overflowY: 'hidden',
                    fontSize: '10px',
                }}
            >
                <p style={{ margin: '0 auto', lineHeight: '1.2' }}>
                    ### [{targetName}] ###
                </p>
                {pingHistory.map((ping, index) => (
                    <p key={index} style={{ margin: '0', lineHeight: '1.2' }}>
                        {ping}
                    </p>
                ))}
            </div>
        </div>
    );
};

export default PingComponent;
```

### Como Usar

1. **Importação e Renderização**: Importe o componente e renderize-o em qualquer lugar da sua aplicação:
   ```jsx
   import PingComponent from './PingComponent';
   
   function App() {
       return (
           <div>
               <PingComponent />
           </div>
       );
   }
   
   export default App;
   ```

2. **Customização**:
   - Altere `shootPingAgainst` para o URL que deseja monitorar.
   - Modifique `targetName` para um nome descritivo do alvo.
   - Ajuste `quantityOfLines` para limitar o número de registros exibidos no histórico.

3. **Estilo**:
   O componente inclui um estilo básico que pode ser ajustado diretamente nos objetos `style` ou extraído para um arquivo CSS.

4. **Limitações**:
   - A opção `mode: 'no-cors'` no `fetch` é usada para evitar problemas de CORS, mas pode limitar a captura de respostas completas.
   - O componente não utiliza bibliotecas externas, mantendo-o leve, mas a funcionalidade de ping depende da disponibilidade da rede e permissões do navegador.

---

### Observações

Este componente é ideal para monitoramento básico. Para soluções mais avançadas, considere o uso de ferramentas especializadas e logs detalhados com frameworks de monitoramento.

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

## Envio de Emails com Backend utilizando Nodemailer

Este guia demonstra como configurar um backend com **Node.js** para enviar emails utilizando a biblioteca **Nodemailer**. Ele também mostra como integrar o backend com um frontend React.

---

### Estrutura de Diretórios

```plaintext
project/
├── server/
│   ├── api/
│   │   └── email.js       # Rota para envio de email
│   ├── server.js          # Configuração principal do servidor
│   ├── .env               # Configurações sensíveis (e-mail e senha)
├── client/
│   ├── src/
│   │   ├── components/
│   │   │   └── ContactForm.jsx  # Componente React para o formulário
│   │   └── App.jsx        # Aplicação principal
├── package.json           # Configuração do projeto
```

---

### Configuração do Backend

#### 1. Instalar Dependências

No diretório `server`, instale as dependências necessárias:

```bash
npm install express nodemailer dotenv
```

#### 2. Configuração do Servidor

Crie o arquivo `server/server.js`:

```javascript
import express from 'express';
import emailRouter from './api/email.js'; // Importa a rota para envio de email
import dotenv from 'dotenv';

dotenv.config(); // Carrega as variáveis do arquivo .env

const app = express();
const PORT = process.env.PORT || 5000;

app.use(express.json()); // Middleware para interpretar JSON
app.use('/api', emailRouter); // Rota para APIs

app.listen(PORT, () => {
  console.log(`Servidor rodando na porta ${PORT}`);
});
```

#### 3. Criar Rota para Envio de Email

No diretório `server/api`, crie o arquivo `email.js`:

```javascript
import express from 'express';
import nodemailer from 'nodemailer';

const router = express.Router();

router.post('/send-email', async (req, res) => {
  const { name, email, subject, message } = req.body;

  if (!name || !email || !subject || !message) {
    return res.status(400).json({ error: 'Todos os campos são obrigatórios.' });
  }

  try {
    const transporter = nodemailer.createTransport({
      service: 'Gmail', // Pode ser outro provedor (Outlook, Yahoo, etc.)
      auth: {
        user: process.env.EMAIL_USER, // Email configurado no arquivo .env
        pass: process.env.EMAIL_PASS, // Senha de app (não a senha do email pessoal)
      },
    });

    await transporter.sendMail({
      from: `"${name}" <${email}>`, // Remetente
      to: 'suporte@seudominio.com', // Destinatário
      subject, // Assunto
      text: message, // Corpo do email
    });

    res.status(200).json({ message: 'E-mail enviado com sucesso!' });
  } catch (error) {
    console.error(error);
    res.status(500).json({ error: 'Erro ao enviar o e-mail.' });
  }
});

export default router;
```

#### 4. Configuração do `.env`

Crie o arquivo `server/.env` para armazenar variáveis sensíveis:

```plaintext
EMAIL_USER=seuemail@gmail.com
EMAIL_PASS=suasenhadeapp
```

> **Nota:** Use uma senha de aplicativo gerada pelo provedor do e-mail (ex.: Gmail).

---

### Configuração do Frontend

#### 1. Criar o Formulário de Contato

No diretório `client/src/components`, crie o arquivo `ContactForm.jsx`:

```jsx
import React, { useState } from 'react';

const ContactForm = () => {
  const [name, setName] = useState('');
  const [email, setEmail] = useState('');
  const [subject, setSubject] = useState('');
  const [message, setMessage] = useState('');

  const handleSubmit = async (e) => {
    e.preventDefault();

    if (!name || !email || !subject || !message) {
      alert('Todos os campos são obrigatórios.');
      return;
    }

    try {
      const response = await fetch('/api/send-email', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({ name, email, subject, message }),
      });

      if (response.ok) {
        alert('E-mail enviado com sucesso!');
        setName('');
        setEmail('');
        setSubject('');
        setMessage('');
      } else {
        alert('Erro ao enviar o e-mail.');
      }
    } catch (error) {
      console.error('Erro ao conectar com o servidor:', error);
      alert('Falha ao conectar com o servidor.');
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Nome:
        <input
          type="text"
          value={name}
          onChange={(e) => setName(e.target.value)}
        />
      </label>
      <label>
        E-mail:
        <input
          type="email"
          value={email}
          onChange={(e) => setEmail(e.target.value)}
        />
      </label>
      <label>
        Assunto:
        <input
          type="text"
          value={subject}
          onChange={(e) => setSubject(e.target.value)}
        />
      </label>
      <label>
        Mensagem:
        <textarea
          value={message}
          onChange={(e) => setMessage(e.target.value)}
        />
      </label>
      <button type="submit">Enviar</button>
    </form>
  );
};

export default ContactForm;
```

#### 2. Integrar o Formulário no Frontend

No arquivo `client/src/App.jsx`:

```jsx
import React from 'react';
import ContactForm from './components/ContactForm';

const App = () => (
  <div>
    <h1>Formulário de Contato</h1>
    <ContactForm />
  </div>
);

export default App;
```

---

### Executar o Projeto

1. **Iniciar o servidor backend**:
   No diretório `server`:
   ```bash
   node server.js
   ```

2. **Iniciar o frontend**:
   No diretório `client`:
   ```bash
   npm start
   ```

---

### Notas Finais

- Substitua `suporte@seudominio.com` pelo endereço de e-mail para onde as mensagens devem ser enviadas.
- Certifique-se de que o backend esteja acessível ao frontend, configurando proxies ou utilizando um endereço de rede público.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Manipulação de Objetos no DOM com JavaScript

Aqui estão exemplos genéricos de manipulações no DOM usando JavaScript. Estes exemplos podem ser usados para remover, adicionar antes ou adicionar depois de um elemento existente no DOM.

---

### Remover um Elemento Específico pelo ID

```javascript
// Seleciona o elemento pelo ID
const element = document.getElementById('example_id');
if (element) {
    element.remove(); // Remove o elemento do DOM
    console.log('Elemento removido com sucesso!');
} else {
    console.error('Elemento não encontrado!');
}
```

---

### Adicionar um Elemento Antes de Outro no DOM

```javascript
// Seleciona o elemento de referência
const referenceElement = document.getElementById('example_id');
if (referenceElement) {
    // Cria um novo elemento
    const newElement = document.createElement('div');
    newElement.textContent = 'Novo elemento antes';
    newElement.className = 'new-element';

    // Insere o novo elemento antes do elemento de referência
    referenceElement.parentNode.insertBefore(newElement, referenceElement);
    console.log('Novo elemento adicionado antes do elemento de referência!');
} else {
    console.error('Elemento de referência não encontrado!');
}
```

---

### Adicionar um Elemento Depois de Outro no DOM

```javascript
// Seleciona o elemento de referência
const referenceElement = document.getElementById('example_id');
if (referenceElement) {
    // Cria um novo elemento
    const newElement = document.createElement('div');
    newElement.textContent = 'Novo elemento depois';
    newElement.className = 'new-element';

    // Insere o novo elemento após o elemento de referência
    referenceElement.parentNode.insertBefore(newElement, referenceElement.nextSibling);
    console.log('Novo elemento adicionado depois do elemento de referência!');
} else {
    console.error('Elemento de referência não encontrado!');
}
```

---

### Substituir um Elemento por Outro no DOM

```javascript
// Seleciona o elemento que será substituído
const oldElement = document.getElementById('example_id');
if (oldElement) {
    // Cria um novo elemento
    const newElement = document.createElement('div');
    newElement.textContent = 'Elemento substituto';
    newElement.className = 'replacement-element';

    // Substitui o elemento antigo pelo novo
    oldElement.parentNode.replaceChild(newElement, oldElement);
    console.log('Elemento substituído com sucesso!');
} else {
    console.error('Elemento a ser substituído não encontrado!');
}
```

---

### Substituir um Elemento do DOM por um elemento com Componente React

Para substituir o elemento por um componente React `<ReactComponent />`, você deve renderizá-lo dentro do elemento alvo usando `ReactDOM.createRoot`. Veja os códigos a seguir:

### Códigos:

1. **Indicação o Elemento Alvo:**

Adicione um novo `elemento alvo`, no nosso caso, será uma `div` e siga os três passos a seguir:

```jsx
{/* ... outras linhas ... */}
<Container>
    <div className="elementClass"></div>
</Container>
{/* ... outras linhas ... */}
```

> ( ! ) Se houver algo dentro do elemento e você precisa substituí-lo, como pro exemplo, um componente que precisa ser renderizado novamente, coloque-o dentro do elemento alvo!

2. **Importações dependentes:**

Importe o `ReactDOM` e o `ReactComponent` no componente que executará o script.

```jsx
import ReactDOM from 'react-dom/client';
import { ReactComponent } from '../../ReactComponent';
```

> ( ! ) `ReactComponent` será o componente o qual estará dentro do elemento alvo, importe no início do seu código!

3. **Script que substituirá o elemento alvo:**

Implemente o script a seguir no seu componente. 

```jsx
// Substituir o Elemento do DOM pelo elemento com o Componente React '<ReactComponent />'.
const oldElement = document.querySelector('.elementClass'); // Seleciona o elemento que será substituído.
if (oldElement) {
    // Cria um novo elemento para renderizar o componente React.
    const newElement = document.createElement('div');
    newElement.className = 'elementClass';

    // Substitui o elemento antigo pelo novo.
    oldElement.parentNode.replaceChild(newElement, oldElement);

    // Cria a raiz para renderizar com React.
    const root = ReactDOM.createRoot(newElement);
    root.render(<ReactComponent />);

    console.log('Componente ReactComponent renderizado com sucesso!');
} else {
    console.error('Elemento a ser substituído não encontrado!');
}
```

> ( ! ) Exemplo de uso: Esse script, pode ser executado em algum evento, dentro do componente antes do `return(...)`!

### Explicação:
1. **Selecionar o Elemento Alvo:**
   O script localiza o elemento com `id='elementID'`.
   ( ! ) Pode ser uma classe também, mudando `getElementById('elementID')` para `querySelector('.elementClass')`!

2. **Criar um Novo Elemento para Substituição:**
   Um novo elemento `<div>` é criado como container para o componente React. A classe `replacement-element` é adicionada para estilização, se necessário.

3. **Substituir o Elemento Antigo:**
   O novo elemento substitui o antigo usando `replaceChild`.

4. **Renderizar o Componente React:**
   O ReactDOM é usado para renderizar `<ReactComponent />` no novo elemento substituto.

5. **Conclusão:**
   O elemento alvo terá o `<ReactComponent />` como conteúdo.

   > Exemplo:
   ```jsx
   {/* ... outras linhas ... */}
   <Container>
       <div className="elementClass">
           <ReactComponent />
       </div>
   </Container>
   {/* ... outras linhas ... */}
   ```

### Considerações:
- **React no Frontend:** Essa abordagem é válida quando você precisa combinar manipulação do DOM com renderizações React.
- **Manutenção do Estado no React:** Se o `fenestra` vier de um estado ou contexto React, certifique-se de que está acessível no escopo do script.

Com isso, o componente `<ReactComponent>` será renderizado no lugar do elemento substituído.

---

### Exemplo Genérico para Substituir Elemento do DOM por Componente React

Este exemplo demonstra como substituir um elemento do DOM existente por um componente React, garantindo que a manipulação do DOM seja integrada ao ciclo de vida do React.

#### Código Genérico

> Importação do ReactDOM
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
```

> Exemplo de componente React
```jsx
// Exemplo de componente React
const ExampleComponent = ({ propValue }) => (
    <div>
        <h1>Componente React</h1>
        <p>Propriedade recebida: {propValue}</p>
    </div>
);
```

> Função para substituir um elemento do DOM por um elemento com componente React
```jsx
// Função para substituir um elemento do DOM por um elemento com componente React
function replaceElementWithReactComponent(elementId, ReactComponent, props = {}) {
    // Seleciona o elemento que será substituído
    const oldElement = document.getElementById('elementId');
    if (oldElement) {
        // Cria um novo elemento para renderizar o componente React
        const newElement = document.createElement('div');
        newElement.className = 'replacement-element';

        // Substitui o elemento antigo pelo novo
        oldElement.parentNode.replaceChild(newElement, oldElement);

        // Renderiza o componente React no novo elemento
        ReactDOM.createRoot(<ReactComponent {...props} />, newElement);

        console.log(`Elemento #${elementId} substituído com sucesso!`);
    } else {
        console.error(`Elemento com o ID '${elementId}' não foi encontrado.`);
    }
}
```

> Exemplo de uso
```jsx
// Exemplo de uso
replaceElementWithReactComponent('elemento-alvo', ExampleComponent, { propValue: 'Exemplo de valor' });
```

#### Explicação:
1. **Componente React**: O exemplo utiliza `ExampleComponent`, que pode ser substituído por qualquer componente React.
2. **Função Reutilizável**: A função `replaceElementWithReactComponent` facilita a substituição de qualquer elemento do DOM por um elemento com componente React.
3. **Parâmetros Dinâmicos**:
   - `elementId`: O ID do elemento que será substituído.
   - `ReactComponent`: O componente React que será renderizado.
   - `props`: Propriedades passadas para o componente React.

#### Como Usar:
1. Substitua `ExampleComponent` pelo seu componente.
2. Passe o `ID` do elemento alvo e as propriedades necessárias para o componente.
3. Garanta que o elemento alvo existe no DOM antes de executar o script.

#### Observações:
- **Consistência com React**: Use essa abordagem apenas quando necessário manipular diretamente o DOM; priorize soluções React sempre que possível.
- **Desmontar Componentes**: Se o elemento que será substituído já tiver um componente React, considere desmontá-lo antes de substituir o DOM. Use `ReactDOM.unmountComponentAtNode` para evitar vazamentos de memória.

### Adicionar um Novo Elemento como Filho de Outro

```javascript
// Seleciona o elemento pai
const parentElement = document.getElementById('example_parent');
if (parentElement) {
    // Cria um novo elemento
    const newElement = document.createElement('div');
    newElement.textContent = 'Novo elemento filho';
    newElement.className = 'child-element';

    // Adiciona o novo elemento como filho do elemento pai
    parentElement.appendChild(newElement);
    console.log('Novo elemento filho adicionado com sucesso!');
} else {
    console.error('Elemento pai não encontrado!');
}
```

---

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

### Exemplo de Uso para Estruturas de Tabela

Para uso em tabelas, você pode adaptar qualquer exemplo acima. Por exemplo:

**Adicionar uma Linha Depois de Outra Linha:**

```javascript
// Seleciona a linha de referência
const referenceRow = document.getElementById('example_row');
if (referenceRow) {
    // Cria uma nova linha
    const newRow = document.createElement('tr');
    newRow.innerHTML = `
        <td>Novo ID</td>
        <td>Nome Exemplo</td>
        <td>Usuário Exemplo</td>
        <td>Nível Exemplo</td>
        <td>Ação</td>
    `;

    // Insere a nova linha após a linha de referência
    referenceRow.parentNode.insertBefore(newRow, referenceRow.nextSibling);
    console.log('Nova linha adicionada com sucesso!');
} else {
    console.error('Linha de referência não encontrada!');
}
```

Para adicionar dinamicamente uma linha nessa tabela, precisamos criar um novo elemento `<tr>` e preencher suas colunas (`<td>` e `<th>`) com os dados fornecidos. O código ajustado para adicionar uma linha à tabela seria o seguinte:

### Script atualizado:
```jsx
// Seleciona o elemento de referência
const referenceElement = document.getElementById('test_table_admins');
if (referenceElement) {
    // Cria um novo elemento de linha (<tr>)
    const newRow = document.createElement('tr');
    
    // Cria as colunas da linha (<td> e <th>)
    const rowContent = `
        <td>99</td>
        <td>a</td>
        <td>b</td>
        <td>c</td>
        <th>d</th>
    `;

    // Adiciona o conteúdo às células da linha
    newRow.innerHTML = rowContent;

    // Insere a nova linha no final do corpo da tabela
    referenceElement.appendChild(newRow);

    console.log('Nova linha adicionada à tabela!');
} else {
    console.error('Tabela não encontrada!');
}
```

### Explicação do código:

1. **Seleciona o elemento de referência**:
   - O elemento `test_table_admins` é o `<tbody>` da tabela, onde as linhas estão sendo geradas dinamicamente.

2. **Cria a linha `<tr>`**:
   - Utilizamos `document.createElement('tr')` para criar uma nova linha vazia.

3. **Preenche o conteúdo da linha**:
   - Com `newRow.innerHTML = rowContent`, definimos o conteúdo HTML das células dessa linha.

4. **Adiciona a nova linha à tabela**:
   - Usamos `referenceElement.appendChild(newRow)` para inserir a linha no final do corpo da tabela (`<tbody>`).

5. **Mensagem de sucesso ou erro**:
   - Caso a tabela (`<tbody>`) seja encontrada, adicionamos a linha; caso contrário, mostramos um erro no console.

### Resultado esperado:

Uma nova linha será adicionada ao final da tabela, com os valores fornecidos:

| ID  | Nome | Usuário | Nível | Ação |
|-----|------|---------|-------|------|
| 99  | a    | b       | c     | d    |

Se precisar adicionar a linha em uma posição específica, basta utilizar `insertBefore` em vez de `appendChild`.

Para adicionar a nova linha antes dos outros itens existentes na tabela, você pode usar o método `insertBefore`. No caso, você precisa adicionar a nova linha como o primeiro filho do `<tbody>` (`test_table_admins`). O código ajustado fica assim:

### Script atualizado:
```jsx
// Seleciona o elemento de referência
const referenceElement = document.getElementById('test_table_admins');
if (referenceElement) {
    // Cria um novo elemento de linha (<tr>)
    const newRow = document.createElement('tr');
    
    // Cria as colunas da linha (<td> e <th>)
    const rowContent = `
        <td>99</td>
        <td>a</td>
        <td>b</td>
        <td>c</td>
        <th>d</th>
    `;

    // Adiciona o conteúdo às células da linha
    newRow.innerHTML = rowContent;

    // Insere a nova linha antes do primeiro elemento do corpo da tabela
    const firstChild = referenceElement.firstChild;
    referenceElement.insertBefore(newRow, firstChild);

    console.log('Nova linha adicionada antes das outras!');
} else {
    console.error('Tabela não encontrada!');
}
```

### Alterações feitas:

1. **Identificar o primeiro filho do `<tbody>`**:
   - Usamos `referenceElement.firstChild` para capturar o primeiro elemento existente dentro de `<tbody>`.

2. **Adicionar antes do primeiro filho**:
   - O método `insertBefore(newRow, firstChild)` insere a nova linha (`newRow`) antes do primeiro elemento (`firstChild`).

### Resultado:

Agora, a nova linha será adicionada como a primeira linha dentro do `<tbody>`, aparecendo antes de todos os itens existentes na tabela. 

Se precisar de mais ajustes ou tiver dúvidas, é só perguntar! 😊

---

Esses exemplos são altamente reutilizáveis e podem ser adaptados para diferentes cenários. Se precisar de mais adaptações ou esclarecimentos, é só pedir! 😊

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Manipulação Dinâmica do Título da Página com JavaScript

Aqui está um pequeno script JavaScript que altera dinamicamente o conteúdo da tag `<title>` de uma página:

### Script JavaScript para mudar o título da página

```javascript
function changePageTitle(newTitle) {
    document.title = newTitle;
}

// Exemplo de uso
changePageTitle("Novo Título da Página");
```

### Como usar:
1. Copie o script acima.
2. Insira-o no seu arquivo JavaScript ou diretamente em uma tag `<script>` no HTML.
3. Substitua `"Novo Título da Página"` pelo título que deseja aplicar.

### Aplicação em uma Página HTML

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Título da página</title>
</head>
<body>
    <h1>Bem-vindo à página</h1>
    <button onclick="changePageTitle('Título atualizado!')">Mudar Título</button>

    <script>
        function changePageTitle(newTitle) {
            document.title = newTitle;
        }
    </script>
</body>
</html>
```

### O que acontece:
1. Inicialmente, o título da página será `Título da página`.
2. Quando você clicar no botão, o título será alterado para `Título atualizado!`.

Essa é uma abordagem simples, mas poderosa, para dinamicamente alterar o título da página.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Função simples

Quando a função é acionada a partir de um click do usuário, é recomendável colocar o prefix `handle` e em seguida o nome de sua função em `CamelCase`, onde é uma denominação em inglês para a prática de escrever as palavras compostas ou frases, onde cada palavra é iniciada com maiúsculas e unidas sem espaços. Exemplo: `handleYourFunction() {...}`.

```jsx
function handleYourFunction() {
    alert('Helo World!');
};
```

Outra forma em uma constante:

```jsx
const handleYourFunction = () => {
    alert('Helo World!');
};
```

Sua função pode ser executada por exemplo, em um elemento HTML escrita da seguinte forma na propriedade `onClick={}`:

```jsx
 onClick={handleYourFunction}
```

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Preenchimento Automático de Formulários com React: Manipulação de Campos de Texto, Select, Radiobutton e Checkbox

Aqui está um exemplo de código em JavaScript JSX que pode ser usado em um componente de formulário para preencher automaticamente diferentes tipos de campos (como `text`, `textarea`, `select`, `radiobutton`, e `checkbox`) ao clicar em um link.

```jsx
import React, { useState } from 'react';

const FormularioAutoPreencher = () => {
  const [formData, setFormData] = useState({
    campoTexto: '',
    campoTextarea: '',
    campoSelect: '',
    campoRadio: '',
    campoCheckbox1: false,
    campoCheckbox2: false,
  });

  const preencherCampos = () => {
    setFormData({
      campoTexto: 'Exemplo de texto preenchido',
      campoTextarea: 'Texto preenchido automaticamente na textarea.',
      campoSelect: 'opcao2',
      campoRadio: 'opcao1',
      campoCheckbox1: true,
      campoCheckbox2: true,
    });
  };

  const handleChange = (e) => {
    const { name, value, type, checked } = e.target;
    setFormData((prevState) => ({
      ...prevState,
      [name]: type === 'checkbox' ? checked : value,
    }));
  };

  return (
    <div>
      <h2>Formulário de Exemplo</h2>
      
      <div>
        <label>Campo de Texto:</label>
        <input 
          type="text" 
          name="campoTexto" 
          value={formData.campoTexto} 
          onChange={handleChange} 
        />
      </div>

      <div>
        <label>Textarea:</label>
        <textarea 
          name="campoTextarea" 
          value={formData.campoTextarea} 
          onChange={handleChange} 
        />
      </div>

      <div>
        <label>Seleção:</label>
        <select 
          name="campoSelect" 
          value={formData.campoSelect} 
          onChange={handleChange}
        >
          <option value="">Selecione uma opção</option>
          <option value="opcao1">Opção 1</option>
          <option value="opcao2">Opção 2</option>
          <option value="opcao3">Opção 3</option>
        </select>
      </div>

      <div>
        <label>Radiobutton:</label>
        <input 
          type="radio" 
          name="campoRadio" 
          value="opcao1" 
          checked={formData.campoRadio === 'opcao1'} 
          onChange={handleChange} 
        />
        Opção 1
        <input 
          type="radio" 
          name="campoRadio" 
          value="opcao2" 
          checked={formData.campoRadio === 'opcao2'} 
          onChange={handleChange} 
        />
        Opção 2
      </div>

      <div>
        <label>Checkbox 1:</label>
        <input 
          type="checkbox" 
          name="campoCheckbox1" 
          checked={formData.campoCheckbox1} 
          onChange={handleChange} 
        />
      </div>

      <div>
        <label>Checkbox 2:</label>
        <input 
          type="checkbox" 
          name="campoCheckbox2" 
          checked={formData.campoCheckbox2} 
          onChange={handleChange} 
        />
      </div>

      <button type="button" onClick={preencherCampos}>
        Preencher Campos
      </button>
    </div>
  );
};

export default FormularioAutoPreencher;
```

### Explicação:

- **Estado Inicial (`formData`)**: O estado é utilizado para armazenar os valores dos campos do formulário. Cada campo possui seu próprio valor inicial.
  
- **Função `preencherCampos`**: Ao clicar no botão, essa função atualiza o estado com valores predefinidos, preenchendo automaticamente os campos de texto, `textarea`, `select`, `radiobutton` e `checkbox`.

- **Função `handleChange`**: Essa função lida com as mudanças nos campos do formulário, atualizando o estado conforme o usuário interage com o formulário.

### Comportamento:
- O campo de texto (`input type="text"`) será preenchido com "Exemplo de texto preenchido".
- A `textarea` será preenchida com "Texto preenchido automaticamente na textarea.".
- O `select` irá selecionar "Opção 2".
- O radiobutton "Opção 1" será marcado.
- Os dois checkboxes serão marcados (`checked`).

Isso pode ser expandido para mais campos ou comportamentos adicionais conforme a necessidade!

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Modularização de Funções de Preenchimento Automático de Formulários em React com Importação Externa

Sim, a função de preenchimento automático pode ser movida para um arquivo separado e importada para dentro do componente, onde pode ser acionada através de um evento `onClick`.

Aqui está um exemplo de como você pode organizar isso:

### 1. **Criar a função em um arquivo separado**

Você pode criar um arquivo chamado `preencherCampos.js` com a função que retorna os dados preenchidos:

```javascript
// preencherCampos.js
export const preencherCampos = () => {
  return {
    campoTexto: 'Exemplo de texto preenchido',
    campoTextarea: 'Texto preenchido automaticamente na textarea.',
    campoSelect: 'opcao2',
    campoRadio: 'opcao1',
    campoCheckbox1: true,
    campoCheckbox2: true,
  };
};
```

### 2. **Importar e utilizar no componente**

Agora, no seu componente principal, você pode importar essa função e usá-la no evento `onClick`.

```jsx
import React, { useState } from 'react';
import { preencherCampos } from './preencherCampos'; // Importando a função

const FormularioAutoPreencher = () => {
  const [formData, setFormData] = useState({
    campoTexto: '',
    campoTextarea: '',
    campoSelect: '',
    campoRadio: '',
    campoCheckbox1: false,
    campoCheckbox2: false,
  });

  const handlePreencherCampos = () => {
    const dadosPreenchidos = preencherCampos(); // Usando a função importada
    setFormData(dadosPreenchidos); // Atualizando o estado com os dados preenchidos
  };

  const handleChange = (e) => {
    const { name, value, type, checked } = e.target;
    setFormData((prevState) => ({
      ...prevState,
      [name]: type === 'checkbox' ? checked : value,
    }));
  };

  return (
    <div>
      <h2>Formulário de Exemplo</h2>
      
      <div>
        <label>Campo de Texto:</label>
        <input 
          type="text" 
          name="campoTexto" 
          value={formData.campoTexto} 
          onChange={handleChange} 
        />
      </div>

      <div>
        <label>Textarea:</label>
        <textarea 
          name="campoTextarea" 
          value={formData.campoTextarea} 
          onChange={handleChange} 
        />
      </div>

      <div>
        <label>Seleção:</label>
        <select 
          name="campoSelect" 
          value={formData.campoSelect} 
          onChange={handleChange}
        >
          <option value="">Selecione uma opção</option>
          <option value="opcao1">Opção 1</option>
          <option value="opcao2">Opção 2</option>
          <option value="opcao3">Opção 3</option>
        </select>
      </div>

      <div>
        <label>Radiobutton:</label>
        <input 
          type="radio" 
          name="campoRadio" 
          value="opcao1" 
          checked={formData.campoRadio === 'opcao1'} 
          onChange={handleChange} 
        />
        Opção 1
        <input 
          type="radio" 
          name="campoRadio" 
          value="opcao2" 
          checked={formData.campoRadio === 'opcao2'} 
          onChange={handleChange} 
        />
        Opção 2
      </div>

      <div>
        <label>Checkbox 1:</label>
        <input 
          type="checkbox" 
          name="campoCheckbox1" 
          checked={formData.campoCheckbox1} 
          onChange={handleChange} 
        />
      </div>

      <div>
        <label>Checkbox 2:</label>
        <input 
          type="checkbox" 
          name="campoCheckbox2" 
          checked={formData.campoCheckbox2} 
          onChange={handleChange} 
        />
      </div>

      <button type="button" onClick={handlePreencherCampos}>
        Preencher Campos
      </button>
    </div>
  );
};

export default FormularioAutoPreencher;
```

### Explicação:

1. **Arquivo `preencherCampos.js`**:
   - Ele contém apenas a função `preencherCampos`, que retorna os valores para serem preenchidos no formulário.

2. **Componente Principal (`FormularioAutoPreencher`)**:
   - Importa a função `preencherCampos`.
   - Ao clicar no botão, a função `handlePreencherCampos` é chamada, que utiliza a função `preencherCampos` para obter os valores e, em seguida, atualiza o estado `formData` com esses valores.

### Vantagens dessa abordagem:
- **Reutilizável**: A função de preenchimento automático está separada e pode ser facilmente reutilizada em outros componentes ou módulos.
- **Organização**: Deixa o código mais organizado, separando a lógica de preenchimento da interface do componente.

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Exemplo de Adição de Evento de Clique em JavaScript

O código abaixo seleciona um elemento com o id "myButton" e adiciona um ouvinte de evento para exibir um alerta quando o botão for clicado.

> Aqui está o código reescrito em sintaxe JavaScript:

```javascript
const myButton = document.querySelector('#myButton');

myButton.addEventListener("click", function() {
    alert("Hello World!");
});
```

Esse código JavaScript executa as seguintes ações:

1. Ele seleciona um elemento HTML com o atributo `id` igual a "myButton" usando o método `document.querySelector()`. Esse método permite selecionar elementos DOM usando seletores CSS.

2. Em seguida, ele adiciona um ouvinte de evento ao elemento selecionado. O evento específico é "click", o que significa que o código será executado quando o botão for clicado.

3. Quando o botão é clicado, a função anônima passada para `addEventListener` é ativada. Nesse caso, a função simplesmente exibe um alerta com a mensagem "Hello World!".

Em resumo, esse código seleciona um botão com o id "myButton" e adiciona um ouvinte de evento para exibir um alerta "Hello World!" sempre que o botão for clicado.

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Passar uma propriedade de um elemento para uma arrow function

Para executar uma arrow function que recebe a propriedade de um elemento quando um evento onClick é disparado, você pode definir a arrow function como uma função que recebe o evento e o elemento como seus parâmetros, e em seguida passá-la para a propriedade onClick do elemento.

Por exemplo, suponha que você tenha um botão com um id definido e deseja executar uma arrow function que recebe o id do botão quando ele é clicado. Você pode fazer o seguinte:

```jsx
// Evento do onClick={}
const handleClick = (event, id) => {
    console.log(`O evento do onClick no botão com o valor ${id} definido no segundo parâmentro arrow function handleClick() foi clicado.`);
};
```

Neste exemplo, a arrow function handleClick é definida para receber o evento e o id do elemento como seus parâmetros. O seu componente renderiza um botão com o id definido e passa a arrow function handleClick para a propriedade onClick do botão, juntamente com o id do botão.

Quando o botão é clicado, a arrow function é executada com o evento e o id do botão como seus parâmetros, permitindo que você acesse a propriedade do elemento dentro da função.

```jsx
return <button onClick={(event) => handleClick(event, "123")}>Clique aqui</button>;
```

> O `onClick={}` envia o evento, e no segundo parâmetro de `handleClick(event, "123")` será definido o valor a ser enviado. O resultado deste exemplo é exibido no `console`.

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## PopUp com uma determinada URL passada via parâmetro

Para abrir uma popup com uma determinada URL em um projeto em ReactJS, você pode usar o seguinte código:

```jsx
// PopUp simples.
function openPopup(url) {
  window.open(url, 'popup', 'width=600,height=600');
}

// Exemplo de uso.
openPopup('https://www.google.com');
```

Neste exemplo, a função `openPopup` recebe uma URL como parâmetro e utiliza o método `window.open` para abrir uma nova janela com a URL especificada. O segundo parâmetro da função `window.open` define o nome da janela (no caso, "popup"), e o terceiro parâmetro especifica as dimensões da janela. Você pode ajustar o tamanho de acordo com suas necessidades.

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## PopUp passando além de uma URL, dimensões e centralizada

Você pode usar o método `window.open()` do JavaScript para abrir uma nova janela popup com uma determinada URL e dimensões. Para centralizar a janela na tela, você pode usar as dimensões da tela e as dimensões da janela para calcular a posição do canto superior esquerdo da janela. Aqui está um exemplo de código que faz isso:

```jsx
// PopUp simples centralizada.
function openPopup(url, width, height) {
  // Calcular a posição do canto superior esquerdo da janela para centralizá-la.
  const left = (screen.width - width) / 2;
  const top = (screen.height - height) / 2;

  // Abrir a janela popup com a URL e dimensões especificadas.
  window.open(url, "", `width=${width}, height=${height}, left=${left}, top=${top}`);
}
```

Para usar essa função em seu projeto React, basta chamá-la em algum evento de um elemento da interface do usuário, por exemplo:

```jsx
<button onClick={() => openPopup("https://www.google.com", 800, 600)}>Abrir popup</button>
```

Este exemplo criará um botão que, quando clicado, abrirá uma janela popup com a URL "https://www.google.com" e as dimensões 800x600, centralizadas na tela.

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Contar número de caracteres de uma string

Esta função recebe a o valor da string, conta os caracteres e retorna o valor referente à quantidade de caracteres.

```jsx
// Contar caracteres
function countCharacters(string) {
    const numberOfCharacters = string.length;
    return numberOfCharacters;
}
// Exemplo: countCharacters("Seu texto aqui.")
```

Para contar o número de caracteres de uma string em ReactJS, você pode simplesmente usar a propriedade `length` da string. Por exemplo, suponha que você tenha uma variável chamada "texto" que contém o texto que você deseja contar os caracteres, você pode obter o número de caracteres usando o seguinte código:

```jsx
const texto = "Exemplo de texto";
const numeroCaracteres = texto.length;
console.log(numeroCaracteres); // 16
```

Neste exemplo, a constante `numeroCaracteres` vai conter o número de caracteres do texto, que no caso é 16.

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Capitalizar nomes (ótimo para cadastro de pessoas)

Você pode criar uma nova função em seu componente React que capitalize as letras da string. Segue um exemplo:

```jsx
// Capitalizando as palavras.
function capitalize(str) {
  return str.replace(/\b\w/g, function (match) {
    return match.toUpperCase();
  });
}
```

Em seguida, você pode utilizá-la no seu campo de formulário da seguinte forma:

```jsx
<Form.Control
  type="text"
  size="sm"
  placeholder="Nome completo do cliente"
  value={full_name}
  onChange={(e) => setFull_name(capitalize(e.target.value))}
  ref={full_nameInputRef}
/>
```

Dessa forma, a função `capitalize()` será chamada sempre que houver uma mudança no valor do campo de formulário e a string digitada será capitalizada.

> ( ! ) Quero que ignore as seguintes palavras: "de", "do", "da", "dos", "uma", "umas", "um", "uns".

Para ignorar as palavras especificadas, você pode verificar se cada palavra está na lista de palavras ignoradas antes de capitalizá-la. Aqui está uma possível implementação da função:

```jsx
// Capitalizando as palavras.
function capitalizeWords(value) {
  const ignoredWords = ['de', 'do', 'da', 'dos', 'uma', 'umas', 'um', 'uns'];
  const words = value.split(' ');
  const capitalizedWords = words.map((word) => {
    if (ignoredWords.includes(word.toLowerCase())) {
      return word.toLowerCase();
    } else {
      return word.charAt(0).toUpperCase() + word.slice(1).toLowerCase();
    }
  });
  return capitalizedWords.join(' ');
}
```

Você pode usar essa função `capitalizeWords()` no seu componente React assim:

```jsx
<Form.Control
  type="text"
  size="sm"
  placeholder="Nome completo do cliente"
  value={full_name}
  onChange={(e) => setFull_name(capitalizeWords(e.target.value))}
  ref={full_nameInputRef}
/>
```

Para utilizar a função `capitalizeWords` em um elemento HTML, basta chamá-la passando a string desejada como parâmetro e envolver o resultado em um elemento que deseja aplicá-lo, como um `<h1>` por exemplo. Veja um exemplo:

```jsx
<h1>{capitalizeWords('este é um exemplo de título capitalizado')}</h1>
```

Isso irá renderizar o texto "Este é um Exemplo de Título Capitalizado" dentro de um elemento `<h1>`.

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Capitalizar a primeira palavra de um parágrafo com exceções em ReactJS

É possível usar um array para facilitar a inclusão de palavras em exceções no texto capitalizado. Aqui está o código que utiliza um array de palavras excepcionais:

```jsx
// Capitalizar a primeira palavra de um parágrafo com exceções.
function capitalizeFirstWord(text) {
  const lowercaseText = text.toLowerCase();
  const words = lowercaseText.split(' ');

  const exceptions = ['educação', 'maranhão'];

  const capitalizedWords = words.map((word, index) => {
    if (index === 0) {
      return word.charAt(0).toUpperCase() + word.slice(1);
    } else if (exceptions.includes(word)) {
      return word.toUpperCase();
    } else {
      return word;
    }
  });
  const capitalizedText = capitalizedWords.join(' ');
  return capitalizedText;
}

console.log(capitalizeFirstWord(yourParagraph));
```

As palavras excepcionais estão armazenadas no array `exceptions`. O código verifica se a palavra está contida nesse array usando `exceptions.includes(word)`. Dessa forma, você pode adicionar ou remover palavras no array `exceptions` de acordo com suas necessidades. O resultado continuará sendo apenas a capitalização da primeira palavra e a preservação das palavras excepcionais.

Este código em ReactJS tem como objetivo capitalizar a primeira palavra de um parágrafo, enquanto mantém as palavras em minúsculas, exceto por algumas exceções. Aqui está uma descrição passo a passo do código:

1. É definida a função `capitalizeFirstWord` que recebe um texto como parâmetro.
2. O texto é convertido para minúsculas usando o método `toLowerCase()`.
3. O texto é dividido em palavras usando o método `split(' ')`, que retorna um array de palavras.
4. É definido um array chamado `exceptions` que contém as palavras excepcionais que não serão convertidas para minúsculas.
5. O array de palavras é percorrido usando o método `map()`.
6. Para a primeira palavra (índice 0), a primeira letra é capitalizada usando `word.charAt(0).toUpperCase() + word.slice(1)`, que retorna a primeira letra em maiúscula concatenada com o restante da palavra em minúscula.
7. Para as palavras subsequentes, é verificado se a palavra está presente no array `exceptions` usando `exceptions.includes(word)`.
8. Se a palavra estiver no array de exceções, ela é mantida em maiúscula.
9. Caso contrário, a palavra é mantida em minúscula.
10. As palavras modificadas são armazenadas em um novo array chamado `capitalizedWords`.
11. O array `capitalizedWords` é juntado novamente em um texto usando o método `join(' ')`.
12. O texto final com a primeira palavra capitalizada e as exceções mantidas é retornado pela função `capitalizeFirstWord`.
13. No componente `App`, é definido um parágrafo como exemplo, onde todas as palavras estão em letras maiúsculas.
14. A função `capitalizeFirstWord` é chamada com o parágrafo como argumento, retornando o parágrafo modificado.
15. O parágrafo modificado é renderizado em um elemento `<p>`.

Esse código pode ser usado como referência para capitalizar a primeira palavra de um parágrafo e lidar com exceções de palavras específicas em seu projeto ReactJS.

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Transformando meses de 01 a 12 em Janeiro a Dezembro

Você pode criar uma função que receba o número do mês como argumento e retorne o nome do mês correspondente. Veja um exemplo:

```jsx
// Transformando meses de 01 a 12 em Janeiro a Dezembro
function getMonthName(month) {
  const monthNames = [
    "Janeiro", "Fevereiro", "Março", "Abril", 
    "Maio", "Junho", "Julho", "Agosto", 
    "Setembro", "Outubro", "Novembro", "Dezembro"
  ];
  return monthNames[month - 1];
}
```

Nesse exemplo, a função `getMonthName` recebe um número de mês (de 1 a 12) como argumento e retorna o nome do mês correspondente. O array `monthNames` contém os nomes dos meses em ordem, e a função usa o número do mês como índice para obter o nome correspondente do array. Note que a função subtrai 1 do número do mês, já que os arrays em JavaScript são indexados a partir de zero.

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Como Rolar a Barra de Rotação para o Topo de uma Página ao Carregá-la com JavaScript

Sim, você pode usar JavaScript para rolar a barra de rolagem para o topo da página ao carregar a página. Você pode fazer isso adicionando um código simples ao seu componente da página "single". Aqui está um exemplo de como fazer isso:

```javascript
import React, { useEffect } from 'react';

function SinglePage() {

  // Função para rolar a página para o topo.
  const scrollToTop = () => {
    window.scrollTo({
      top: 0,
      behavior: 'smooth' // Você pode remover isso se quiser uma rolagem instantânea.
    });
  };
  // Rolar para o topo quando o componente for montado.
  useEffect(() => {
    scrollToTop();
  }, []);

  // Seu conteúdo da página "single" aqui.
  return (
    <div>
      {/* Conteúdo da sua página */}
    </div>
  );
}

export default SinglePage;
```

Neste exemplo, estamos usando o `useEffect` para chamar a função `scrollToTop` quando o componente é montado. A função `scrollToTop` usa `window.scrollTo` para rolar a página para o topo. Você pode ajustar o valor de `top` para controlar a posição exata para a qual deseja rolar.

Além disso, estamos usando `behavior: 'smooth'` para uma rolagem suave. Se você preferir uma rolagem instantânea, basta remover essa opção.

Isso fará com que a página role para o topo sempre que a página "single" for carregada. Certifique-se de incorporar isso ao seu componente "single" existente.

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Removendo Tags HTML em ReactJS: Uma Abordagem Simples e Segura

Sim, você pode usar uma expressão regular (regex) para remover todas as tags HTML de uma string em ReactJS. Você pode criar uma função utilitária para fazer isso. Aqui está um exemplo de como você pode fazer isso:

```jsx
import React from 'react';

// Removendo Tags HTML.
const removeHtmlTags = (htmlString) => {
  const regex = /<[^>]*>/g;
  return htmlString.replace(regex, '');
};

const YourComponent = () => {
  const htmlString = '<p>Seu texto com tags HTML.</p>';
  const textWithoutHtml = removeHtmlTags(htmlString);

  return (
    <div>
      <p>Texto com tags HTML:</p>
      <div dangerouslySetInnerHTML={{ __html: htmlString }} />
      <p>Texto sem tags HTML:</p>
      <div>{textWithoutHtml}</div>
    </div>
  );
};

export default YourComponent;
```

Neste exemplo, a função `removeHtmlTags` aceita uma string com tags HTML e usa uma regex para remover todas as ocorrências de tags HTML. Em seguida, você pode exibir a versão sem tags HTML no seu componente React.

Por favor, note que ao usar `dangerouslySetInnerHTML`, você está inserindo HTML diretamente no DOM, o que pode ser arriscado se o conteúdo não for confiável. Certifique-se de que o conteúdo que você está exibindo é seguro para evitar ataques XSS (Cross-Site Scripting).

<!-- Botões de navegação -->
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Removendo Tags HTML com ReactJS: Uma Abordagem Simples e Elegante

Sim, você pode usar uma função em ReactJS para remover todas as tags HTML de um texto, deixando apenas o texto. Uma maneira de fazer isso é usando uma expressão regular (regex) para coincidir com todas as tags HTML e removê-las. Aqui está um exemplo de como você pode fazer isso:

```jsx
// Removendo Tags HTML.
function removeHtmlTags(textWithHtml) {
  const regex = /<[^>]+>/g;
  return textWithHtml.replace(regex, '');
}

const textWithHtml = "<p>Este é um <strong>exemplo</strong> de texto com tags HTML.</p>";
const textWithoutHtml = removeHtmlTags(textWithHtml);

console.log(textWithoutHtml);
```

A função `removeHtmlTags` recebe um texto que contém tags HTML e usa a expressão regular `<[^>]+>` para encontrar todas as tags e, em seguida, usa o método `replace` para substituir essas tags por uma string vazia, efetivamente removendo-as.

Lembre-se de que essa abordagem remove todas as tags HTML, incluindo qualquer conteúdo que possa estar entre as tags. Certifique-se de que isso seja o que você deseja para o seu caso específico.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Função de Formatação de Data e Hora com Ajuste de Horas

Claro! Segue um modelo genérico que você pode guardar como referência. Ele recebe três parâmetros: data (`dateStr`), hora (`timeStr`) e horas a serem adicionadas (`hours`). Caso não receba `hours`, ele utiliza **0** como valor padrão.

```jsx
// formatDate.js

import { format, parseISO, addHours } from 'date-fns';

/**
 * Formata data e hora, e adiciona um número específico de horas à data/hora informadas.
 * 
 * @param {string} dateStr - String com a data em formato ISO (ex.: "2025-12-31").
 * @param {string} timeStr - String com a hora em formato ISO (ex.: "2025-12-31T10:00:00").
 * @param {number} [hours=0] - Quantidade de horas que você deseja adicionar à data/hora.
 * @returns {string} Retorna a data/hora final formatada no padrão "Dia dd/MM/yyyy às HH:mm:ss".
 */
function formatDate(dateStr, timeStr, hours = 0) {
  // 1. Se não houver dados suficientes, retorna uma string vazia (ou algum fallback)
  if (!dateStr || !timeStr) {
    return '';
  }

  try {
    // 2. Faz o parse das strings para objeto Date
    const parsedDate = parseISO(dateStr);
    const parsedTime = parseISO(timeStr);

    // 3. Verifica se são datas válidas
    if (isNaN(parsedDate) || isNaN(parsedTime)) {
      return '';
    }

    // 4. Combina data e hora em um único objeto Date
    const dateWithTime = new Date(parsedDate);
    dateWithTime.setHours(parsedTime.getHours());
    dateWithTime.setMinutes(parsedTime.getMinutes());
    dateWithTime.setSeconds(parsedTime.getSeconds());

    // 5. Adiciona as horas definidas (default = 0)
    const finalDate = addHours(dateWithTime, hours);

    // 6. Formata data e hora
    const formattedDate = format(finalDate, 'dd/MM/yyyy');
    const formattedTime = format(finalDate, 'HH:mm:ss');

    // 7. Retorna a string formatada
    return `${formattedDate} às ${formattedTime}`;
  } catch (error) {
    // Em caso de erro no parse, retorne algo seguro
    return '';
  }
}

export default formatDate;
```

### Exemplo de uso

```js
import formatDate from './formatDate';

const dataExemplo1 = formatDate('2025-12-31', '2025-12-31T10:00:00');
console.log(dataExemplo1);
// Saída: "Dia 31/12/2025 às 10:00:00" (caso não seja passado o parâmetro hours, soma-se 0)

const dataExemplo2 = formatDate('2025-12-31', '2025-12-31T10:00:00', 27);
console.log(dataExemplo2);
// Saída: "Dia 01/01/2026 às 13:00:00" (27 horas a mais)
```

---

> ( i ) Dica!

Assim, você tem um modelo genérico para formatar data e hora, com a opção de adicionar um número variável de horas.

Uma prática bastante comum é criar uma pasta **"utils"** ou **"helpers"** dentro de `src` para guardar funções e scripts genéricos em `.js` que não pertencem diretamente a um componente específico. Esses nomes deixam claro que o diretório contém recursos utilitários/reutilizáveis. 

Por exemplo:
```bash
/src
  ├── assets
  ├── components
  ├── contexts
  ├── css
  ├── DataTables
  ├── server
  ├── utils  ← novo diretório sugerido
  │    └── formatDate.js
  ├── App.jsx
  ├── AppRoutes.jsx
  ├── Desktop.jsx
  ├── global.css
  ├── Home.jsx
  ├── Icon.jsx
  ├── index.js
  ├── main.jsx
  ├── Taskbar.jsx
  └── Window.jsx
```

Dessa forma, **`formatDate.js`** (e quaisquer outras funções auxiliares) ficariam num local mais organizado e significativo do ponto de vista da arquitetura do projeto.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Componente React para Exibição de Localização com Google Maps

Este exemplo demonstra como incorporar um mapa do Google Maps em um componente React utilizando um `iframe`. A latitude e a longitude da localização desejada são passadas dinamicamente na URL.

### Código

```jsx
// Importação de estilos, se necessário
import styles from './YourStyles.module.css';

// Coordenadas da localização da empresa
const companyLatitude = "-5.078706";
const companyLongitude = "-42.800151";

const CompanyLocation = (
  <iframe
    src={`https://www.google.com/maps?q=${companyLatitude},${companyLongitude}&hl=pt&z=15&output=embed`}
    allowFullScreen=""
    loading="lazy"
    referrerPolicy="no-referrer-when-downgrade"
    className={styles.iframe}
  ></iframe>
);

export default CompanyLocation;
```

### Explicação

1. **Coordenadas da localização**: Substitua `companyLatitude` e `companyLongitude` pelas coordenadas da localização que você deseja exibir no mapa.
2. **Parâmetros da URL**:
   - `hl=pt`: Define o idioma como português.
   - `z=15`: Define o nível de zoom no mapa.
   - `output=embed`: Gera a URL no formato de incorporação.
3. **Estilização**: Use a classe CSS `iframe` para ajustar a aparência do mapa, conforme definido no arquivo de estilos.
4. **Propriedades do `iframe`**:
   - `allowFullScreen`: Permite que o mapa seja exibido em tela cheia.
   - `loading="lazy"`: Melhora o desempenho ao carregar o mapa apenas quando necessário.
   - `referrerPolicy`: Configura a política de referenciadores para melhorar a segurança.

### Observação

- Certifique-se de incluir os estilos personalizados no arquivo `YourStyles.module.css` (ou similar). Exemplo de estilo básico para o iframe:

```css
.iframe {
  width: 100%;
  height: 400px;
  border: none;
}
```

Agora você pode reutilizar este componente para exibir localizações com o Google Maps em seus projetos React.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Componentes Fixos e Posicionados no Layout com CSS

Aqui está um exemplo de como implementar os quadros descritos utilizando **React** e **CSS**. O código atende aos requisitos de estilo, posicionamento e flexibilidade no conteúdo.

### Estrutura do Componente React

```jsx
import React from 'react';
import './FloatingBoxes.css';

const FloatingBoxes = () => {
  return (
    <div className="box-container">
      <div className="box">Conteúdo do Quadro 1</div>
      <div className="box">Conteúdo do Quadro 2</div>
      <div className="box">Conteúdo do Quadro 3</div>
    </div>
  );
};

export default FloatingBoxes;
```

### Estilos CSS (FloatingBoxes.css)

```css
/* Estilos principais */
.box-container {
  position: fixed;
  bottom: 10px;
  right: 10px;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  z-index: 0;
}

/* Estilos para cada quadro */
.box {
  width: 165px;
  min-height: 80px;
  margin-bottom: 5px;
  background-color: #f0f0f0;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 10px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  overflow-wrap: break-word;
  word-wrap: break-word;
}

/* Remove margem do último quadro */
.box:last-child {
  margin-bottom: 0;
}
```

### Funcionamento e Explicação

1. **Container fixo no canto inferior direito**: A `div` principal (`box-container`) é posicionada no canto inferior direito usando `position: fixed` com `bottom: 10px` e `right: 10px`.

2. **Quadros flexíveis**: Cada quadro (`.box`) possui largura fixa (`165px`), altura mínima (`80px`) e uma margem inferior de `5px` entre eles. Essa margem é aplicada automaticamente, exceto no último quadro.

3. **Ajuste de altura automático**: Graças à propriedade `min-height`, os quadros expandem automaticamente conforme o conteúdo cresce.

4. **Estilo reutilizável**: Para adicionar novos quadros, basta duplicar a `div` com a classe `box` no componente `FloatingBoxes`.

### Resultado Esperado

Os quadros aparecerão um embaixo do outro no canto inferior direito da página. Quando um dos quadros tiver conteúdo maior, ele se ajustará automaticamente sem sobreposição.

### Exemplo de Uso

Caso deseje adicionar mais quadros, basta copiar e colar no componente:

```jsx
<div className="box">Novo Quadro</div>
```

### Personalização

Se quiser ajustar o espaçamento ou cores:
- Modifique `margin-bottom` para ajustar o espaçamento entre os quadros.
- Altere `background-color` e `border` para personalizar o estilo visual dos quadros.

Pronto! 🚀 Este é um código simples e eficaz que cumpre com os requisitos descritos.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Organização de Terminais: Fluxo de Trabalho Produtivo

Para manter a produtividade e organização no desenvolvimento do projeto, utilizo uma estrutura de **três terminais separados**, cada um com uma responsabilidade específica. Essa divisão facilita a execução de tarefas simultâneas e evita confusões ao rodar o sistema. A organização é a seguinte:

| Terminais no VSCode                                          | Informações                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![Terminais](../Backend_com_Prisma_e_Node.js/images/Terminals.png) | A imagem ilustra como organizo e utilizo os terminais de forma separada em projetos que envolvem Backend e Frontend, com o objetivo de manter a estrutura organizada e otimizar a produtividade no desenvolvimento. |

> ( i ) Marcos Auélio Rocha da Silva (Engenheiro de Software).
>
> *Ícones: "folder", "server" e "symbol-misc".*

1. **Terminal Geral (`bash SiSFloatBase`)**  
   
   - Este terminal é o ponto central para **instalar dependências** e executar comandos adicionais durante o desenvolvimento.  
   - Utilizo para instalar pacotes do **Node.js/React.js**, rodar scripts de teste e outras operações gerais do projeto.  
   - Exemplo de uso:
     ```bash
     npm install <pacote>
     npm run build
     ```
   
2. **Terminal Backend (`npm api`)**  
   - Este terminal é dedicado à execução do servidor **backend** do projeto.  
   - Utilizo para iniciar o servidor localmente e monitorar logs de requisições e erros.  
   - Comando comum:
     ```bash
     npm run dev
     ```

3. **Terminal Frontend (`npm frontend`)**  
   - Neste terminal, executo o servidor do **frontend**, garantindo que a interface esteja rodando corretamente.  
   - Uso para testes visuais, ver mudanças em tempo real e monitorar erros da aplicação React.  
   - Comando comum:
     ```bash
     npm start
     ```

---

### **Por que essa organização funciona?**  
- **Clareza**: Cada terminal tem uma responsabilidade única, evitando confusões durante o desenvolvimento.  
- **Produtividade**: Facilita o monitoramento em tempo real de logs e execução de comandos sem precisar alternar ou reiniciar processos.  
- **Eficiência**: Deixa o fluxo de trabalho mais ágil, pois consigo rodar o backend e o frontend ao mesmo tempo, enquanto instalo recursos no terminal principal.

---

Essa prática simples ajuda a manter o foco e organiza melhor as tarefas enquanto o projeto está em desenvolvimento. 🚀

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Recebendo e Usando Propriedades (`props`) em Componentes React

Este modelo explica como criar componentes React que recebem e utilizam propriedades (`props`), com exemplos em componentes funcionais, de classe e boas práticas para validação e tipagem.

---

### Componente Funcional

Para receber propriedades em um componente funcional, você pode desestruturar os `props` diretamente no argumento da função:

```jsx
const MeuComponente = ({ propriedade1, propriedade2 }) => {
  return (
    <div>
      <p>Propriedade 1: {propriedade1}</p>
      <p>Propriedade 2: {propriedade2}</p>
    </div>
  );
};
```

Se preferir, você também pode acessar os `props` diretamente sem desestruturá-los:

```jsx
const MeuComponente = (props) => {
  return (
    <div>
      <p>Propriedade 1: {props.propriedade1}</p>
      <p>Propriedade 2: {props.propriedade2}</p>
    </div>
  );
};
```

------

### Componente de Classe

Se estiver utilizando um componente de classe, as propriedades podem ser acessadas através de `this.props`:

```jsx
class MeuComponente extends React.Component {
  render() {
    const { propriedade1, propriedade2 } = this.props;
    return (
      <div>
        <p>Propriedade 1: {propriedade1}</p>
        <p>Propriedade 2: {propriedade2}</p>
      </div>
    );
  }
}
```

------

### Boas Práticas: Tipagem e Validação

#### Usando TypeScript

Se estiver utilizando TypeScript, defina a interface ou tipo dos `props` para maior segurança e clareza:

```tsx
interface MeuComponenteProps {
  propriedade1: string;
  propriedade2: number;
}

const MeuComponente: React.FC<MeuComponenteProps> = ({ propriedade1, propriedade2 }) => {
  return (
    <div>
      <p>Propriedade 1: {propriedade1}</p>
      <p>Propriedade 2: {propriedade2}</p>
    </div>
  );
};
```

#### Usando PropTypes

Se estiver utilizando JavaScript, valide os `props` com a biblioteca `prop-types`:

```jsx
import PropTypes from 'prop-types';

const MeuComponente = ({ propriedade1, propriedade2 }) => {
  return (
    <div>
      <p>Propriedade 1: {propriedade1}</p>
      <p>Propriedade 2: {propriedade2}</p>
    </div>
  );
};

MeuComponente.propTypes = {
  propriedade1: PropTypes.string.isRequired,
  propriedade2: PropTypes.number.isRequired,
};
```

------

### Exemplo de Uso

```jsx
const App = () => {
  return <MeuComponente propriedade1="Exemplo" propriedade2={42} />;
};
```

Com base nesse modelo, você pode criar componentes reutilizáveis e organizados, sempre garantindo clareza no recebimento e uso de `props`.

```
Agora você pode usar este modelo genérico em seus futuros projetos. 🚀
```

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Uso de ENUMs no Prisma ORM

Enums são úteis para definir um conjunto fixo de valores possíveis para um campo no banco de dados. No Prisma, os `enum` são definidos fora dos `model` e referenciados nos campos desejados.

### Exemplo genérico de enum com modelo Prisma

```prisma
// Definição do ENUM
enum Status {
  ACTIVE
  INACTIVE
  PENDING
}

// Modelo utilizando o ENUM
model User {
  id       Int     @id @default(autoincrement())
  name     String  @db.VarChar(255)
  email    String  @db.VarChar(255)
  status   Status
}
```

### Boas práticas

- Use `enum` quando os valores possíveis forem limitados e bem definidos.
- Enums facilitam a validação, garantindo que apenas valores válidos sejam inseridos no banco.
- No frontend, é possível usar os valores do enum para preencher selects ou filtros com segurança e consistência.

### Observações

- Após criar ou alterar um `enum`, sempre rode `npx prisma generate` e `npx prisma migrate dev` (ou `deploy`, se for produção) para aplicar as mudanças.
- Enums são especialmente úteis para campos como `status`, `tipo`, `categoria`, `sexo`, entre outros.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Integração de ENUM do Prisma com TypeScript

Ao definir um `enum` no Prisma, ele é automaticamente refletido no client TypeScript após executar `npx prisma generate`.

### Backend – Usando enum com segurança

Depois de gerar o client, o enum estará disponível como um tipo no Prisma Client:

```ts
import { Prisma, PrismaClient } from '@prisma/client'

const prisma = new PrismaClient()

async function createUser() {
  const user = await prisma.user.create({
    data: {
      name: 'João',
      email: 'joao@email.com',
      status: Prisma.Status.ACTIVE, // uso seguro do enum
    },
  })
}
```

Você também pode tipar parâmetros ou argumentos com o enum:

```ts
function isUserActive(status: Prisma.Status): boolean {
  return status === Prisma.Status.ACTIVE
}
```

### Frontend – Compartilhando enums com o client

Se você quiser usar o mesmo enum no frontend (ex: React), o Prisma **não expõe enums diretamente para o frontend**. Mas há duas boas abordagens:

#### 1. Criar um objeto/export manual

```ts
// shared/enums.ts
export const UserStatus = {
  ACTIVE: 'ACTIVE',
  INACTIVE: 'INACTIVE',
  PENDING: 'PENDING',
} as const

export type UserStatus = keyof typeof UserStatus
```

#### 2. Gerar dinamicamente com script (avançado)

Você pode criar um script para extrair os enums do Prisma e gerar arquivos para uso no frontend, garantindo consistência automática. (Se quiser esse script, posso gerar um exemplo.)

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Geração automática de enums Prisma para uso no frontend

### Objetivo

Extrair os enums definidos no schema do Prisma e gerar um arquivo TypeScript com eles para uso no frontend, mantendo consistência entre backend e frontend.

### Estrutura recomendada

```bash
.
├── prisma/
│   └── schema.prisma
├── scripts/
│   └── generate-enums.ts
├── shared/
│   └── enums.ts  ← será gerado automaticamente
├── backend/
├── frontend/
```

---

### 1. Script para gerar enums – `/scripts/generate-enums.ts`

```ts
import fs from 'fs'
import path from 'path'
import { getDMMF } from '@prisma/sdk'

async function generateEnums() {
  const schemaPath = path.resolve(__dirname, '../prisma/schema.prisma')
  const dmmf = await getDMMF({ datamodel: fs.readFileSync(schemaPath, 'utf-8') })

  const enums = dmmf.datamodel.enums
  const outputLines: string[] = []

  outputLines.push('// ESTE ARQUIVO É GERADO AUTOMATICAMENTE. NÃO EDITE MANUALMENTE.')
  outputLines.push('')
  
  enums.forEach((e) => {
    outputLines.push(`export const ${e.name} = {`)
    e.values.forEach((v) => {
      outputLines.push(`  ${v.name}: '${v.name}',`)
    })
    outputLines.push(`} as const\n`)
    outputLines.push(`export type ${e.name} = keyof typeof ${e.name}\n`)
  })

  const outputPath = path.resolve(__dirname, '../shared/enums.ts')
  fs.writeFileSync(outputPath, outputLines.join('\n'), 'utf-8')
  console.log('✅ Arquivo enums.ts gerado com sucesso!')
}

generateEnums().catch((err) => {
  console.error('Erro ao gerar enums:', err)
  process.exit(1)
})
```

---

### 2. Adicione script no `package.json`

```json
{
  "scripts": {
    "generate:enums": "ts-node scripts/generate-enums.ts"
  }
}
```

> Certifique-se de ter o `ts-node` instalado:  
> `npm install --save-dev ts-node @types/node @prisma/sdk`

---

### 3. Resultado esperado – `/shared/enums.ts`

```ts
// ESTE ARQUIVO É GERADO AUTOMATICAMENTE. NÃO EDITE MANUALMENTE.

export const Status = {
  ACTIVE: 'ACTIVE',
  INACTIVE: 'INACTIVE',
  PENDING: 'PENDING',
} as const

export type Status = keyof typeof Status
```

---

### Dica

Sempre que alterar seus enums no `schema.prisma`, execute:

```bash
npm run generate:enums
```

Ou automatize após `prisma generate` com:

```json
"scripts": {
  "postprisma:generate": "npm run generate:enums"
}
```

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Versão Avançada do Script de Geração de Enums

Vamos ampliar o script para torná-lo **mais flexível**, incluindo:

1. **Suporte a schemas localizados em subpastas**, usando `--schema` como argumento.
2. **Geração opcional de enums em JSON**, útil para frontend em outras stacks (ex: Vue, mobile, etc.).

### `/scripts/generate-enums.ts`

```ts
import fs from 'fs'
import path from 'path'
import { getDMMF } from '@prisma/sdk'

const args = process.argv.slice(2)
const schemaFlagIndex = args.indexOf('--schema')
const schemaPath = schemaFlagIndex !== -1 && args[schemaFlagIndex + 1]
  ? path.resolve(args[schemaFlagIndex + 1])
  : path.resolve(__dirname, '../prisma/schema.prisma')

const outputDir = path.resolve(__dirname, '../shared')
const tsOutput = path.join(outputDir, 'enums.ts')
const jsonOutput = path.join(outputDir, 'enums.json')

async function generateEnums() {
  const datamodel = fs.readFileSync(schemaPath, 'utf-8')
  const dmmf = await getDMMF({ datamodel })
  const enums = dmmf.datamodel.enums

  const tsLines: string[] = []
  const jsonObject: Record<string, string[]> = {}

  tsLines.push('// ESTE ARQUIVO É GERADO AUTOMATICAMENTE. NÃO EDITE MANUALMENTE.')
  tsLines.push('')

  enums.forEach((e) => {
    tsLines.push(`export const ${e.name} = {`)
    const values = e.values.map((v) => `'${v.name}'`)
    e.values.forEach((v) => {
      tsLines.push(`  ${v.name}: '${v.name}',`)
    })
    tsLines.push(`} as const\n`)
    tsLines.push(`export type ${e.name} = keyof typeof ${e.name}\n`)
    jsonObject[e.name] = e.values.map((v) => v.name)
  })

  if (!fs.existsSync(outputDir)) {
    fs.mkdirSync(outputDir)
  }

  fs.writeFileSync(tsOutput, tsLines.join('\n'), 'utf-8')
  fs.writeFileSync(jsonOutput, JSON.stringify(jsonObject, null, 2), 'utf-8')

  console.log('✅ Arquivos enums.ts e enums.json gerados com sucesso!')
}

generateEnums().catch((err) => {
  console.error('Erro ao gerar enums:', err)
  process.exit(1)
})
```

---

### Uso do script

#### Usando schema padrão:

```bash
npx ts-node scripts/generate-enums.ts
```

#### Usando schema em subpasta:

```bash
npx ts-node scripts/generate-enums.ts --schema ./apps/api/prisma/schema.prisma
```

---

### Resultado

#### `/shared/enums.ts` – Para uso TypeScript
#### `/shared/enums.json` – Para consumo genérico (frontend não-TypeScript, mobile, etc.)

```json
{
  "Status": ["ACTIVE", "INACTIVE", "PENDING"]
}
```

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Como consumir enums do Prisma no frontend

Aqui está como usar os enums gerados no frontend, tanto com o `.ts` (para projetos React com TypeScript), quanto com o `.json` (para React, Vue, mobile ou outras stacks).

### 1. Usando o arquivo `enums.ts` (React + TypeScript)

#### Exemplo: select com enum `Status`

```tsx
// frontend/components/StatusSelect.tsx
import React from 'react'
import { Status } from '../../shared/enums' // ajuste o caminho conforme sua estrutura

type Props = {
  value: keyof typeof Status
  onChange: (value: keyof typeof Status) => void
}

const StatusSelect: React.FC<Props> = ({ value, onChange }) => {
  return (
    <select value={value} onChange={(e) => onChange(e.target.value as keyof typeof Status)}>
      {Object.entries(Status).map(([key, label]) => (
        <option key={key} value={label}>
          {label}
        </option>
      ))}
    </select>
  )
}

export default StatusSelect
```

---

### 2. Usando o arquivo `enums.json` (React, Vue, mobile, etc.)

#### React com JavaScript ou TypeScript

```tsx
// frontend/components/StatusSelect.tsx
import React from 'react'
import enums from '../../shared/enums.json' // ajuste o caminho conforme sua estrutura

const StatusSelect = ({ value, onChange }) => {
  const statuses = enums.Status

  return (
    <select value={value} onChange={(e) => onChange(e.target.value)}>
      {statuses.map((status) => (
        <option key={status} value={status}>
          {status}
        </option>
      ))}
    </select>
  )
}

export default StatusSelect
```

#### Vue 3 com Composition API

```vue
<!-- components/StatusSelect.vue -->
<template>
  <select v-model="modelValue" @change="$emit('update:modelValue', modelValue)">
    <option v-for="status in statuses" :key="status" :value="status">
      {{ status }}
    </option>
  </select>
</template>

<script setup>
import enums from '../../shared/enums.json'

defineProps({
  modelValue: String,
})
defineEmits(['update:modelValue'])

const statuses = enums.Status
</script>
```

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---
