> ### QuickSnip

# Backend com Prisma e Node.js

---

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
<!-- /Botões de navegação -->

## Conteúdo
1. **ORM Prisma**
   - **Instalação e Configuração**
     - Configuração inicial do Prisma
     - Definição do schema.prisma
     - Integração com bancos de dados (PostgreSQL, MySQL, etc.)
   - **Modelagem de Dados**
     - Definição de modelos no Prisma
     - Relacionamentos (1:1, 1:N, N:M)
     - Campos opcionais e padrões
   - **Consultas**
     - Consultas básicas (findUnique, findMany)
     - Filtragem, paginação e ordenação
     - Relações aninhadas
   - **Mutations**
     - Criação de registros (create)
     - Atualização de registros (update)
     - Exclusão de registros (delete)
   - **Migrations**
     - Gerar migrations a partir do schema
     - Aplicar migrations no banco de dados
     - Desfazer migrations
     - [Sincronizar Modelo do Banco de Dados](#sincronizar-modelo-do-banco-de-dados "Sincronizar Modelo do Banco de Dados")
     - [Gerar Tipos e Classes a Partir do Schema](#gerar-tipos-e-classes-a-partir-do-schema "Gerar Tipos e Classes a Partir do Schema")

---

Todos os tópicos relacionados a **Frontend** estão organizados dentro de **React.JS**, facilitando o acesso ao conteúdo específico de React.

---

## Comandos do Prisma para Sincronização e Geração de Tipos

### Sincronizar Modelo do Banco de Dados
Use o comando abaixo para sincronizar o modelo do Prisma com o estado atual do banco de dados. Isso é útil quando há mudanças diretas no banco de dados e você quer refletir essas alterações no esquema do Prisma.

```bash
npx prisma db pull
```

Esse comando atualiza o arquivo `schema.prisma` com as definições mais recentes de tabelas e colunas do banco de dados.

### Gerar Tipos e Classes a Partir do Schema
Após qualquer modificação no arquivo `schema.prisma`, execute o comando a seguir para gerar os tipos e as classes necessárias para o uso com o Prisma Client:

```bash
npx prisma generate
```

Esse comando cria automaticamente o cliente Prisma, facilitando o acesso aos modelos e consultas ao banco de dados dentro do seu código JavaScript ou TypeScript.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

