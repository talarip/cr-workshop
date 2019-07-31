## Lookout for Bloaters

Long Method: A method contains too many lines of code

    Extract Method.

```php
    function printSupporterAccount() {
        $this->getSupporterDetails();

        // Print details.
        print("name:  " . $this->name);
        print("address " . $this->address);

        print("childname" . $this->getSupporterChild());
    }
```

    Replace Temp with Query,

```php
$basePrice = $this->quantity * $this->itemPrice;
if ($basePrice > 1000) {
  return $basePrice * 0.95;
} else {
  return $basePrice * 0.98;
}
```

    Introduce Parameter Object

```php
class Event {

    public function isValidEvent(Date $eventStartDate,  Date $eventEndDate)
    {
        # code...
    }
    public function getAllEvents(Date $eventStartDate,  Date $eventEndDate)
    {
        # code...
    }
    public function getEventsExpiredIn(Date $eventStartDate,  Date $eventEndDate)
    {
        # code...
    }
}
```

    Preserve Whole Object.

```php
$eventStartDate = $Event->startDate;
$eventendDate = $Event->endDate;
$eventID = $Event->ID;

$valid = $this->isValidEvent($eventID, $eventStartDate, $eventendDate)
```

    Replace Method with Method Object

```php
class Order {
  // ...
  public function price() {
    $primaryBasePrice = 10;
    $secondaryBasePrice = 20;
    $tertiaryBasePrice = 30;
    // Perform long computation.
  }
}
```

    Decompose Conditional

```php
if ($date->before(SUMMER_START) || $date->after(SUMMER_END)) {
  $charge = $quantity * $winterRate + $winterServiceCharge;
} else {
  $charge = $quantity * $summerRate;
}
```

Large Class: A class contains many fields/methods/lines of code.

    Extract Class
    Extract Subclass
    Extract Interface

Too many primary variables or fields

    Replace Data Value with Object.
    Introduce Parameter Object
    Preserve Whole Object.

    Lookout for Type Code:
        Replace Type Code with Class
        Replace Type Code with Subclasses
        Replace Type Code with State

    Replace Array with Object.

More than three or four parameters for a method.

Replace Parameter with Method Call
Preserve Whole Object.
Introduce Parameter Object.

Data bunches: Too many identical groups of variables

    Extract Class
    Introduce Parameter Object
    Preserve Whole Object.
