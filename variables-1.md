## Use readable variable names
$ymdstr = $moment->format('y-m-d');

## Use the same vocabulary for the same type of variable
getUserInfo();
getUserData();
getUserRecord();
getUserProfile();

## Use searchable names
$result = $serializer->serialize($data, 448);

if ($user->access & 4) {
  // ...
}

## Use explanatory variables
$address = 'One Infinite Loop, Cupertino 95014';
$cityZipCodeRegex = '/^[^,]+,\s*(.+?)\s*(\d{5})$/';
preg_match($cityZipCodeRegex, $address, $matches);

saveCityZipCode($matches[1], $matches[2]);


## Avoid Mental Mapping (Explicit is better than implicit)

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

## Don't add unneeded context

class Car
{
    public $carMake;
    public $carModel;
    public $carColor;

    //...
}