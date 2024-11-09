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

