```php
<?php

$link = __DIR__ . '/public';
$target = __DIR__ . '/../site/public';

try {
    if (!is_link($link) && !file_exists($link)) {

        set_error_handler(function ($severity, $message) {
            throw new ErrorException($message, 0, $severity);
        });

        symlink($target, $link);

        restore_error_handler();

        echo "Symbolic link created successfully.";
        return;
    }

    echo "Symbolic link already exists.";
} catch (Throwable $e) {
    restore_error_handler();
    echo "Error creating symbolic link: " . $e->getMessage();
}
```

```
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteRule ^(.*)$ public/$1 [L]
</IfModule>


```

```env
MAIL_MAILER=smtp
MAIL_HOST=mail.domain.com
MAIL_PORT=465
MAIL_USERNAME=support@domain.com
MAIL_PASSWORD=password
MAIL_ENCRYPTION=ssl
MAIL_FROM_ADDRESS="support@domain.com"
MAIL_FROM_NAME="${APP_NAME}"
```
