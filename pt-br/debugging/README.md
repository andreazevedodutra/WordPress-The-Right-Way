# Depuração

Ao desenvolver para o WordPress, é importante que seu código funciona, mas quando ele falhar, ele pode ser como uma agulha em um palheiro. Ele não precisa ser assim.

Este capítulo abrange:

 - Como descobrir o que os erros ocorreram
 - Como depurar o problema
 - Plugins e ferramentas para tornar a sua vida mais fácil
 - Características em WordPress que fazem a depuração mais fácil
 - Como prevenir a ocorrência de problemas para começar e fáceis ferramentas automatizadas para pegar os erros para você

But before you continue, a word on White Screens of Death

## Telas brancas da morte

Um problema comum com novos desenvolvedores do WordPress é a tela branca da morte. Isso acontece quando ocorre um erro fatal em PHP. Muitos novos desenvolvedores responder a esta fazendo alterações e esperando que o problema vai embora, mas há melhores maneiras de lidar com isso.

Quando ocorre um erro em PHP, ele fica registrado em algum lugar, e você pode descobrir o que deu errado e onde.

Um bom ponto de partida para os desenvolvedores é [enable `WP_DEBUG`](wp-configphp.md).

