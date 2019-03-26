## Don't use flags as function parameters

```php
function createFile(string $name, bool $temp = false): void
{
    if ($temp) {
        touch('./temp/'.$name);
    } else {
        touch($name);
    }
}
```

## Avoid negative conditionals

```php
function isSMSNotSelected(\Supporter $supporter): bool
{
    // ...
}

if (!isSMSNotSelected($supporter))
{
    // ...
}
```