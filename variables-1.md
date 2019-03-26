## Use readable variable names
```php
$ymdstr = $moment->format('y-m-d');
```

## Use the same vocabulary for the same type of variable
```php
getUserInfo();
getUserData();
getUserRecord();
getUserProfile();
```

## Use searchable names
```php
$result = $serializer->serialize($data, 448);

if ($user->access & 4) {
  // ...
}
```
## Use explanatory variables

```php
$address = 'One Infinite Loop, Cupertino 95014';
$cityZipCodeRegex = '/^[^,]+,\s*(.+?)\s*(\d{5})$/';
preg_match($cityZipCodeRegex, $address, $matches);

saveCityZipCode($matches[1], $matches[2]);
```

## Avoid Mental Mapping (Explicit is better than implicit)
```php
$l = ['Austin', 'New York', 'San Francisco'];

for ($i = 0; $i < count($l); $i++) {
    $li = $l[$i];
    doStuff();
    doSomeOtherStuff();
    // ...
    // ...
    // ...
    // Wait, what is `$li` for again?
    dispatch($li);
}
```
## Don't add unneeded context

```php
class Car
{
    public $carMake;
    public $carModel;
    public $carColor;

    //...
}
```
