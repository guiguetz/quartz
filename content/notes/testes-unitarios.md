---
title: "Testes unitários"
alias: "Testes unitários"
---

Testes unitários são [[testes]] automatizados que visam testar unidades isoladas de código, como funções, métodos ou classes, de forma individual e independente de outras partes do sistema. O objetivo dos testes unitários é verificar se essas unidades de código estão funcionando corretamente, de acordo com as especificações definidas, e detectar possíveis erros ou comportamentos inesperados.

Os testes unitários são importantes porque garantem que as unidades de código estejam funcionando corretamente e que possíveis erros sejam detectados o mais cedo possível no processo de desenvolvimento, quando é mais fácil e mais barato corrigi-los. Além disso, os testes unitários permitem que as unidades de código sejam testadas de forma isolada, sem depender de outras partes do sistema, o que facilita a identificação e correção de erros.

Um exemplo de teste unitário em JavaScript, utilizando a biblioteca Jest, seria o seguinte:

```javascript
function soma(a, b) {
  return a + b
}

describe("Teste da função soma", () => {
  test("Deve retornar 2 ao somar 1 + 1", () => {
    expect(soma(1, 1)).toBe(2)
  })

  test("Deve retornar 0 ao somar 0 + 0", () => {
    expect(soma(0, 0)).toBe(0)
  })

  test("Deve retornar -2 ao somar -1 + -1", () => {
    expect(soma(-1, -1)).toBe(-2)
  })
})
```

Neste exemplo, temos a função `soma` que recebe dois números e retorna a soma deles. Em seguida, utilizamos a biblioteca Jest para escrever um conjunto de testes unitários que testam essa função em diferentes cenários. Cada teste é definido dentro de um bloco `test` e utiliza a função `expect` para verificar o resultado da função `soma` para diferentes valores de entrada.

No final, quando rodamos esses testes, a biblioteca Jest nos retorna um relatório indicando se os testes foram bem sucedidos ou não. Se algum teste falhar, podemos identificar e corrigir o erro antes que ele se torne um problema maior no processo de desenvolvimento.
