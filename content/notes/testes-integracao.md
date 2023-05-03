---
title: "Testes de integração"
alias: "Testes de integração"
---

Os [[testes]] de integração são testes automatizados que verificam se diferentes partes do sistema funcionam corretamente quando combinadas. Eles testam a integração entre os componentes do sistema, como módulos, serviços ou sistemas externos, e avaliam se o sistema como um todo atende aos requisitos e especificações.

Ao contrário dos testes unitários, que verificam unidades de código isoladas, os testes de integração exigem que as diferentes partes do sistema sejam integradas e testadas juntas. Isso significa que, para realizar os testes de integração, é necessário ter pelo menos duas unidades de código que possam ser integradas e testadas.

Os testes de integração são importantes porque permitem detectar problemas que podem surgir quando diferentes partes do sistema são combinadas, como problemas de compatibilidade, dependências ou interações inesperadas. Eles também ajudam a garantir que o sistema como um todo esteja funcionando corretamente e atendendo aos requisitos e especificações.

Um exemplo de teste de integração seria a integração entre um sistema de gerenciamento de pedidos de uma loja virtual e um sistema de pagamentos. Nesse caso, seria necessário criar um cenário de teste em que um pedido é realizado e o sistema de pagamentos é acionado para realizar o pagamento do pedido. O teste de integração verificaria se os sistemas estão funcionando corretamente em conjunto, incluindo a criação do pedido, o processamento do pagamento e a atualização do status do pedido.

Em JavaScript, um exemplo de teste de integração utilizando a biblioteca Jest seria o seguinte:

```javascript
const app = require("./app")
const request = require("supertest")

describe("Teste da API de usuários", () => {
  test("Deve criar um novo usuário", async () => {
    const response = await request(app).post("/usuarios").send({
      nome: "Fulano de Tal",
      email: "fulano@exemplo.com",
      senha: "123456",
    })

    expect(response.status).toBe(201)
    expect(response.body).toHaveProperty("id")
  })

  test("Deve listar todos os usuários", async () => {
    const response = await request(app).get("/usuarios")

    expect(response.status).toBe(200)
    expect(response.body).toHaveLength(1)
  })
})
```

Neste exemplo, estamos testando uma API de usuários que permite a criação e listagem de usuários. Utilizamos a biblioteca Supertest para realizar as requisições HTTP e verificar as respostas do servidor. Os testes garantem que a API esteja funcionando corretamente e que os endpoints de criação e listagem de usuários estejam integrados e funcionando juntos.
