
![[00-Index-of-Python-Fundamentals]]

# Booleans

Booleans represent one of two values: `True` or `False`.

---

## Boolean Values

In programming you often need to know if an expression is `True` or `False`.

You can evaluate any expression in Python, and get one of two answers, `True` or `False`.

When you compare two values, the expression is evaluated and Python returns the Boolean answer:

> PYTHON CODE : BOOLEANS
```python
# When you compare two values, the expression is evaluated and Python returns the Boolean answer

print("Is '10' greater than '9' :",10 > 9)

print("Is '10' equals to 9, just assuming : ", 10 == 9)

print("Is '10' less than '9' : ", 10 < 9 )

```
> OUTPUT
```
Is '10' greater than '9' : True
Is '10' equals to 9, just assuming :  False
Is '10' less than '9' :   False
```


When you run a condition in an if statement, Python returns `True` or `False`:
> PYTHON CODE : EVALUATING A CONDITIONAL STATEMENTS
```python
# Print a message based on whether the condition is True or False:

a = 440
b = 44

msg = ("Checking if 'b > a' : ")
if b > a :
	result = ("'b' is greater than a ")
else:
	result = ("'b' is not greater than 'a'")
print(msg + result)

```
> OUTPUT
``` 
Checking if 'b > a' : 'b' is not greater than 'a'      
```

---
## Evaluate Values and Variables
 The `bool()` function allows you to evaluate any value, and give you `True` or `False` in return.

| Data-Type | `TRUE`                                | `FALSE`       |
| --------- | ------------------------------------- | ------------- |
| String    | `bool("Hello")`                       | `bool("")`    |
| Integer   | `bool(18)`                            | `bool(0)`     |
| List      | `bool(["apple", "cherry", "banana"])` | `bool([])`    |
|           |                                       | `bool(False)` |
|           |                                       | `bool(None)`  |
|           |                                       | `bool(())`    |
|           |                                       | `bool({})`    |

| Most Values are True                                                    | Some Values are False                                                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Almost any value is evaluated to `True` if it has some sort of content. | In fact, there are not many values that evaluate to `False`, except empty values, such as `()`, `[]`, `{}`, `""`, |
| Any string is `True`, except empty strings.                             | Empty Strings : `""`                                                                                              |
| Any number is `True`, except `0`                                        | the number `0`, and the value `None`                                                                              |
| Any list, tuple, set, and dictionary are `True`, except empty ones.     |                                                                                                                   |
