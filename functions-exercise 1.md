## Avoid conditionals (Remember to do one thing)
```php
class Bird {
  // ...
  public function getSpeed() {
    switch ($this->type) {
      case EUROPEAN:
        return $this->getBaseSpeed();
      case AFRICAN:
        return $this->getBaseSpeed() - $this->getLoadFactor() * $this->numberOfCoconuts;
      case NORWEGIAN_BLUE:
        return ($this->isNailed) ? 0 : $this->getBaseSpeed($this->voltage);
    }
    throw new Exception("Should be unreachable");
  }
  // ...
}
```

## Dead Code
```php
function oldRequestModule(string $url): void
{
    // ...
}

function newRequestModule(string $url): void
{
    // ...
}

$request = newRequestModule($requestUrl);
inventoryTracker('apples', $request, 'www.inventory-awesome.io');
```
