# Como funciona a internet

Basicamente com requisições:
~~~ 
brownser -> requisição -> servidor -> resposta (HTML, CSS)
~~~ 

## Requisições HTTP
- **HTTP (Hyper Transfer Protocol)**
    - Padronizou a comunicação entre navegadores e servidores

- **Tipos de requisições:**
    - `Get:` recuperar dados no servidor
    - `Post:` Criar dado novo no servidor
    - `Put:`Atualizar dados no servidor
    - `Delete:` Deletar dados no servidor

## Código de status

Toda vez que uma requisição é feita, o servidor pode retornar uma mensagem de erro.

**Alguns códigos de erro:**

- `404:` Not Found
- `200:` ok
- `501:` Bad Gateway

## Utilizando API

- **API** (Application Programming Interface), em português: "Interface de Programação de Aplicações.

Basicamente é um software criado em algum tipo de linguagem de programação que fica em um servidor respondendo requisições.

### __Tipos de retornos API:__

- XML ( _eXtensible Markup Language_ )
~~~
<resultado>
    <temperatura>20</temperatura>
    <unidade>Celsius</unidade>
</resultado>
~~~

Algumas API's retornam um tipo específico, isso precisa ser consultado na documentação.

- JSON ( _JavaScript Object Notation_ )
~~~
{"resultado":
    {
    "temperatura":20
    ,"unidade: "Celsius"
    }
}
~~~