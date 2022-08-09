## O que é XML?

XML (e**X**tensible **M**arkup **L**anguage)

É uma linguagem de marcação utilizada para criar componentes de interfaces, onfe basicamente se trabalha com tags `<tag/>`.

~~~~ html
- <receita nome="pão"> (abertura da tag)
- <ingredientes quantidade="3" unidade="xícara" item="farinha"/> (conteúdo da tag)
- </receita> (fechamento da tag)
~~~~

## Orientação de tela

Existem 3 principais tipos:

- **`portrait`** : é o modo principal onde o celular funciona sempre na vertical, o layout não se adapta.
- **`sensor`** : o sensor do celular é quem define a orientação, o layout se adapta.
- **`landscape`** : nesse modo a orientação do celular fica na horizontal.

Para fazer a alteração da orientação, é necessário: 

1. Ir no arquivo: **`AndroidManifest.xml`** e procurar pela linha: **`<action android:name=".MainActivity">`**
2. Colocar o cursor entre as aspas duplas de 'MainActivity' e o sinal de '>'.
3. Digitar: **`android:screenOrientation=""`** e preencher com a orientação desejada.

> EX: **`android:screenOrientation="portrait"`**

![alt](https://aboutreact.com/wp-content/uploads/2018/08/landscap_example4.png "exemplo")

## Constraint Layout

É uma maneira de criar layouts que se adptam muitos bem a uma diversidade de dispositivos.

`wrap_content` : Se adapta de acordo com o tamanho do conteúdo.
`match_constraint` : O componente ocupa todo o espaço disponível.


 
