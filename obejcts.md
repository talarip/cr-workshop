## Object encapsulation

class BankAccount
{
    public $balance = 1000;
}

$bankAccount = new BankAccount();

// Buy shoes...
$bankAccount->balance -= 100;

## Make objects have private/protected members

class Employee
{
    public $name;

    public function __construct(string $name)
    {
        $this->name = $name;
    }
}

$employee = new Employee('John Doe');
echo 'Employee name: '.$employee->name; // Employee name: John Doe

## Jenga Effect https://www.urbandictionary.com/define.php?term=Jengaphobia&defid=2494196

