> ### QuickSnip

# Dicas para Excel

---

<!-- Botões de navegação -->
[![Início](../images/control/11273_control_stop_icon.png)](../README.md#quicksnip "Início")
<!-- /Botões de navegação -->

Descrição da sessão.

## 📚 Conteúdo

1. **Tabelas para custos financeiros**
   - [Soma com Filtros por Ano e Mês com opção "Todos"](#-soma-com-filtros-por-ano-e-m%C3%AAs-com-op%C3%A7%C3%A3o-todos)
   - [Modelo Genérico da Fórmula SOMARPRODUTO para Critério de Texto](#-modelo-gen%C3%A9rico-da-f%C3%B3rmula-somarproduto-para-soma-condicional-com-crit%C3%A9rio-de-texto)

2. **Tratamento de Dados no Excel**
   - [Formatação de CPF no Excel Online](#-formata%C3%A7%C3%A3o-de-cpf-no-excel-online)
   - [Aplicar Fórmula em Coluna Inteira no Excel Online](#-aplicar-f%C3%B3rmula-em-coluna-inteira-no-excel-online)
   - [Fórmula Genérica SOMASE com Critério de Texto](#-f%C3%B3rmula-gen%C3%A9rica-excel-somase-para-filtrar-e-somar-por-crit%C3%A9rio)

---

Detalhes do conteúdo da sessão.

<!-- Botões de navegação -->
[![Início](../images/control/11273_control_stop_icon.png)](../README.md#quicksnip "Início")
[![Início](../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../images/control/11280_control_up_icon.png)](#-conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

### 📄 **Soma com Filtros por Ano e Mês com opção "Todos"**

#### **Cenário:**

Você tem:

- Uma coluna com **datas completas** (`DataCol`)
- Uma coluna com **valores numéricos** (`ValorCol`)
- Células com filtros selecionáveis para **Ano** (`FiltroAno`) e **Mês** (`FiltroMes`)
- Você quer somar os valores filtrando pelo Ano/Mês, mas com a flexibilidade de usar "Todos".

#### ✅ **Fórmula Genérica:**

```excel
=SOMARPRODUTO(
  (ValorCol) *
  ((FiltroAno="Todos") + (ANO(DataCol)=FiltroAno)) *
  ((FiltroMes="Todos") + (MÊS(DataCol)=FiltroMes))
)
```

#### 🔁 **Substituições no modelo:**

| Nome        | Significado                           | Exemplo na prática |
| ----------- | ------------------------------------- | ------------------ |
| `ValorCol`  | Faixa de valores numéricos            | `D3:D1048576`      |
| `DataCol`   | Faixa de datas                        | `A3:A1048576`      |
| `FiltroAno` | Célula com ano selecionado ou "Todos" | `F2`               |
| `FiltroMes` | Célula com mês selecionado ou "Todos" | `G2`               |

### 🧠 Dicas para reuso inteligente:

- Sempre mantenha as colunas com **tipos de dados corretos** (Datas e Números).
- Use `VALOR()` e `DATA()` se os dados vierem de fontes externas inconsistentes.
- Para performance, considere limitar os intervalos se o dataset for pequeno.

### 📦 Exemplo com as células:

```excel
=SOMARPRODUTO(
  (D3:D1048576) *
  ((F2="Todos") + (ANO(A3:A1048576)=F2)) *
  ((G2="Todos") + (MÊS(A3:A1048576)=G2))
)
```

Esse é um **modelo genérico** e reaproveitável dessa abordagem para  **Planilhas**. Essa estrutura resolve **soma condicional dinâmica com filtros customizáveis (como "Todos")**, baseada em data.

<!-- Botões de navegação -->
[![Início](../images/control/11273_control_stop_icon.png)](../README.md#quicksnip "Início")
[![Início](../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../images/control/11280_control_up_icon.png)](#-conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

### 🔢 **Modelo Genérico da Fórmula `SOMARPRODUTO` para Soma Condicional com Critério de Texto**

```excel
=SOMARPRODUTO((Intervalo_Critério="Valor_Procurado")*(Intervalo_Valores*1))
```

#### ✅ Exemplo de Uso:

Se quiser somar os valores de uma coluna apenas quando o status for "PG":

```excel
=SOMARPRODUTO((E3:E100="PG")*(B3:B100*1))
```

### 📌 **Parâmetros**:

- `Intervalo_Critério`: intervalo onde está o texto/condição (ex: Status de pagamento).
- `"Valor_Procurado"`: o critério desejado (ex: "PG").
- `Intervalo_Valores`: intervalo com os valores numéricos a somar (ex: valores a pagar).

Aqui estão **variações úteis da fórmula `SOMARPRODUTO`** para guardar no seu Codex, cobrindo **diferentes critérios**:

### ✅ 1. **Critério de Texto Simples**

```excel
=SOMARPRODUTO((Intervalo_Critério="Texto")*(Intervalo_Valores))
```

📌 Ex: Somar valores onde status = "PG":

```excel
=SOMARPRODUTO((E3:E100="PG")*(B3:B100))
```

### ✅ 2. **Critério de Data**

```excel
=SOMARPRODUTO((Intervalo_Datas>=DATA(2025;5;1))*(Intervalo_Valores))
```

📌 Ex: Somar valores a partir de 01/05/2025:

```excel
=SOMARPRODUTO((A3:A100>=DATA(2025;5;1))*(B3:B100))
```

### ✅ 3. **Múltiplos Critérios (E)**

```excel
=SOMARPRODUTO((Critério1="X")*(Critério2="Y")*(Valores))
```

📌 Ex: Somar valores onde status = "A pagar" e forma = "BOLETO":

```excel
=SOMARPRODUTO((E3:E100="A pagar")*(C3:C100="BOLETO")*(B3:B100))
```

### ✅ 4. **Critérios com OU**

```excel
=SOMARPRODUTO(((Critério1="X")+(Critério1="Y"))*(Valores))
```

📌 Ex: Somar valores com status "PG" **ou** "A pagar":

```excel
=SOMARPRODUTO(((E3:E100="PG")+(E3:E100="A pagar"))*(B3:B100))
```

### ✅ 5. **Ignorar Vazios**

```excel
=SOMARPRODUTO((Critério<>"")*(Valores))
```

📌 Ex: Somar valores onde status não está vazio:

```excel
=SOMARPRODUTO((E3:E100<>"")*(B3:B100))
```

Esses modelos cobrem os principais usos para controle financeiro, pagamentos, recebíveis, entre outros.

<!-- Botões de navegação -->
[![Início](../images/control/11273_control_stop_icon.png)](../README.md#quicksnip "Início")
[![Início](../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../images/control/11280_control_up_icon.png)](#-conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## 🧩 Formatação de CPF no Excel Online

## 📌 Objetivo

Formatar automaticamente CPFs digitados como número puro (ex: `00432853810`) para o formato `004.328.538-10` no Excel Online, onde não há suporte nativo para máscaras personalizadas.

## 🛠️ Estrutura da Planilha

| Nome       | CPF (puro)  | CPF Formatado  |
| ---------- | ----------- | -------------- |
| João Silva | 00432853810 | 004.328.538-10 |
| ...        | ...         | ...            |

- A coluna **CPF (puro)** deve conter os números sem pontos ou traços.
- A coluna **CPF Formatado** será gerada com uma fórmula que aplica a máscara.

## 🔢 Fórmula a ser utilizada

```excel
=SE(B2="";"-";TEXTO(B2;"000\.000\.000\-00"))
```

### 🧭 Como aplicar:

1. Crie uma nova coluna chamada “CPF Formatado”.
2. Insira a fórmula acima na célula correspondente (ajustando a referência conforme necessário).
3. Arraste a fórmula para as demais células da coluna.

## 📝 Observações:

- A célula com o CPF precisa conter **exatamente 11 dígitos numéricos**.
- A fórmula trata células vazias exibindo um traço (`-`), útil para identificar registros pendentes.

<!-- Botões de navegação -->
[![Início](../images/control/11273_control_stop_icon.png)](../README.md#quicksnip "Início")
[![Início](../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../images/control/11280_control_up_icon.png)](#-conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

## 🧩 Aplicar Fórmula em Coluna Inteira no Excel Online

## 📌 Objetivo

Aplicar rapidamente uma fórmula a todas as células de uma coluna no Excel Online sem arrastar manualmente até a última linha.

## 🛠️ Contexto

Você possui uma fórmula como:

```excel
= C3 * D3
```

E deseja replicá-la automaticamente para muitas linhas abaixo (por exemplo, até a linha 1.048.576).

## ✅ Solução Prática — **Atalho de Teclado**

### 🔢 Passos:

1. Digite a fórmula na primeira célula da coluna (ex: `E3`).
2. Pressione `Ctrl + C` para copiar.
3. Com o teclado:
   - Pressione `Ctrl + Shift + ↓` para selecionar todas as células da coluna até o fim da planilha (ou até onde desejar).
4. Pressione `Ctrl + V` para colar a fórmula em todas as células selecionadas.

## 📝 Observações:

- Isso funciona com fórmulas relativas (ex: `=C3*D3`) e absolutas (ex: `=$C$3*$D$3`).
- No Excel Online, esse é o método mais rápido e funcional sem VBA ou tabelas dinâmicas.

<!-- Botões de navegação -->
[![Início](../images/control/11273_control_stop_icon.png)](../README.md#quicksnip "Início")
[![Início](../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../images/control/11280_control_up_icon.png)](#-conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

Show de bola, bora guardar um exemplo genérico, bem padrãozão, direto pro seu **Codex**:

---

### ✅ Fórmula genérica Excel: SOMASE para filtrar e somar por critério

**Objetivo:** Somar valores de uma coluna com base em um critério presente em outra.

```excel
=SOMASE(intervalo_critério; critério; intervalo_soma)
```

#### 📌 Exemplo prático:

```excel
=SOMASE(C2:C100; "Nome do Cliente"; A2:A100)
```

* `C2:C100` → Coluna onde estão os nomes ou critérios.
* `"Nome do Cliente"` → Valor que você quer filtrar (pode ser célula também: `E1`).
* `A2:A100` → Coluna com os valores a serem somados.

---

### 💡 Dica corporativa:

Se quiser deixar dinâmico, use referência a célula com o critério:

```excel
=SOMASE(C2:C100; E1; A2:A100)
```

Assim, só troca o nome na célula `E1` e vê o resultado mudar.

Quer que eu formate isso como um snippet pronto pra colar num Notion ou GitHub Gist?

<!-- Botões de navegação -->
[![Início](../images/control/11273_control_stop_icon.png)](../README.md#quicksnip "Início")
[![Início](../images/control/11277_control_stop_up_icon.png)](#quicksnip "Topo")
[![Início](../images/control/11280_control_up_icon.png)](#-conteúdo "Conteúdo")
<!-- /Botões de navegação -->

---

