## Functions should do one thing

```php
function emailClients(array $clients)
{
    foreach ($clients as $client) {
        $clientRecord = $db->find($client);
        if ($clientRecord->isActive()) {
            email($client);
        }
    }
}
```
## Function names should say what they do

```php
class Email
{
    //...

    public function handle(): void
    {
        mail($this->to, $this->subject, $this->body);
    }
}

$message = new Email(...);
$message->handle();
```

## Type Checking
```php
function travelToTexas($vehicle): void
{
    if ($vehicle instanceof Bicycle) {
        $vehicle->pedalTo(new Location('texas'));
    } elseif ($vehicle instanceof Car) {
        $vehicle->driveTo(new Location('texas'));
    }
}

function combine($val1, $val2): int
{
    if (!is_numeric($val1) || !is_numeric($val2)) {
        throw new \Exception('Must be of type Number');
    }

    return $val1 + $val2;
}
```