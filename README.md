Monolog Stdout Handler
======================
[![Latest Stable Version](https://poser.pugx.org/kmelia/monolog-stdout-handler/v/stable.png)](https://packagist.org/packages/kmelia/monolog-stdout-handler)

Provides a handler for [Monolog][1] that sends colored messages to stdout.
Messages may be uncolored with a provided formatter.

Loggers are able to interprete a balise language (like bbcode)
Balises currently recognized are :

 * `[c=<color>]...[/c]` with color: `black`, `blue`, `green`, `cyan`, `red`, `purple`, `yellow`, `white`

Example
-------
use `StdoutHandler`
```php
use Monolog\Logger;
use Monolog\Handler\StdoutHandler;

$stdoutHandler = new StdoutHandler();
$logger = new Logger('cronjob');
$logger->pushHandler($stdoutHandler);

$logger->error('[c=green]Hello world![/c]');
```

remove colored formatter
```php
use Monolog\Formatter\NoColorLineFormatter;
  
$stdoutHandler->setFormatter(new NoColorLineFormatter(StdoutHandler::FORMAT));
```


  [1]: https://github.com/Seldaek/monolog
