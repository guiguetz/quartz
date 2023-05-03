
---
title: Testes de regressão
alias: Testes de regressão
---

Os testes de regressão são realizados para verificar se uma alteração no código introduzida em uma nova versão ou release do software, não introduziu erros em funcionalidades existentes, ou seja, se a nova versão do software continua a funcionar corretamente como as versões anteriores. 

Isso é importante porque, quando novas funcionalidades são adicionadas ou alteradas, pode ocorrer de algo que antes funcionava corretamente deixar de funcionar devido a interações não previstas entre o novo código e o código já existente. Os testes de regressão ajudam a detectar esses erros antes que eles sejam colocados em produção, garantindo que a qualidade do software não seja comprometida.

Os testes de regressão podem ser realizados em diferentes níveis de teste, incluindo testes unitários, de integração e de sistema. Eles podem ser executados automaticamente ou manualmente, dependendo da complexidade do software e do processo de teste.

Um exemplo de teste de regressão pode ser a adição de uma nova funcionalidade em uma aplicação web que já existe há algum tempo. Suponha que a aplicação permita a criação de uma conta de usuário e que um novo recurso seja adicionado para permitir que o usuário faça login com a conta do Google. Para realizar um teste de regressão, seria necessário garantir que, após a adição desse novo recurso, a criação de contas de usuário e login com email e senha ainda estejam funcionando corretamente.

Em JavaScript, um exemplo de teste de regressão utilizando a biblioteca Jest poderia ser o seguinte:

```javascript
describe('Testes de regressão da função de cálculo de desconto', () => {
  test('Deve retornar o valor correto do desconto', () => {
    // Teste inicial para verificar se a função de cálculo de desconto está funcionando corretamente
    expect(calcularDesconto(100, 10)).toBe(90);
  });

  test('Deve manter o valor do desconto após atualização do código', () => {
    // Simula a atualização do código adicionando uma nova condição para o desconto
    const novoCodigo = `function calcularDesconto(valor, percentual) {
      if (percentual > 20) {
        return valor - (valor * 0.2);
      }
      return valor - (valor * percentual / 100);
    }`;

    // Executa o código atualizado
    eval(novoCodigo);

    // Testa se a função ainda está retornando o valor correto após a atualização do código
    expect(calcularDesconto(100, 10)).toBe(90);
  });
});
```

Neste exemplo, estamos testando uma função de cálculo de desconto que recebe um valor e um percentual de desconto e retorna o valor com o desconto aplicado. O primeiro teste é um teste inicial para verificar se a função está funcionando corretamente. O segundo teste simula uma atualização do código adicionando uma nova condição para o desconto e verifica se a função ainda está retornando o valor correto após a atualização do código. Esse teste de regressão ajuda a garantir que a nova condição de desconto não afetou o funcionamento da função para outros valores de entrada.