```php
<?php

$source = __DIR__ . '/../swapnaporiagt.in/public';
$dest   = __DIR__ . '/../public_html';

$items = scandir($source);

foreach ($items as $item) {

    if ($item === '.' || $item === '..') {
        continue;
    }

    $target = $source . '/' . $item;
    $link   = $dest . '/' . $item;

    if (file_exists($link) || is_link($link)) {
        continue;
    }

    if (symlink($target, $link)) {
        echo "Linked: $item\n";
    } else {
        echo "Failed: $item\n";
    }
}

unlink(__FILE__);
```
