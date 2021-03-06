PHP Syntax Note
======

## General

- A PHP script starts with `<?php` and ends with `?>`. You can also use the shorthand PHP tags, `<?` and `?>`, as long as they're supported by the server.
- PHP statements end with semicolons `;`.
- Comment: single-line `//`, multi-line begins with `/*` and ends with `*/`.

## Variable and Constant

```php
$variable_name = 'value';
echo $variable_name; // 'value'

$var1 = 'var2';
$var2 = 'value';
echo $$var1; // 'value'
```

- A variable name can only contain alpha-numeric characters and underscores. (`A-z`, `0-9`, and `_`)
- A variable name must start with a letter or an underscore.
- Variable names are case-sensitive. (`$name` and `$NAME` would be two different variables)

```php
define(CONSTANT_NAME, `value`, `case-insensitive`);
echo CONSTANT_NAME;
```

- Constants are similar to variables except that they cannot be changed or undefined after they've been defined.
- name: Specifies the name of the constant.
- value: Specifies the value of the constant.
- case-insensitive: Specifies whether the constant name should be case-insensitive. Default is `false`.

## Operators

| Operator     | Example       | Note                                                         |
| ------------ | ------------- | ------------------------------------------------------------ |
| `+`          | `$a + $b`     | Addition. Supports `$a += $b`.                               |
| `-`          | `$a - $b`     | Subtraction. Supports `$a -= $b`.                            |
| `*`          | `$a * $b`     | Multiplication. Supports `$a *= $b`.                         |
| `/`          | `$a / $b`     | Division (**NOT** Truncation Division). Supports `$a /= $b`. `10 / 3 == 3.3333...` |
| `%`          | `$a % $b`     | Modulus. Supports `$a %= $b`. If you use floating point numbers with the modulus operator, they will be converted to **integers** before the operation. |
| `++`         | `$a++; ++$a;` | post-increment / pre-increment. The difference is that the post-increment returns the original value **before** it changes the variable, while the pre-increment changes the variable first and then returns the value. |
| `--`         | `$a--; --$a;` | post-decrement / pre-decrement.                              |
| `==`         | `$a == $b`    | Returns `true` if `$a` is equal to `$b`.                     |
| `===`        | `$a === $b`   | Returns `true` if `$a` is equal to `$b` and they are same type. |
| `!=`         | `$a != $b`    | Returns `true` if `$a` is **NOT** equal to `$b`. Same to `$a <> $b`. |
| `!==`        | `$a !== $b`   | Returns `true` if `$a` is **NOT** equal to `$b` **OR** they are **NOT** same type. |
| `>` / `>=`   | `$a > $b`     | Greater than (or equal to).                                  |
| `<` / `<=`   | `$a < $b`     | Less than (or equal to).                                     |
| `&&` / `and` | `$a && $b`    | Returns `true` if **both** `$a` and `$b` are `true`.         |
| `||` / `or`  | `$a || $b`    | Returns `true` if **either** `$a` and `$b` is `true`.        |
| `xor`        | `$a xor $b`   | Returns `true` if **either** `$a` and `$b` is `true`, but **NOT both**. |
| `!`          | `!$a`         | Returns `true` if `$a` is falsy.                             |

## Template

- `include`: continue if file was not found. `require`: throw error if file was not found.

## `String`

- `""` supports escape character and html tag, but `''` do NOT.

## `Array`

- Numeric Array: generic array; Associative Array: like a hashtable.

### Inited by values

```php
$arr = array('a', 'b', 'c');
echo $arr[0]; // 'a'
$arr[0] = 'd';
echo $arr[0]; // 'd'

$arr = array('a' => 1, 'b' => 2, 'c' => 3);
echo $arr['a']; // 1
$arr['a'] = 4;
echo $arr['a']; // 4
```

### Inited by size

```php
// 1d array
$arr = array_fill(0, 10, 1);
echo implode(',', $arr); // 1,1,1,1,1,1,1,1,1,1

// 2d array
$arr = array_fill(0, 5, array_fill(0, 5, 1));
echo $arr[0][0]; // 1
$arr[0][0] = 2;
echo $arr[0][0]; // 2

echo implode(',', $arr[0]); // 2,1,1,1,1
echo implode(',', $arr[1]); // 1,1,1,1,1
echo implode(',', $arr[2]); // 1,1,1,1,1
echo implode(',', $arr[3]); // 1,1,1,1,1
echo implode(',', $arr[4]); // 1,1,1,1,1
```
