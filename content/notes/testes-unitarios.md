---
title: "Testes unitários"
alias: "Testes unitários"
---

Os testes unitários são um tipo de teste automatizado que verifica o comportamento de partes individuais do código, como funções, métodos ou classes, isolando-as de outras partes do sistema. O objetivo dos testes unitários é garantir que as partes individuais do código funcionem corretamente, de acordo com sua especificação, em diferentes cenários.

Os testes unitários são escritos geralmente pelos próprios desenvolvedores, e são executados a cada nova alteração de código para garantir que a funcionalidade não tenha sido afetada. Esses testes são escritos em uma linguagem de teste, como JUnit para Java, NUnit para .NET ou Mocha para JavaScript, e são executados automaticamente por meio de ferramentas de integração contínua, como o Jenkins ou o Travis CI.

Os testes unitários têm várias vantagens, como:

- Detectar problemas de forma rápida e precisa em partes individuais do código, tornando mais fácil corrigir problemas antes que eles se propaguem para outras partes do sistema;
- Permitir que os desenvolvedores testem o código em cenários específicos, garantindo que a funcionalidade esteja correta mesmo quando as condições mudam;
- Servir como documentação do código, já que um teste unitário bem escrito pode ser usado para entender como uma parte do sistema deve se comportar.

Para escrever testes unitários eficazes, é importante ter em mente que cada teste deve ser independente, isolado de outros testes e sem dependências externas. O teste deve ser construído em torno de uma hipótese e um conjunto de entradas que se espera que produza uma determinada saída. A saída do teste deve ser verificada automaticamente, usando assertivas ou outras ferramentas de teste, para confirmar se a hipótese é verdadeira.

Um exemplo de teste unitário em JavaScript, utilizando a biblioteca Jest, seria o seguinte:

```javascript
function soma(a, b) {
  return a + b
}

describe("Teste da função soma", () => {
  test("Deve retornar 2 ao somar 1 + 1", () => {
    expect(soma(1, 1)).toBe(2)
  })

  test("Deve retornar 3 ao somar 2 + 1", () => {
    expect(soma(2, 1)).toBe(3)
  })

  test("Deve retornar 0 ao somar -1 + 1", () => {
    expect(soma(-1, 1)).toBe(0)
  })
})
```

Neste exemplo, temos a função `soma` que recebe dois números e retorna a soma deles. Em seguida, utilizamos a biblioteca Jest para escrever um conjunto de testes unitários que testam essa função em diferentes cenários. Cada teste é definido dentro de um bloco `test` e utiliza a função `expect` para verificar o resultado da função `soma` para diferentes valores de entrada.

No final, quando rodamos esses testes, a biblioteca Jest nos retorna um relatório indicando se os testes foram bem sucedidos ou não. Se algum teste falhar, podemos identificar e corrigir o erro antes que ele se torne um problema maior no processo de desenvolvimento.
