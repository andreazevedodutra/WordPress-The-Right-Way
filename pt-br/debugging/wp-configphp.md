# Constantes de `wp-config.php`

Atualmente, existem várias constantes do PHP no `wp-config.php` que lhe permitirá melhorar o seu código WordPress e ajudá-lo a depurar.

---

### `WP_DEBUG`
Esta é uma opção incluída na [WordPress version 2.3.1](http://codex.wordpress.org/Version_2.3.1).

Por padrão, este será definido para `false` o que impedirá avisos e erros de ser mostrado, mas **todos os desenvolvedores do WordPress devem ter essa opção ativa**.

#### Ativa os logs
```php
define( 'WP_DEBUG', true );
```

#### Desativa os Logs
```php
define( 'WP_DEBUG', false );
```
_Check que os valores devem ser **bool** ao invés de **string**_

Um patch menor depois, o on [Wordpress version 2.3.2](http://codex.wordpress.org/Version_2.3.2), o sistema nos permitiu ter um controle mais acertivo sobre os logs de erros de banco de dados.

Mais tarde, na versão 2.5, WordPress levantou a [error reporting](http://www.php.net/error-reporting) a nível E_ALL, que permitirá ver os logs para os avisos e mensagens de descontinuação.

###### _Notes:_

Se você tiver essa opção ativada, você poderá encontrar problemas com solicitações de AJAX, este problema está relacionado com Avisos sido impresso na saída da resposta AJAX, que **
vai quebrar o XML e JSON**.

#### `WP_DEBUG_LOG`
Quando você usa `WP_DEBUG` definido como `true` você tem acesso a essa constante, e isso vai permitir que você registrar seus avisos e advertências para um arquivo.

#### `WP_DEBUG_DISPLAY`
Quando você usa `WP_DEBUG` definido como `true` você tem acesso a essa constante, com ele você pode optar por exibir ou não os avisos e avisos na tela.

###### Note:
Se essas variáveis não produzir o resultado que você está esperando verificar o [Codex Section about ways to setup your logging](http://codex.wordpress.org/Editing_wp-config.php#Configure_Error_Logging).

---

### `SCRIPT_DEBUG`
Quando você tem um plugin para WordPress ou tema que está incluindo a versão minified do seu arquivos CSS ou JavaScript, por padrão, você está fazendo errado!

Seguindo a idéia WordPress de criar um arquivo para o desenvolvimento e sua versão minified é muito boa e você deve ter ambos os arquivos no seu plug-in, e com base nesta variável que vai enfileirar um ou o outro.

Por padrão esta constante será definida para `false`, e se você quer ser capaz de depurar arquivos CSS ou JavaScript a partir do WordPress você deve transformá-lo para `true`.

#### Ativa os logs
```php
define( 'SCRIPT_DEBUG', true );
```
_Check que os valores devem ser **bool** ao invés de **string**_

Arquivos padrão do WordPress `wp-includes` e `wp-admin` será definido para a sua versão de desenvolvimento se definido como `true`.

### `CONCATENATE_SCRIPTS`
Em sua administração WordPress você vai ter todos os seus arquivos JavaScript concatenados para um único pedido com base nas dependências e prioridade de enfileiramento.

Para remover esse recurso pode definir esta constante para `false`.
```php
define( 'CONCATENATE_SCRIPTS', false );
```

---

### `SAVEQUERIES`
Quando você está lidando com o banco de dados você pode querer salvar suas consultas para que você possa depurar o que está acontecendo dentro do seu plugin ou tema.

**Make `$wpdb` save Queries**
```php
define( 'SAVEQUERIES', true );
```
_**Note:** isso irá desacelerar seu WordPress_
