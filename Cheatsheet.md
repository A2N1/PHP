# PHP Cheat Sheet – COMPLETE LEARNING VERSION 📘 (PHP 8+)

This cheat sheet covers **core PHP concepts**, syntax, functions, arrays, OOP, and modern PHP features.  
Suitable for beginners and refreshers (Backend / Web).

---

## Table of Contents

- [PHP Cheat Sheet – COMPLETE LEARNING VERSION 📘 (PHP 8+)](#php-cheat-sheet--complete-learning-version--php-8)
  - [Table of Contents](#table-of-contents)
  - [1. Basics](#1-basics)
  - [2. Variables \& Data Types](#2-variables--data-types)
  - [3. Operators](#3-operators)
  - [4. Control Structures](#4-control-structures)
  - [5. Functions](#5-functions)
  - [6. Arrays](#6-arrays)
  - [7. Strings](#7-strings)
  - [8. Associative Arrays](#8-associative-arrays)
  - [9. Loops](#9-loops)
  - [10. Superglobals](#10-superglobals)
  - [11. Forms \& Input](#11-forms--input)
  - [12. File Handling](#12-file-handling)
  - [13. Object-Oriented PHP](#13-object-oriented-php)
  - [14. Namespaces \& Autoloading](#14-namespaces--autoloading)
  - [15. Error Handling](#15-error-handling)
  - [16. Sessions \& Cookies](#16-sessions--cookies)
  - [17. Database (PDO)](#17-database-pdo)
  - [18. Modern PHP Features](#18-modern-php-features)
  - [19. Security Basics](#19-security-basics)
  - [20. Best Practices](#20-best-practices)
  - [End](#end)

---

## 1. Basics

~~~php
<?php
// PHP code is executed on the server

echo "Hello World";        // Output
print "Hello World";       // Also output

// Comments
// single-line
# single-line
/* multi-line */
~~~

---

## 2. Variables & Data Types

~~~php
// Variables always start with $
$name = "Max";
$age = 30;
$isActive = true;

// Data types
$string = "text";
$number = 42;
$float = 3.14;
$bool = false;
$null = null;

// Type checking
var_dump($age);    // int(30)
gettype($name);    // string
~~~

---

## 3. Operators

~~~php
// Arithmetic
5 + 3;   // 8
5 - 3;   // 2
5 * 3;   // 15
5 / 2;   // 2.5
5 % 2;   // 1

// Comparison
1 == "1";   // true
1 === "1";  // false (type-safe)
1 != 2;
1 !== "1";

// Logical
true && false;
true || false;
!true;

// Null coalescing
$username = $_GET["user"] ?? "Guest";
~~~

---

## 4. Control Structures

~~~php
$score = 85;

if ($score > 90) {
    $grade = "A";
} elseif ($score > 80) {
    $grade = "B";
} else {
    $grade = "C";
}

// Switch
$role = "admin";
switch ($role) {
    case "admin":
        echo "Admin";
        break;
    default:
        echo "User";
}
~~~

---

## 5. Functions

~~~php
// Function definition
function add(int $a, int $b): int {
    return $a + $b;
}

echo add(2, 3); // 5

// Default parameters
function greet(string $name = "Guest"): string {
    return "Hello $name";
}

// Variadic function
function sum(int ...$numbers): int {
    return array_sum($numbers);
}
~~~

---

## 6. Arrays

~~~php
// Indexed array
$numbers = [1, 2, 3];

// Add / remove
array_push($numbers, 4);
array_pop($numbers);

// Access
echo $numbers[0]; // 1
~~~

---

## 7. Strings

~~~php
$text = "Hello";

// Concatenation
$text .= " World";

// Length
strlen($text);

// Replace
str_replace("World", "PHP", $text);

// String interpolation
$name = "Max";
echo "Hello $name";
~~~

---

## 8. Associative Arrays

~~~php
$user = [
    "name" => "Max",
    "age" => 30
];

// Access
echo $user["name"];

// Keys & values
array_keys($user);
array_values($user);
~~~

---

## 9. Loops

~~~php
// for loop
for ($i = 0; $i < 3; $i++) {
    echo $i;
}

// while
$i = 0;
while ($i < 3) {
    echo $i;
    $i++;
}

// foreach
foreach ($user as $key => $value) {
    echo "$key: $value";
}
~~~

---

## 10. Superglobals

~~~php
$_GET;
$_POST;
$_REQUEST;
$_SERVER;
$_FILES;
$_COOKIE;
$_SESSION;
$_ENV;
~~~

---

## 11. Forms & Input

~~~php
// Access form data
$name = $_POST["name"] ?? "";

// Sanitize input
$name = htmlspecialchars($name);
~~~

---

## 12. File Handling

~~~php
// Read file
$content = file_get_contents("file.txt");

// Write file
file_put_contents("file.txt", "Hello");

// Check file
file_exists("file.txt");
~~~

---

## 13. Object-Oriented PHP

~~~php
class Person {
    public string $name;

    public function __construct(string $name) {
        $this->name = $name;
    }

    public function greet(): string {
        return "Hello " . $this->name;
    }
}

class Student extends Person {
    public function study(): string {
        return "Studying";
    }
}

$p = new Student("Anna");
echo $p->greet();
~~~

---

## 14. Namespaces & Autoloading

~~~php
namespace App\Models;

class User {}
~~~

~~~php
use App\Models\User;

$user = new User();
~~~

---

## 15. Error Handling

~~~php
try {
    throw new Exception("Something went wrong");
} catch (Exception $e) {
    echo $e->getMessage();
} finally {
    echo "Done";
}
~~~

---

## 16. Sessions & Cookies

~~~php
// Sessions
session_start();
$_SESSION["user"] = "Max";

// Cookies
setcookie("theme", "dark", time() + 3600);
~~~

---

## 17. Database (PDO)

~~~php
$pdo = new PDO("mysql:host=localhost;dbname=test", "user", "pass");

// Prepared statement
$stmt = $pdo->prepare("SELECT * FROM users WHERE id = :id");
$stmt->execute(["id" => 1]);
$data = $stmt->fetch();
~~~

---

## 18. Modern PHP Features

~~~php
// Arrow function
$double = fn($x) => $x * 2;

// Typed properties
class Example {
    public int $count = 0;
}

// Match expression (PHP 8)
$result = match($role) {
    "admin" => "Admin",
    default => "User"
};
~~~

---

## 19. Security Basics

~~~php
// Password hashing
$passwordHash = password_hash("secret", PASSWORD_DEFAULT);

// Verify password
password_verify("secret", $passwordHash);

// Prevent SQL injection → always use prepared statements
~~~

---

## 20. Best Practices

- Always use strict types: `declare(strict_types=1);`
- Use prepared statements (PDO)
- Escape user input
- Avoid global variables
- Separate logic and presentation
- Use modern PHP (8+)
- Follow PSR standards

---

## End
