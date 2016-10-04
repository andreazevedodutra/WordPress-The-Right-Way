# Tools

Ferramentas de depuração se dividem em duas categorias:

 - Ferramentas para diagnosticar problemas quando eles surgem e revelam problemas
 - Ferramentas para evitar que advertências e erros aconteçam

O velho ditado ainda se aplica: **é melhor prevenir do que remediar**

## Ferramentas de Depuração / Plugins

Instalando o plugin [Developer](https://wordpress.org/plugins/developer/) a partir do repositório WordPress vai lhe dar acesso rápido a uma ampla gama de ferramentas de depuração. Os seguintes plugins de depuração são bastante úteis:

 - [Log Deprecated Notices](https://wordpress.org/plugins/log-deprecated-notices/) Avisos através de Logs sobre o uso de funções obsoletas.
 - [Debug Bar](http://wordpress.org/plugins/debug-bar) Fornece uma interface para a depuração de PHP Notificações/Avisos/Erros, revendo SQL Queries, analisando o comportamento de armazenamento em cache e muito mais. Também é extensível com plugins.
 - [Debug Console](https://wordpress.org/plugins/debug-bar-console/) O Console de Depuração, é realmente útil.
 - [Query Monitor](https://wordpress.org/plugins/query-monitor/) Visualizar informações de depuração e desempenho em consultas de banco de dados, os ganchos, condicionais solicitações HTTP, redirecionamentos e mais.

### Xdebug e depuração remota
O [Xdebug](http://xdebug.org/index.php) PHP Extension  permite a depuração aumentada, função e método de rastreamento, e mostrar o perfil de aplicações PHP. Ele é [instalado  com VVV e pode ser ligado/desligado.](https://github.com/Varying-Vagrant-Vagrants/VVV/wiki/Code-Debugging#meet-xdebug).

Com [PHPStorm](https://www.jetbrains.com/phpstorm/), você pode instalar uma extensão do navegador para acessar Xdebug (or [Zend Debugger](http://files.zend.com/help/Zend-Studio/zend-studio.htm#debugging_php_in_zend_studio.htm)) de dentro da IDE.

Em vez de adicionar manualmente declarações `var_dump` e recarregar a página, você pode adicionar um ponto de interrupção em qualquer lugar em seu código PHP, a execução irá parar e você pode ver um rastreamento de pilha, inspeccionar (e modificar) os valores de todas as variáveis e objetos ou manualmente avaliar (testar) uma expressão PHP.

Com [zero-configuration debugging](http://confluence.jetbrains.com/display/PhpStorm/Zero-configuration+Web+Application+Debugging+with+Xdebug+and+PhpStorm) (controlado através de cookies e bookmarklets) você não precisa acrescentar `?XDEBUG_SESSION_START` aos seus URLs e pode ainda depurar solicitações de HTTP POST.

### PHP Debuggers
- [DBG](http://www.php-debugger.com/) - PHP Debugger and Profiler

### Os inspectores de navegação Web
- [Chrome DevTools](http://discover-devtools.codeschool.com/) para Google Chrome
- [Firebug](http://getfirebug.com/) para Mozilla Firefox
- [F12 developer tools](http://msdn.microsoft.com/library/ie/bg182326) para Internet Explorer
- [Opera Dragonfly](http://www.opera.com/dragonfly/) para Opera

## Prevenção

Há uma série de ferramentas dedicados à análise de código e captura erros semânticos, ou apontar problemas no código.

[PHP Mess Detector](http://phpmd.org/) por exemplo, irá destacar nomes longos de variáveis, nPath e complexidade ciclomática, classes que são demasiado grandes, variáveis não utilizadas, e outros problemas. [SCheck](https://github.com/facebook/pfff/wiki/Scheck) é uma ferramenta fornecida pelo Facebook, e realiza verificações semelhantes, tais como encontrar declarações mortos e classes não utilizadas.

Você pode fazer uso de uma ferramenta como o  [phantm](https://github.com/colder/phantm/) para inferir tipos e encontrar confrontos. Muitos outros existem, porém, ele integrar-se com o seu editor / IDE, para melhor visualização
