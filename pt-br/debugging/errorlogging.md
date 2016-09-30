# Registro de erros

Existem vários tipos de registo de erros, mas são os mais básicos:

 - Exibição de erros no frontend
 - Escrever os erros em um arquivo de log
 - Não exibir nada em tudo

Em um ambiente de produção / live, é aconselhavel você escrever erros em um arquivo de log.

## Advertências vs Erros

Dependendo de como o PHP é configurado, os avisos também será mostrado. Um aviso é algo que não pára de correr PHP, mas indica um problema pode ter ocorrido. Por exemplo:

```php
$my_array = array(
    'alice' => 5,
    'bob' => 6
);
echo $my_array['eve'];
```

Aqui, estou inserindo a entrada 'eve' em `$my_array`, mas não existe essa entrada. PHP responde criando um valor vazio e registrar um aviso. Os avisos são indicadores de erros e enganos.

## Relatório de Erros PHP

Dependendo do que foi definido no seu `php.ini`, PHP terá um nível de relatório de erros. Tudo abaixo desse nível será ignorado ou considerado um aviso. Tudo acima será considerado um erro. Isso pode variar de servidor para servidor.

## O operador `@` 

Nunca use o operador `@`. Ele é usado para esconder erros e avisos em código, mas ele não faz o que as pessoas esperam que ele faça.

`@` Funciona definindo o nível de relatório de erro em um comando para que nenhum erro seja  registrado. Ele não impede que o erro aconteça, que é o que as pessoas esperam que ele faça. Isto pode significar erros fatais não são capturados ou logado. Evite usar o operador `@`, e tratar todas as instâncias com suspeita.
