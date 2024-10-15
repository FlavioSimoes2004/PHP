# PHP: INTRODUCTION
```php
<?php
echo "Hello World!";
```
- This part '<?php' denotes that we are beginning our PHP code. The closing tag is not longer required
- 'echo' is to output something

```php
<?php
// a simple comment

echo "Hello World!";

/* a multi line
comment */
```

```php
echo "She said "hi" to the dog."; //syntax error, unexpected 'hi' (T_STRING)

echo "She said \"hi\" to the dog."; // Prints: She said "hi" to the dog.
```

## STRING CONCATENATION
```php
<?php
echo "one" . "two"; // prints: onetwo
echo "one " . "two"; // prints: one two
```

## CREATING VARIABLES
```php
<?php
$name = "Seila";
echo "The name is " . $name; // prints: The name is Seila
```
OR
```php
<?php
$name = "Seila";
echo "The name is $name"; // prints: The name is Seila
```
OR
```php
<?php
$color = "brown";
echo "${color}ish hair"; // prints: brownish hair
```
OR
```php
<?php
$integer = 10;
$float = 9.9;
```

## VARIABLE REASSIGNMENT
```php
<?php
$var1 = "opa";
echo $var1;

$var2 = $var1;
$var1 = "eita";

echo $var1; // prints: eita
echo $var2; // prints: opa
```

## CONCATENATING ASSIGNMENT OPERATOR
```php
$full_name = "Seila " . "Opa";
echo $full_name; // Seila Opa

$fullname2 = "Seila";
$fullname2 = $full_name2 . " Opa";
echo $full_name2; // Seila Opa

$full_name3 = "Seila";
$full_name3 .= " Opa";
echo $full_name3; // Seila Opa
```

## ASSIGN BY REFERENCE
acts as a pointer, just like C language.
```php
<?php
$first_player_rank = "Beginner";
$second_player_rank =& $first_player_rank; 
echo $second_player_rank; // Prints: Beginner

$first_player_rank = "Intermediate"; // Reassign the value of $first_player_rank
echo $second_player_rank; // Prints: Intermediate

$second_player_rank .= " aaa";
echo $first_player_rank; // Prints: Intermediate aaa
```

## ADDITION AND SUBTRACTION
```php
<?php
echo 5 + 1;
echo 1.1 + 0.9;
echo 5 - 1;
echo -10.1 - 9.5;
```

## USING NUMBER VARIABLES
```php
<?php
$pedro_age = 30;
$joao_age = 21;
$difference_age = $pedro_age - $joao_age;
echo $difference_age; // prints: 9

$fav_num = 7;
echo $fav_num + 1; // prints: 8
echo $fav_num; // prints: 7

$fav_num = $fav_num + 2;
echo $fav_num; // prints: 9
```

## MULTIPLICATION AND DIVISION
```php
<?php
echo 2 * 3; // prints: 6
echo -21 / 7; // prints: -3
```

## EXPONENTIATION
```php
<?php
echo 5 ** 2; // prints: 25
echo 10 ** -2; // prints: 0.01
echo 3 * * 4; // will result in a error
```

## MODULO (REST OF DIVISION)
```php
echo 7 % 3; // prints: 1

$students = 27;
$groups = 4;
$left_students = $students % $groups;
echo $left_students; // prints: 3
```
The modulo operator (%) will convert its operands to integers before performing the operation. This means 7.9 % 3.8 will perform the same calculation as 7 % 3—both operations will return 1.

## ORDER OF OPERATION
```php
<?php
echo 1 + 20 * 2; // prints: 41
echo 2 + 20 / 2; // prints: 11
echo (4 + 20) / 2; // prints: 12
```

## MATHEMATICAL ASSIGNMENTS OPERATORS
```php
<?php
$my_num = 100;
$my_num--;
echo $my_num; // prints: 99

$my_num++;
echo $my_num; // prints: 100
/*
Also contains:
+=
-=
*=
/=
%=
*/
```

## DEFINING FUNCTIONS
```php
<?php
function teste(){
    echo "Hello World";
}

teste(); // prints: Hello World
```

### RETURN STATEMENTS
```php
function getString(){
    return "Ola";
}

$str = getString();
echo $str; // prints: Ola

function zero(){
    return 0;
}
echo zero() + 1; // prints: 1
```

### RETURNING NULL VALUE
```php
function returnNull(){
    echo "seila";
    // there is not return inside this function
}
$var = returnNull();
echo $var; // nothing is printed
```

### PARAMETERS
```php
function printString($string){
    echo $string;
}
printString("Hello World");

function sum($x, $y){
    return $x + $y;
}
```

### DEFAULT PARAMETERS
```php
function printName($name = "John Doe"){
    echo $name;
}

printName(); // prints: John Doe
printName("Seila"); // prints: Seila
```

### PASS BY REFERENCE
```php
function addDot(&$str){
    $str .= ".";
}
$word = "Hello";
addDot($word);
echo $word; // prints: Hello.
```

## VARIABLE SCOPE (GLOBAL VARIABLES)
```php
$x = 10;
function sum($y){
    global $x;
    return $x + $y;
}
```

## GET VARIABLES TYPE
```php
$str = "ola";
$num = 10;

echo gettype($str); // prints: string
echo gettype($num); // prints: integer
```

## VAR_DUMP FUNCTION
```php
$str = "ola";
$num = 100;
echo var_dump($str); // prints: string(3) "ola"
echo var_dump($num); // prints: int(100)
```

## STRING FUNCTIONS
```php
echo strrev("hello"); // prints: olleh

echo strtolower("heLLo"); // prints: hello

echo str_repeat("hi ", 3); // prints hi hi hi 

echo str_pad("hi", 8, "-", STR_PAD_BOTH); // prints: ---hi---
```

## WORKING WITH SUBSTRINGS
```php
$str = "hi hi hi";
echo substr_count($str, "hi"); // prints: 3
```

## NUMBER FUNCTIONS
```php
echo abs(-2); // prints: 2

echo round(999.1) // prints: 999
echo round(999.9) // prints: 1000
```

## RANDOM NUMBERS
```php
echo getrandmax(); // prints: the maximun random number possible

echo rand(1, 2); // prints: 1 or 2
echo rand(5, 10); // prints: a number between 5 or 10, including 5 and 10
echo rand(1, 100); // prints: a number between 1 and 100, including 1 and 100
```

## CONDITIONAL AND LOGIC
```php
<?php
$bool = TRUE; //OR FALSE
if($bool)
{
    echo "IS TRUE";
}
else
{
    echo "IS FALSE";
}
```
