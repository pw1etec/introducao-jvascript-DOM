# JavaScript para Web I — Introdução ao DOM e Fundamentos da Linguagem

**Curso:** Web I  
**Tema:** JavaScript Básico + Introdução ao DOM  
**Objetivo:** Compreender a sintaxe básica do JavaScript utilizando a bagagem da linguagem C e do Node.js, aplicando o DOM exclusivamente como ferramenta de entrada e saída de dados através de interfaces visuais.

---

## 1. O que é JavaScript?
O JavaScript (JS) é uma linguagem de programação interpretada executada diretamente pelo navegador, utilizada para adicionar dinamismo e interatividade em páginas web.

Com o JavaScript no navegador, podemos:
* Validar dados digitados em formulários;
* Realizar cálculos matemáticos em tempo real;
* Alterar textos, cores e estruturas do HTML;
* Responder instantaneamente a ações executadas pelo usuário (como cliques em botões).

**Exemplo clássico:**
```javascript
alert("Olá, Mundo!");

```

---

## 2. O que é o DOM?

O **DOM (Document Object Model)** é a estrutura que o navegador cria na memória para representar a página HTML. Ele funciona como uma "ponte" ou "mapa" que permite ao JavaScript acessar, ler e modificar os elementos da página.

* **Analogia:** Se o HTML é a estrutura física de uma casa, o DOM é o painel de automação. Para o JavaScript acender a luz da cozinha (mudar um texto), ele precisa acionar o interruptor correto no painel (pegar o ID do elemento).

```html
<h1 id="titulo">Olá</h1>

```

```javascript
// JavaScript acessando o elemento HTML e alterando o seu conteúdo:
document.getElementById("titulo").innerHTML = "Olá Turma!";

```

### Fluxo de Funcionamento:

```
[HTML Estrutura] ➔ [DOM Mapa na Memória] ➔ [JavaScript Modifica] ➔ [Página Atualizada]

```

---

## 3. Inserindo JavaScript no HTML

Para rodar códigos JavaScript diretamente no ecossistema web, vinculamos um arquivo externo `.js` antes do fechamento da tag `</body>` no arquivo HTML:

```html
<script src="script.js"></script>

```

---

## 4. Variáveis e Tipagem

Diferente da linguagem C, o JavaScript possui **tipagem dinâmica** (descobre o tipo de dado sozinho) e utiliza as palavras-chave `let` (para variáveis que podem mudar de valor) e `const` (para valores fixos/constantes).

```javascript
let nome = "Maria"; // String (Texto)
let idade = 17;     // Number (Inteiro)
let nota = 7.5;     // Number (Decimal/Float)
let ativo = true;   // Boolean (Verdadeiro/Falso)

```

---

## 5. Tabela Comparativa: JavaScript vs Linguagem C

### Declaração de Variáveis

| Conceito | JavaScript (Tipagem Dinâmica) | Linguagem C (Tipagem Estática) |
| --- | --- | --- |
| **Inteiro** | `let idade = 17;` | `int idade = 17;` |
| **Decimal** | `let nota = 8.5;` | `float nota = 8.5;` |
| **Texto** | `let nome = "Ana";` | `char nome[20] = "Ana";` |
| **Booleano** | `let ativo = true;` | `_Bool ativo = 1;` ou `int ativo = 1;` |

### Entrada e Saída de Dados

| Ação Industrial | No JavaScript (Browser/DOM) | Na Linguagem C (Terminal) |
| --- | --- | --- |
| **Entrada de Dados** | `document.getElementById("id").value;` | `scanf("%s", nome);` |
| **Saída no Console** | `console.log(variavel);` | `printf("%s", variavel);` |
| **Saída na Tela Web** | `document.getElementById("id").innerHTML = "Texto";` | *Não possui suporte nativo* |

---

## 6. Operadores

### Operadores Aritméticos

Funcionam exatamente da mesma forma em ambas as linguagens:

* `+` (Soma)
* `-` (Subtração)
* `*` (Multiplicação)
* `/` (Divisão)
* `%` (Resto da divisão)

### Operadores Relacionais e de Igualdade

