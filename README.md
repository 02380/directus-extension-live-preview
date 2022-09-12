# Introduction
A [Directus](https://github.com/directus/directus) extension for automatically calculating the value of a field based on other fields of the same item, on the client side.

- **Support templating, arithmetic operations**. Concat strings, sum, subtract, multiply, modulo, convert to slug, currency, etc.
- **Can be used as an alias field**.
- **Calculation is performed on the client side**, so it would not work if the item is created/updated via direct API calls or hooks.

# Syntax
## Examples
Sum 2 numbers:
```
{{ SUM(a, b) }}
```

Multiply 2 numbers:
```
{{ MULTIPLY(a, b) }}
```

Convert string to slug:
```
{{ SLUG(title) }}
```

Text interpolation:
```
{{ SLUG(title) }}-{{ id }}
```

Complex calculation:
```
{{ SUM(MULTIPLY(2, x), b) }}
```

## Availables operators

Operator | Description
--- | ---
SUM(a, b) | sum
SUBTRACT(a, b) | subtract
MULTIPLY(a, b) | multiply
DIVIDE(a, b) | divide
REMAINDER(a, b) | remainder
ROUND(a, n) | round number `a` to `n` number of decimals
CONCAT(a, b) | concat 2 strings
INT(a) | convert to integer
FLOAT(a) | convert to float
STRING(a) | convert to string
SLUG(a) | transform a string to a slug
CURRENCY(a) | format number a to currency

# Limitation
- Cannot parse literal strings.
- Cannot use relational fields, such as `{{ user.name }}`