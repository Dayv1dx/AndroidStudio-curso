# SnackBar

Lembra bastante um Toast, porém dá para adicionar as ações: fazer e desfazer.

![i](https://lh3.googleusercontent.com/1ua7ClEv_BMD9DMV43HRj82LR8jFPxhI1EpO4ueLuHnJMc3llqQq6F7sQBxyGDs1XHHW3MIEH6lsciPMF4YwSs78Ug2dG6HCw9Rm5agZFTWdKwx8RXtz=w1064-v0)

 Para utilizar a SnackBar é necessário adicionar uma dependência no `biuld.gradle (Module app)`

 MainAcitivity
 ~~~ java

 private SnackBar snackbar;

 snackbar = SnackBar.make(
    view, // contexto (tem que ser uma view)
    "texto a ser exibido", // texto
    Snackbar.LENGTH_SHORT) // duração
    .show(); // método para exibir

// Para definir uma ação, deve-se usar o método "setAction"

setAction("texto", acao({}))
