## Avoid conditionals (Remember to do one thing)


### Problem
You have a conditional that performs various actions depending on object type or properties.

### Solution
Create subclasses matching the branches of the conditional. In them, create a shared method and move code from the corresponding branch of the conditional to it. Then replace the conditional with the relevant method call. The result is that the proper implementation will be attained via polymorphism depending on the object class.


```php
abstract class Bird {
  // ...
  abstract function getSpeed();
  // ...
}

class European extends Bird {
  public function getSpeed() {
    return $this->getBaseSpeed();
  }
}
class African extends Bird {
  public function getSpeed() {
    return $this->getBaseSpeed() - $this->getLoadFactor() * $this->numberOfCoconuts;
  }
}
class NorwegianBlue extends Bird {
  public function getSpeed() {
    return ($this->isNailed) ? 0 : $this->getBaseSpeed($this->voltage);
  }
}

// Somewhere in Client code.
$speed = $bird->getSpeed();
```

## Dead Code

Dead code is just as bad as duplicate code. There's no reason to keep it in your codebase. If it's not being called, get rid of it! It will still be safe in your version history if you still need it.

```php
function requestModule(string $url): void
{
    // ...
}

$request = requestModule($requestUrl);
inventoryTracker('apples', $request, 'www.inventory-awesome.io');
```

## Type Checking

PHP is untyped, which means your functions can take any type of argument. Sometimes you are bitten by this freedom and it becomes tempting to do type-checking in your functions. There are many ways to avoid having to do this. The first thing to consider is consistent APIs.

```php
function travelToTexas(Traveler $vehicle): void
{
    $vehicle->travelTo(new Location('texas'));
}

function combine($val1, $val2): int
{
    if (!is_numeric($val1) || !is_numeric($val2)) {
        throw new \Exception('Must be of type Number');
    }

    return $val1 + $val2;
}
```