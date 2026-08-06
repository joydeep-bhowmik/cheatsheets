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
RewriteEngine On

# Skip if already requesting /public
RewriteCond %{REQUEST_URI} !^/public/

# Redirect everything to /public
RewriteRule ^(.*)$ /public/$1 [L]

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
