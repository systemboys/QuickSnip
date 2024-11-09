> ### QuickSnip

# Frontend com React.JS

---

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
<!-- /Botões de navegação -->

## Conteúdo
1. **React.JS**
   - **Estrutura Básica**
     - Criação de componentes funcionais
     - JSX e renderização condicional
     - Props e estado (state)
   - **Hooks**
     - useState para gerenciamento de estado
       - [Explicação detalhada sobre `useState` com exemplos práticos](#explica%C3%A7%C3%A3o-detalhada-sobre-usestate-com-exemplos-pr%C3%A1ticos "Explicação detalhada sobre `useState` com exemplos práticos")
       - [Estados complexos (objetos e arrays) com `useState`](#exemplo-1-contador-simples "Estados complexos (objetos e arrays) com `useState`")
       - [Boas práticas e erros comuns ao usar `useState`](#atualizando-estado-com-fun%C3%A7%C3%B5es-de-atualiza%C3%A7%C3%A3o "Boas práticas e erros comuns ao usar `useState`")
     - useEffect para efeitos colaterais
       - [Explicação detalhada sobre `useEffect` com exemplos práticos](#explica%C3%A7%C3%A3o-detalhada-sobre-useeffect-com-exemplos-pr%C3%A1ticos "Explicação detalhada sobre `useEffect` com exemplos práticos")
       - [Limpeza de efeitos e uso de dependências](#3-limpeza-de-efeitos "Limpeza de efeitos e uso de dependências")
       - [Erros comuns e boas práticas com `useEffect`](#erros-comuns-com-useeffect "Erros comuns e boas práticas com `useEffect`")
     - useContext para contexto global
       - [Explicação detalhada sobre `useContext` com exemplos práticos](#o-usecontext-para-contexto-global "Explicação detalhada sobre `useContext` com exemplos práticos")
       - [Compartilhando dados globais com `useContext`](#exemplo-avan%C3%A7ado-compartilhando-tema-global "Compartilhando dados globais com `useContext`")
       - [Quando usar `useContext` e evitar prop drilling](#quando-usar-usecontext "Quando usar `useContext` e evitar prop drilling")
   - **Componentes Avançados**
     - Componentes controlados e não controlados
     - Refs com useRef
     - Lazy loading e Suspense
   - **Roteamento**
     - Configuração básica com React Router
     - Roteamento dinâmico
     - Redirecionamento e links
   - **Gerenciamento de Estado**
     - useReducer para estados complexos
     - Context API
     - Integração com Redux
   - **Estilos**
     - CSS-in-JS com styled-components
     - Animações com Framer Motion
     - Tailwind CSS com React
   - **Boas Práticas**
     - Otimização de performance com memo e useCallback
     - Testes com React Testing Library
     - Acessibilidade em componentes React

---

Nesta sessão há varios itens de conteúdos referentes à React.JS.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Explicação detalhada sobre `useState` com exemplos práticos

O `useState` é um dos hooks mais usados no React, utilizado para adicionar e gerenciar estados em componentes funcionais. Com ele, é possível definir valores dinâmicos que, ao serem alterados, causam uma re-renderização do componente para refletir as mudanças na interface do usuário.

### Como o `useState` Funciona

O `useState` permite que você declare uma variável de estado e uma função para atualizá-la. Ele recebe um valor inicial para o estado e retorna um array com dois elementos:

1. **O valor do estado atual**: a variável que representa o estado.
2. **Uma função para atualizar o estado**: ao ser chamada, essa função define um novo valor para o estado, causando a re-renderização do componente com o novo valor.

### Sintaxe Básica

```javascript
const [state, setState] = useState(initialValue);
```

- `state` é o valor atual do estado.
- `setState` é a função usada para atualizar o valor de `state`.
- `initialValue` é o valor inicial do estado, que pode ser de qualquer tipo: número, string, objeto, array, etc.

### Exemplo 1: Contador Simples

Vamos começar com um exemplo básico: um contador que aumenta de 1 em 1 quando clicamos em um botão.

```javascript
import React, { useState } from 'react';

function Counter() {
    // Declarando uma variável de estado chamada "count" com valor inicial 0
    const [count, setCount] = useState(0);

    return (
        <div>
            <p>Contagem: {count}</p>
            <button onClick={() => setCount(count + 1)}>Incrementar</button>
        </div>
    );
}
```

Neste exemplo:

- `count` é a variável de estado que armazena o valor atual do contador.
- `setCount` é a função que atualiza o estado `count`.
- Toda vez que `setCount` é chamado com um novo valor, o componente `Counter` é re-renderizado com o novo valor de `count`.

### Exemplo 2: Manipulação de Strings

Aqui está um exemplo de como `useState` pode ser usado para gerenciar o estado de uma string, como o valor de um campo de entrada (input).

```javascript
import React, { useState } from 'react';

function NameInput() {
    const [name, setName] = useState('');

    const handleChange = (e) => {
        setName(e.target.value);
    };

    return (
        <div>
            <input type="text" value={name} onChange={handleChange} placeholder="Digite seu nome" />
            <p>Seu nome é: {name}</p>
        </div>
    );
}
```

Neste exemplo:

- `name` é a variável de estado que armazena o valor do campo de entrada.
- `setName` atualiza o valor de `name` sempre que o usuário digita algo no campo de entrada.
- O valor de `name` é exibido em tempo real.

### Exemplo 3: Estado com Objetos

Você também pode usar `useState` para gerenciar estados complexos, como objetos. Neste exemplo, vamos armazenar o estado de um formulário com várias entradas (nome e idade).

```javascript
import React, { useState } from 'react';

function UserProfile() {
    const [user, setUser] = useState({ name: '', age: '' });

    const handleNameChange = (e) => {
        setUser((prevUser) => ({
            ...prevUser,
            name: e.target.value
        }));
    };

    const handleAgeChange = (e) => {
        setUser((prevUser) => ({
            ...prevUser,
            age: e.target.value
        }));
    };

    return (
        <div>
            <input type="text" value={user.name} onChange={handleNameChange} placeholder="Nome" />
            <input type="number" value={user.age} onChange={handleAgeChange} placeholder="Idade" />
            <p>Nome: {user.name}, Idade: {user.age}</p>
        </div>
    );
}
```

Neste exemplo:

- `user` é um objeto contendo o nome e a idade.
- `setUser` atualiza o objeto `user`. Utilizamos o spread operator (`...prevUser`) para garantir que outras propriedades de `user` não sejam sobrescritas.
- Isso é útil para formulários onde queremos manter várias entradas em um único objeto de estado.

### Exemplo 4: Estado com Arrays

Também é comum usar o `useState` para gerenciar arrays. Vamos ver um exemplo onde adicionamos itens a uma lista:

```javascript
import React, { useState } from 'react';

function ItemList() {
    const [items, setItems] = useState([]);

    const addItem = () => {
        setItems([...items, `Item ${items.length + 1}`]);
    };

    return (
        <div>
            <button onClick={addItem}>Adicionar Item</button>
            <ul>
                {items.map((item, index) => (
                    <li key={index}>{item}</li>
                ))}
            </ul>
        </div>
    );
}
```

Neste exemplo:

- `items` é um array que armazena uma lista de strings.
- `setItems` atualiza o array `items`, adicionando um novo item a cada clique do botão.
- Utilizamos o spread operator (`...items`) para copiar o array atual e adicionar um novo item ao final.

### Atualizando Estado com Funções de Atualização

Se o novo valor do estado depende do valor anterior, é melhor passar uma função para o `setState` em vez de um valor direto. A função recebe o estado anterior como argumento, o que ajuda a evitar problemas quando o estado é atualizado de forma assíncrona.

```javascript
setCount((prevCount) => prevCount + 1);
```

Isso é especialmente útil em casos onde o estado pode mudar rapidamente, como em contadores ou atualizações consecutivas.

### Resumo do `useState`

1. **Declaração**: `useState` permite declarar uma variável de estado e uma função para atualizá-la.
2. **Atualização**: Toda vez que a função de atualização do estado é chamada, o componente é re-renderizado com o novo valor do estado.
3. **Estado Inicial**: `useState` aceita um valor inicial, que pode ser um valor direto ou o resultado de uma função.
4. **Complexidade de Estado**: `useState` pode ser usado para estados simples (como números e strings) ou complexos (como arrays e objetos).

### Considerações

- **Atualizações de Estado Assíncronas**: `useState` realiza atualizações de estado de forma assíncrona, o que significa que o valor do estado pode não ser atualizado imediatamente após chamar `setState`. Isso é importante para operações que dependem do valor atualizado.
  
- **Não Modificar o Estado Diretamente**: Sempre use a função de atualização (como `setCount`) em vez de modificar o valor do estado diretamente. Isso garante que o React consiga detectar as mudanças e renderizar o componente corretamente.

O `useState` é a base para gerenciar estados em componentes funcionais e permite que seus componentes sejam interativos e dinâmicos. Junto com outros hooks como `useEffect`, ele forma a base de desenvolvimento de componentes React modernos.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## Explicação detalhada sobre `useEffect` com exemplos práticos

O `useEffect` é um dos hooks fundamentais no React. Ele permite que você realize efeitos colaterais em componentes funcionais, como executar código após a renderização, manipular o DOM, buscar dados de APIs, configurar um intervalo de tempo, e muito mais. Antes do `useEffect`, esses tipos de operações eram feitos dentro dos métodos de ciclo de vida em componentes de classe, como `componentDidMount`, `componentDidUpdate`, e `componentWillUnmount`.

### Como o `useEffect` Funciona

O `useEffect` é executado após o React terminar de renderizar o componente pela primeira vez e, opcionalmente, após cada atualização (re-renderização), dependendo das dependências passadas para ele. Ele recebe dois parâmetros:

1. **Uma função de efeito (callback)**: o código que você quer executar após a renderização.
2. **Um array de dependências** (opcional): lista de variáveis que, quando mudam, fazem o `useEffect` ser executado novamente. Se o array estiver vazio (`[]`), o `useEffect` será executado apenas uma vez após a primeira renderização.

### Sintaxe Básica

```javascript
useEffect(() => {
    // Código a ser executado após a renderização
    return () => {
        // Código de limpeza (opcional)
    };
}, [dependências]);
```

### Exemplos de Uso

#### 1. Executando um Efeito Apenas na Primeira Renderização

Para executar um efeito apenas uma vez, após a primeira renderização (como buscar dados de uma API), passe um array de dependências vazio (`[]`). Isso faz o `useEffect` funcionar como `componentDidMount` em um componente de classe.

```javascript
import React, { useEffect, useState } from 'react';

function FetchDataComponent() {
    const [data, setData] = useState(null);

    useEffect(() => {
        // Executa o código de busca de dados apenas uma vez
        fetch('https://api.example.com/data')
            .then((response) => response.json())
            .then((data) => setData(data));
    }, []); // Array vazio como dependência

    return (
        <div>
            <h1>Dados da API</h1>
            {data ? <pre>{JSON.stringify(data, null, 2)}</pre> : <p>Carregando...</p>}
        </div>
    );
}
```

#### 2. Executando um Efeito Quando Uma Dependência Muda

Quando você passa variáveis no array de dependências, o `useEffect` será executado novamente sempre que uma dessas variáveis mudar. Isso é útil para casos como atualizar dados com base em uma entrada do usuário.

```javascript
import React, { useState, useEffect } from 'react';

function SearchComponent() {
    const [query, setQuery] = useState('');
    const [results, setResults] = useState([]);

    useEffect(() => {
        if (query) {
            fetch(`https://api.example.com/search?q=${query}`)
                .then((response) => response.json())
                .then((data) => setResults(data.results));
        }
    }, [query]); // O efeito é executado sempre que `query` muda

    return (
        <div>
            <input
                type="text"
                value={query}
                onChange={(e) => setQuery(e.target.value)}
                placeholder="Buscar..."
            />
            <ul>
                {results.map((result) => (
                    <li key={result.id}>{result.name}</li>
                ))}
            </ul>
        </div>
    );
}
```

#### 3. Limpeza de Efeitos

Muitos efeitos precisam de uma "limpeza" quando o componente é desmontado ou quando o efeito é executado novamente (por exemplo, remover um event listener, cancelar uma requisição ou limpar um intervalo). Para isso, o `useEffect` permite retornar uma função de limpeza.

```javascript
import React, { useEffect, useState } from 'react';

function TimerComponent() {
    const [count, setCount] = useState(0);

    useEffect(() => {
        // Define um intervalo de tempo
        const interval = setInterval(() => {
            setCount((prevCount) => prevCount + 1);
        }, 1000);

        // Função de limpeza que limpa o intervalo quando o componente é desmontado
        return () => clearInterval(interval);
    }, []); // Array vazio para rodar apenas uma vez

    return <h1>Contador: {count}</h1>;
}
```

Neste exemplo, o intervalo será limpo quando o componente for desmontado, prevenindo possíveis erros e vazamento de memória.

#### 4. Efeito Sem Dependências (Executa em Toda Renderização)

Se você não passar um array de dependências, o `useEffect` será executado após cada renderização do componente. Essa prática deve ser evitada na maioria dos casos, pois pode causar loops infinitos e sobrecarregar a aplicação.

```javascript
useEffect(() => {
    console.log('Este efeito será executado em toda renderização');
});
```

Esse uso é raro e geralmente não é recomendado.

### Resumo das Dependências

- **Sem array de dependências**: o efeito executa em toda renderização.
- **Array vazio (`[]`)**: o efeito executa apenas na primeira renderização.
- **Com dependências**: o efeito executa na primeira renderização e toda vez que uma das dependências mudar.

### Erros Comuns com `useEffect`

1. **Loops Infinitos**: Se você não configurar o array de dependências corretamente, pode causar um loop infinito, pois o efeito continuará sendo executado indefinidamente.
   
2. **Esquecer a Função de Limpeza**: Para efeitos que adicionam listeners ou intervalos, esquecer de limpar pode levar a problemas de desempenho e bugs.

3. **Dependências não Declaráveis**: Às vezes, você precisa de variáveis ou funções dentro do `useEffect` que não podem ser declaradas diretamente no array de dependências. Nestes casos, é recomendável usar `useCallback` ou `useMemo` para garantir que as referências não mudem em cada renderização.

### Conclusão

O `useEffect` é um hook poderoso que permite realizar efeitos colaterais em componentes funcionais de maneira controlada e previsível. Dominar seu uso e entender a mecânica das dependências ajudará a construir componentes mais eficientes e sem bugs.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## O `useContext` para contexto global

O `useContext` é um hook no React que permite acessar o valor de um contexto em qualquer lugar de um componente funcional, sem precisar "passar" props através de vários níveis de componentes. Isso é útil para compartilhar informações globais, como dados de autenticação, configurações de tema, ou preferências do usuário, entre diversos componentes sem a necessidade de prop drilling (passagem de props por múltiplos componentes intermediários).

### Como o `useContext` Funciona

Para entender como `useContext` funciona, primeiro precisamos entender o contexto (`Context`) no React. O contexto é criado usando a função `React.createContext`, que retorna um objeto contendo um `Provider` e um `Consumer`.

- **`Provider`**: O `Provider` é um componente que "fornece" o valor do contexto para os componentes filhos.
- **`Consumer`**: O `Consumer` é um componente que permite acessar o valor do contexto. Com o hook `useContext`, você pode acessar o valor diretamente, sem precisar usar o `Consumer`.

O `useContext` simplifica o acesso ao valor do contexto em componentes funcionais. Ele recebe o próprio contexto como argumento e retorna o valor atual do contexto fornecido pelo `Provider`.

### Sintaxe Básica

```javascript
const valor = useContext(MyContext);
```

- `MyContext` é o contexto criado com `React.createContext`.
- `valor` será o valor atual do contexto, que pode ser um número, string, objeto, função, etc.

### Exemplo Completo de Uso do `useContext`

#### Passo 1: Criar um Contexto

Primeiro, criamos um contexto que será usado para armazenar o estado global. Neste exemplo, vamos criar um contexto para dados de autenticação.

```javascript
import React, { createContext, useState } from 'react';

// Criação do contexto de autenticação
export const AuthContext = createContext();

// Componente Provider que fornecerá o contexto
export function AuthProvider({ children }) {
    const [user, setUser] = useState(null);

    const login = (userData) => {
        setUser(userData); // Simula o login do usuário
    };

    const logout = () => {
        setUser(null); // Simula o logout do usuário
    };

    return (
        <AuthContext.Provider value={{ user, login, logout }}>
            {children}
        </AuthContext.Provider>
    );
}
```

- `AuthContext` é o contexto criado.
- `AuthProvider` é o componente que fornece o contexto para os componentes filhos.
- `login` e `logout` são funções de manipulação do estado `user`, que simulam a entrada e saída do usuário.

#### Passo 2: Envolver a Aplicação com o `Provider`

Para que o contexto esteja disponível em toda a aplicação, envolva o `AuthProvider` ao redor de componentes que precisam acessar o contexto. Normalmente, isso é feito no ponto mais alto da árvore de componentes, como `App.js`.

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import { AuthProvider } from './AuthContext';

ReactDOM.render(
    <AuthProvider>
        <App />
    </AuthProvider>,
    document.getElementById('root')
);
```

#### Passo 3: Consumir o Contexto com `useContext`

Agora, em qualquer componente dentro de `AuthProvider`, podemos acessar o contexto de autenticação com o `useContext`.

```javascript
import React, { useContext } from 'react';
import { AuthContext } from './AuthContext';

function UserProfile() {
    const { user, login, logout } = useContext(AuthContext);

    return (
        <div>
            {user ? (
                <>
                    <p>Bem-vindo, {user.name}!</p>
                    <button onClick={logout}>Sair</button>
                </>
            ) : (
                <button onClick={() => login({ name: 'Marcos' })}>Entrar</button>
            )}
        </div>
    );
}
```

Neste exemplo:

- `useContext(AuthContext)` é usado para acessar o valor do contexto, que inclui o usuário (`user`) e as funções `login` e `logout`.
- Dependendo de `user`, mostramos uma mensagem de boas-vindas e um botão de logout, ou um botão de login que simula a entrada do usuário.

### Exemplo Avançado: Compartilhando Tema Global

Outro exemplo comum é compartilhar configurações de tema (como "claro" e "escuro") entre os componentes da aplicação.

#### Criando o Contexto de Tema

```javascript
import React, { createContext, useState } from 'react';

export const ThemeContext = createContext();

export function ThemeProvider({ children }) {
    const [theme, setTheme] = useState('light');

    const toggleTheme = () => {
        setTheme((prevTheme) => (prevTheme === 'light' ? 'dark' : 'light'));
    };

    return (
        <ThemeContext.Provider value={{ theme, toggleTheme }}>
            {children}
        </ThemeContext.Provider>
    );
}
```

#### Usando o `Provider` em `App.js`

```javascript
import React from 'react';
import { ThemeProvider } from './ThemeContext';
import AppContent from './AppContent';

function App() {
    return (
        <ThemeProvider>
            <AppContent />
        </ThemeProvider>
    );
}

export default App;
```

#### Consumindo o Contexto de Tema

No componente `AppContent`, consumimos o contexto de tema com o `useContext`.

```javascript
import React, { useContext } from 'react';
import { ThemeContext } from './ThemeContext';

function AppContent() {
    const { theme, toggleTheme } = useContext(ThemeContext);

    return (
        <div style={{ background: theme === 'light' ? '#fff' : '#333', color: theme === 'light' ? '#000' : '#fff' }}>
            <h1>Tema atual: {theme}</h1>
            <button onClick={toggleTheme}>Alternar Tema</button>
        </div>
    );
}

export default AppContent;
```

### Explicação

- `theme` armazena o valor atual do tema, e `toggleTheme` altera entre "light" e "dark".
- `AppContent` usa `theme` para alterar as cores de fundo e do texto, criando um tema dinâmico que reflete o valor do contexto.

### Resumo do `useContext`

1. **Criar o Contexto**: Usando `React.createContext()` para criar um contexto.
2. **Fornecer o Contexto**: Envolver os componentes com o `Provider` para que o contexto esteja acessível.
3. **Consumir o Contexto**: Utilizar `useContext` em qualquer componente dentro do `Provider` para acessar o valor do contexto.

### Quando Usar `useContext`

- **Dados Globais**: Ideal para informações que precisam ser acessadas em várias partes da aplicação, como dados de autenticação, preferências do usuário, temas e configurações de idioma.
- **Evitar Prop Drilling**: Simplifica o código evitando a passagem de props por vários níveis de componentes intermediários.

O `useContext` é uma ferramenta poderosa para gerenciamento de dados globais em uma aplicação React e, quando combinado com o `useState` ou `useReducer` no `Provider`, permite gerenciar estados complexos de forma eficiente.

<!-- Botões de navegação -->
[![Início](../../images/control/11273_control_stop_icon.png)](../../README.md#quicksnip "Início")
[![Início](../../images/control/11269_control_left_icon.png)](../README.md#quicksnip "Voltar")
[![Início](../../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../../images/control/11280_control_up_icon.png)](#conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---