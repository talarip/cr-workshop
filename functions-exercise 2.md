
## Functions should only be one level of abstraction

```php
// 
function parseBetterJSAlternative(string $code): void
{
    $regexes = [
        // ...
    ];

    $statements = explode(' ', $code);
    $tokens = [];
    foreach ($regexes as $regex) {
        foreach ($statements as $statement) {
             $tokens[] = /* ... */;
        }
    }

    $ast = [];
    foreach ($tokens as $token) {
        // lexify the tokens
        $ast[] = /* ... */;
    }

    foreach ($ast as $node) {
        // parse...
    }
}
```
