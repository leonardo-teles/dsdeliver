# ➤ Back-end Ds Delivery

A implantação da API foi feita utilizando o Heroku.

**Atenção**: Você precisa ter o Java JDK 11 instalado bem como o `PATH_VARIABLE` do Java configurado e uma IDE de sua preferência.

**O backend está setado em modo de teste, dessa forma, não é necessário nenhum tipo de configuração para banco de dados, pois está sendo utilizado o banco de dados em memória (H2).**

Execute o comando: `mvn install` para instalar as dependências do Maven.

Após baixar as dependências, execute a aplicação e a API estará rodando em `http://localhost:8080`.

Acesso ao banco de dados: `http://localhost:8080/h2-console`.

## ➤ Endpoints

Os seguintes endpoints estão configurados:

### Products

- `/products` - GET - Exibe todos os produtos cadastrados em ordem alfabética crescente pelo nome do produto.

### Orders

- `/orders` - GET - Exibe todos os pedidos que estão com status "PENDING", do mais antigo até o mais recente.
- `/orders` - POST - Cria um pedido.
- `/orders/{id}/delivered` - PUT - Atualiza o status de um pedido para "DELIVERED".

**Exemplo de dados para criar Order (JSON)**

```json
{
  "address": "any_address",
  "longitude": 9999999,
  "latitude": 9999999,
  "products": [
    {
      "id": 1
    },
    {
      "id": 2
    }
  ]
}
```

## ➤ Tecnologias
1. Java 11
2. Spring Boot 2.4.1
3. H2 DB
4. Postgre SQL 9.5


## ➤ Dados para Povoar a API
Arquivo **data.sql** na pasta `src/main/resources`. 