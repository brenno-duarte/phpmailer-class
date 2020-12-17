<p align="center">
  <a href="https://github.com/brenno-duarte/phpmailer-class/releases"><img alt="GitHub release (latest by date)" src="https://img.shields.io/github/v/release/brenno-duarte/phpmailer-class?style=flat-square"></a>
  <a href="https://github.com/brenno-duarte/phpmailer-class/blob/master/LICENSE"><img alt="GitHub" src="https://img.shields.io/github/license/brenno-duarte/phpmailer-class?style=flat-square"></a>
</p>

## Sobre

Classe genérica para o PHPMailer

## Instalação via Composer

```
composer brenno-duarte/phpmailer-class
```

## Inicializando

```php
define('PHPMAILER', [
    'HOST' => 'mail.YOUR_HOST.com.br',
    'USER' => 'contact@YOUR_HOST.com.br',
    'PASS' => 'YOUR_PASSWORD',
    'PORT' => '587',
    'SECURITY' => 'tls',
    'DEBUG' => '0'
]);

require_once 'vendor/autoload.php';

use PHPMailerClass\PHPMailerClass;

$mailer = new PHPMailerClass();
```

## Como usar

```php
// Adiciona informações de remetente e destinatário
$mailer->add('SENDER_EMAIL@gmail.com', 'SENDER NAME', 'RECIPIENT_EMAIL@gmail.com', 'RECIPIENT NAME');

// Envia um arquivo por email (OPCIONAL)
$mailer->attach('imagem.png', 'imagem_name');

// Envia uma imagem no HTML (OPCIONAL)
$mailer->embeddedImage('imagem.png', 'imagem', 'imagem');

// Envia o e-mail
$mailer->send('Teste de e-mail', '<h1>Teste de e-mail</h1><p>cid:imagem</p>');

// Caso haja algum erro
if ($mailer->error()) {
    echo $mailer->error();
}
```

## License

[MIT](https://github.com/brenno-duarte/phpmailer-class/blob/master/LICENSE)
