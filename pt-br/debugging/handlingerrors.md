# Tratamento de erros

Enquanto estiver usando as APIs do núcleo, é uma boa idéia verificar os valores de retorno. Por exemplo, ao criar um post, se algo der errado, você deve ser capaz de lidar com esse resultado. Não lidar com erros e falhas podem levar a um código instável e um comportamento imprevisível.

## Valores de retorno

Muitas funções retornam valores de erro e sucesso. Você deve sempre verificar esses valores depois de fazer uma chamada. Por exemplo `get_post_meta` retorna um valor do campo personalizado, mas se esse campo personalizado / post meta não existe, ele retorna um valor de erro.

Diferentes APIs retornam diferentes valores de erro, e podem incluir:

 - `null` values
 - false
 - `WP_Error` objects

API WordPress chama no momento da escrita e não lança exceções. No entanto, se você chamar ações como `save_post` e lançar uma exceção, ele não pode ser capturado devido a essa expectativa, por isso não lance exceções a menos que você tenha certeza de que sabe o que está fazendo.

## `WP_Error`

O objeto `WP_Error` captura todos os objetos de mensagem de erro retornada por alguns APIs. Ele armazena internamente várias mensagens de erro e códigos de erro.

## `is_wp_error`

Este é um método útil para simplificar a verificação de erros. Ele verifica se um valor retornado era um objeto `WP_Error`, e também verifica para um punhado de outros valores de erro. Ele retorna um valor verdadeiro ou falso, permitindo verificações como estas:

Este é um método útil para simplificar a verificação de erros. Ele verifica se um valor retornado era um objeto `WP_Error`, mas não verifica se há outros valores de erro. Abreviação `if ( get_class( $variable ) == 'WP_Error' )`. Por exemplo:

```php
if ( !is_wp_error( $value ) ) {
    // fazer as coisas
} else {
    // Exibe um aviso para o usuário e abortar
}
```

Embora esta seja uma função útil, lembre-se, nem todas as API's retornam o mesmo valor de erro, e você deve verificar primeiro.