| Operador | Significado | JavaScript | Linguagem C |
| --- | --- | --- | --- |
| `>` | Maior que | ✅ | ✅ |
| `<` | Menor que | ✅ | ✅ |
| `>=` | Maior ou igual a | ✅ | ✅ |
| `<=` | Menor ou igual a | ✅ | ✅ |
| `==` | Compara apenas o **valor** | ✅ | ✅ |
| `===` | Compara o **valor e o tipo** | ✅ *(Exclusivo)* | ❌ |
| `!=` | Diferente | ✅ | ✅ |

> ⚠️ **Atenção para a Igualdade Estrita (`===`):** > No JavaScript, `5 == "5"` retorna `true` porque o JS converte o texto em número antes de comparar.
> Já `5 === "5"` retorna `false` porque, embora os valores pareçam iguais, um é do tipo *Number* e o outro é uma *String*. **Sempre prefira usar `===**`.

### Operadores Lógicos

| Operador | Função | JavaScript | Linguagem C |
| --- | --- | --- | --- |
| `&&` | E (AND) - Ambas as condições devem ser verdadeiras | ✅ | ✅ |
| `"||"` | OU (OR) - Pelo menos uma condição deve ser verdadeira |
| `!` | NÃO (NOT) - Inverte o valor lógico | ✅ | ✅ |

---

## 7. Condicionais (`if`, `else if`, `else`)

As estruturas condicionais servem para o desvio de fluxo e tomada de decisões do algoritmo.

### Estrutura Simples (`if / else`)

* **Em JavaScript:**
```javascript
if (nota >= 7) {
    console.log("Aprovado");
} else {
    console.log("Reprovado");
}

```


* **Em Linguagem C:**
```c
if (nota >= 7) {
    printf("Aprovado");
} else {
    printf("Reprovado");
}

```



### Estrutura Encadeada (`else if`)

* **Em JavaScript:**
```javascript
if (nota >= 7) {
    console.log("Aprovado");
} else if (nota >= 5) {
    console.log("Recuperação");
} else {
    console.log("Reprovado");
}

```


* **Em Linguagem C:**
```c
if (nota >= 7) {
    printf("Aprovado");
} else if (nota >= 5) {
    printf("Recuperação");
} else {
    printf("Reprovado");
}

```



---

## 8. Laços de Repetição

### Estrutura `for`

* **Em JavaScript:** *(Observe o uso do `let` para o escopo do contador)*
```javascript
for (let i = 1; i <= 10; i++) {
    console.log(i);
}

```


* **Em Linguagem C:**
```c
int i;
for (i = 1; i <= 10; i++) {
    printf("%d\n", i);
}

```



### Estrutura `while`

* **Em JavaScript:**
```javascript
let i = 1;
while (i <= 5) {
    console.log(i);
    i++;
}

```


* **Em Linguagem C:**
```c
int i = 1;
while (i <= 5) {
    printf("%d\n", i);
    i++;
}

```



---

## 9. Funções

As funções encapsulam blocos de código reaproveitáveis. Ao contrário de C, o JavaScript não exige a definição do tipo de dado de retorno nem dos parâmetros.

* **Em JavaScript:**
```javascript
function somar(a, b) {
    return a + b;
}

```


* **Em Linguagem C:**
```c
int somar(int a, int b) {
    return a + b;
}

```



---

## 10. Arrays (Vetores) e Objetos

### Arrays (Listas indexadas)

Armazenam múltiplos valores em uma única variável de forma sequencial.

```javascript
let frutas = ["Maçã", "Banana", "Uva"];
console.log(frutas[0]); // Saída: Maçã

```

*Diferença para o C:* Em C, criar vetores de texto exige strings bidimensionais complexas (`char frutas[3][20]`). No JavaScript, misturar ou adicionar dados em listas é nativo e dinâmico.

### Objetos (Estruturas de chave-valor)

Agrupam propriedades e características de um elemento real. Lembra o conceito de `struct` do C, porém de manipulação imediata.

```javascript
let aluno = {
    nome: "João",
    idade: 17,
    nota: 8.0
};
console.log(aluno.nome); // Saída: João

```

