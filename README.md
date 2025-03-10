# php-oop-guide
## 📌 OOP in PHP

Welcome to the **Object-Oriented Programming (OOP) in PHP** guide! This document covers fundamental OOP principles with practical examples in PHP. Whether you're a beginner or looking to refresh your knowledge, this guide will help you master OOP concepts efficiently.

---

## 🚀 Key OOP Concepts in PHP

### 1️⃣ Classes and Objects

A **class** is a blueprint for creating objects. **Objects** are instances of classes that contain properties (variables) and methods (functions).

```php
class User {
  private $name;
  public $email;
  public $password;

  public function __construct($name, $email, $password) {
    $this->name = $name;
    $this->email = $email;
    $this->password = $password;
  }

  function getName() {
    return $this->name;
  }

  function login() {
    return "User $this->name is logged in.";
  }
}

$user1 = new User('John', 'john@gmail.com', '123456');
echo $user1->getName(); // Outputs: John
echo $user1->login(); // Outputs: User John is logged in.
```

---

### 2️⃣ Inheritance

Inheritance allows a class (child class) to inherit properties and methods from another class (parent class), promoting code reuse.

```php
class Employee extends User {
  public $title;

  public function __construct($name, $email, $password, $title) {
    parent::__construct($name, $email, $password);
    $this->title = $title;
  }

  public function getTitle() {
    return $this->title;
  }
}

$employee1 = new Employee('Alice', 'alice@gmail.com', '123456', 'Manager');
echo $employee1->getTitle(); // Outputs: Manager
```

---

### 3️⃣ The `final` Keyword

- Prevents a class from being inherited.
- Prevents methods from being overridden in child classes.

```php
final class FinalClass {
  // This class cannot be extended
}
```

---

### 4️⃣ Encapsulation

Encapsulation restricts direct access to object properties and ensures controlled data modification via methods.

```php
class User {
  private $name;
  private $email;
  private $password;

  public function __construct($name, $email, $password) {
    $this->name = $name;
    $this->email = $email;
    $this->password = $password;
  }

  public function getName() {
    return $this->name;
  }
}
```

---

### 5️⃣ Abstract Classes and Methods

Abstract classes contain at least one abstract method and cannot be instantiated directly.

```php
abstract class AbstractUser {
  protected $name;
  protected $email;
  protected $password;

  public function __construct($name, $email, $password) {
    $this->name = $name;
    $this->email = $email;
    $this->password = $password;
  }

  abstract public function login();
}

class User extends AbstractUser {
  public function login() {
    return "User $this->name is logged in.";
  }
}
```

---

### 6️⃣ Interfaces

Interfaces define methods that must be implemented by a class.

```php
interface Logger {
  public function log($message);
  public function error($message);
}

class FileLogger implements Logger {
  public function log($message) {
    echo "Log: $message";
  }

  public function error($message) {
    echo "Error: $message";
  }
}
```

---

### 7️⃣ Magic Methods

PHP provides predefined methods starting with `__` (double underscore) that perform special operations.

```php
class Iphone {
  public function __call($method, $params) {
    echo "Method $method not found.";
  }
}

$phone = new Iphone();
$phone->sayHello(); // Outputs: Method sayHello not found.
```

---

### 8️⃣ Cloning Objects

Cloning creates a copy of an object without affecting the original.

```php
class Phone {
  public $name;
  public function __construct($name) {
    $this->name = $name;
  }
}

$phone1 = new Phone('iPhone');
$phone2 = clone $phone1;
$phone2->name = 'Samsung';

echo $phone1->name; // Outputs: iPhone
```

---

### 9️⃣ Static Properties and Methods

Static methods and properties belong to a class rather than an instance.

```php
class MyClass {
  public static $counter = 0;

  public function __construct() {
    self::$counter++;
  }
}

echo MyClass::$counter; // Outputs: 0
$obj1 = new MyClass();
$obj2 = new MyClass();
echo MyClass::$counter; // Outputs: 2
```

---

### 🔟 Method Chaining

Method chaining allows multiple method calls on the same object.

```php
class MyClass {
  public function sayHi() {
    echo "Hi user.<br>";
    return $this;
  }

  public function sayHello() {
    echo "Hello user.<br>";
    return $this;
  }
}

$obj = new MyClass();
$obj->sayHi()->sayHello();
```

---

## 📢 Conclusion

OOP in PHP provides a structured approach to coding. Mastering these concepts will help you write **reusable, maintainable, and efficient** code.

🔹 **Happy Coding!** 🚀

---


## 📜 License

This project is open-source and available under the [MIT License](LICENSE).

