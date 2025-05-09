---
Title: 'Modulo'
Description: 'Returns the remainder after division of one number by another.'
Subjects:
  - 'Computer Science'
  - 'Data Science'
Tags:
  - 'Arithmetic'
  - 'Comparison'
  - 'Math'
  - 'Operators'
CatalogContent:
  - 'learn-python-3'
  - 'paths/computer-science'
---

The **modulo operator** (`%`) in Python calculates the remainder of a division operation between two operands. When one number is divided by another, the modulo operation returns what remains after the division is performed.

The modulo operator is used in various programming scenarios including checking for even or odd numbers, implementing cyclic behavior, formatting data, and cryptographic applications. It's a fundamental mathematical operation that helps solve problems where you need to work with remainders or create repeating patterns. In Python, the modulo operator works with different numeric types and offers uniquely consistent behavior with negative numbers compared to some other programming languages.

## Syntax

```pseudo
a % b
```

**Parameters:**

- `a`: The dividend (the value being divided)
- `b`: The divisor (the value dividing the dividend)

**Return value:**

The modulo operator returns the remainder of dividing `a` by `b`. The result will have the same sign as the divisor `b` in Python.

## Example 1: Modulo with Different Numeric Types

The following code demonstrates how the modulo operator works with integers, floats, and negative numbers:

```py
# Modulo with integers
print(15 % 4)

# Modulo with floats
print(10.5 % 2.2)

# Modulo with negative operands
print(-7 % 3)
print(7 % -3)
```

This code generates the following output:

```shell
3
1.6999999999999993
2
-2
```

The output shows that modulo returns the remainder after division for each type of number. Python's modulo operation with negative numbers always returns a result with the same sign as the divisor.

## Example 2: Checking for Even and Odd Numbers

This example shows how to determine if a number is even or odd using the modulo operator:

```py
def check_parity(number):
  if number % 2 == 0:
    return f"{number} is an even number"
  else:
    return f"{number} is an odd number"

# Testing the function with various numbers
print(check_parity(4))
print(check_parity(7))
print(check_parity(0))
print(check_parity(-5))
```

The output generated by the code above is:

```shell
4 is an even number
7 is an odd number
0 is an even number
-5 is an odd number
```

The function works by checking if the remainder after dividing by 2 is zero(even) or not(odd). This technique is fundamental in programming for alternating actions, filtering data, or implementing algorithms that behave differently for even and odd values.

## Codebyte Example: Creating a Time Converter

The code here uses modulo to convert total minutes into hours and minutes format:

```codebyte/python
def convert_minutes_to_hours_and_minutes(total_minutes):
  hours = total_minutes // 60
  minutes = total_minutes % 60

  hour_text = "hour" if hours == 1 else "hours"
  minute_text = "minute" if minutes == 1 else "minutes"

  return f"{total_minutes} minutes = {hours} {hour_text} and {minutes} {minute_text}"

# Test the function with different values
print(convert_minutes_to_hours_and_minutes(90))
print(convert_minutes_to_hours_and_minutes(125))
print(convert_minutes_to_hours_and_minutes(60))
print(convert_minutes_to_hours_and_minutes(45))
```

The modulo operator finds the remaining minutes while integer division calculates the complete hours. This pattern of converting between units is common in applications dealing with time, distance, currency, and other measurements that use different scales.

## Best Practices

1. **Use for Checking Divisibility**: The modulo operator is ideal for checking if a number is divisible by another.

   ```py
   # Check if number is divisible by 3
   if number % 3 == 0:
     print(f"{number} is divisible by 3")
   ```

2. **Use for Cycling Through Values**: The modulo operator helps implement cyclic behavior.

   ```py
   # To cycle through array indices
   next_index = (current_index + 1) % array_length
   ```

3. **Prefer Integer Modulo**: When possible, use modulo with integers for more predictable results.

4. **Handle Negative Inputs Carefully**: Be aware of how modulo treats negative numbers in Python, as it differs from some other programming languages.

5. **Combine with Floor Division**: When you need both the quotient and remainder, use floor division (`//`) and modulo together.

   ```py
   quotient = a // b
   remainder = a % b
   ```

6. **Use `divmod()` for Combined Operations**: Python provides a built-in function [`divmod()`](https://www.codecademy.com/resources/docs/python/built-in-functions/divmod) that returns both the quotient and remainder as a tuple.

   ```py
   quotient, remainder = divmod(a, b)
   ```