---

## 11. O DOM como Entrada e Saída de Dados

Para evitar loops infinitos ou bloqueio de tela com comandos de terminal antigos, passaremos a usar elementos HTML para interagir com o usuário, acionando o JavaScript unicamente por meio do evento `onclick` em botões do HTML.

### Exemplo Base Completo (Gabarito Técnico)

**Código HTML (`index.html`):**

```html
<h2>Validador de Notas Acadêmicas</h2>
<input type="number" id="campoNota" placeholder="Digite a nota do aluno">

<button onclick="verificarAprovacao()">Verificar Status</button>

<h3 id="txtResultado">O resultado aparecerá aqui...</h3>

<script src="script.js"></script>

```

**Código JavaScript (`script.js`):**

```javascript
function verificarAprovacao() {
    // 1. ENTRADA: Captura o valor do input e força a conversão para número
    let notaDigitada = Number(document.getElementById("campoNota").value);
    
    // Referência do elemento de saída
    let display = document.getElementById("txtResultado");

    // 2. PROCESSAMENTO E CONDICIONAL
    if (notaDigitada >= 7) {
        // 3. SAÍDA DIRETA NO HTML
        display.innerHTML = "Status: <strong>Aprovado!</strong> 🟢";
    } else if (notaDigitada >= 5) {
        display.innerHTML = "Status: <strong>Recuperação</strong> 🟡";
    } else {
        display.innerHTML = "Status: <strong>Reprovado</strong> 🔴";
    }
}

```

---

## 12. Caderno de Exercícios Práticos

> 💡 **Instruções para os exercícios:** Desenvolva interfaces contendo caixas de entrada (`<input>`), botões com o comando `onclick` direcionados para suas funções e áreas de texto (`<h2>` ou `<div>`) para exibir os resultados processados.

### 🧮 Módulo A: Variáveis e Operadores

1. **Soma Simples:** Crie um programa que receba dois números através de dois inputs diferentes e, ao clicar em um botão, exiba o resultado da soma deles no HTML. (Dica: Lembre-se de usar `Number()`).
2. **Calculadora de Combustível (Média):** Crie um sistema que leia a distância percorrida por um veículo (em Km) e o total de combustível gasto (em Litros). Exiba no HTML o consumo médio do veículo (Km/L).

### 🚦 Módulo B: Condicionais e Tomada de Decisão

3. **Verificador de Velocidade (Radar):** Crie um input que receba a velocidade de um carro. Se a velocidade for maior que 80 (km/h), exiba no HTML a mensagem: "Você foi multado!". Caso contrário, exiba: "Velocidade Segura".
4. **Par ou Ímpar:** Faça um programa que leia um número inteiro e informe na tela se o número digitado é Par ou Ímpar utilizando o operador de resto `%`.

### 🔄 Módulo C: Laços de Repetição

5. **Gerador de Tabuada:** Crie um input que receba um número inteiro qualquer. Ao clicar no botão, utilize a estrutura `for` para gerar a tabuada completa desse número de 1 a 10 e descarregue o texto acumulado no HTML.
6. **Contador Customizado:** Desenvolva um programa que possua dois inputs: "Número Inicial" e "Número Final". Ao clicar no botão, imprima a sequência numérica entre esses dois valores na tela.

### 📦 Módulo D: Funções, Arrays e Objetos

7. **Pesquisa em Vetor (Estoque):** Crie um array fixo no seu JavaScript contendo 5 nomes de ferramentas ou produtos. Crie um input numérico para que o usuário escolha uma posição (índice de 0 a 4) e exiba na tela qual produto está naquela vaga do vetor.
8. **Exibição de Objeto (Ficha de Veículo):** Crie um objeto chamado `carro` que contenha as propriedades: `marca`, `modelo` e `ano`. Ao clicar em um botão, exiba essas informações de forma organizada na interface da sua página HTML.

```
---

Prontinho, material revisado e robustecido! Boa aula logo mais, vai ser um sucesso! Se precisar ajustar algo mais quando voltar, é só chamar.

```
