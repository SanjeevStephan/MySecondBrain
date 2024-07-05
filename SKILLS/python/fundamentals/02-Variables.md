![[00-Index-of-Python-Fundamentals]]

## Variables

Variables are containers for storing data values.

---

## Creating Variables

Python has no command for declaring a variable.

A variable is created the moment you first assign a value to it.

```python
# Declare Variables

x = 5

y = "Stephan"

  

print("The Value of 'x' : " + str(x))

print("The Value of 'y' : " + y)

print("The Data-Type of 'x' : ",type(x))
```

> Variables do not need to be declared with any particular _type_, and can even change type after they have been set.

```python
x = 4         # x is of type int  
x = "Stephan" # x is now of type str  
print(x)
```


## Casting

If you want to specify the data type of a variable, this can be done with casting

```python
x = str(3)    # x will be '3'  
y = int(3)    # y will be 3  
z = float(3)  # z will be 3.0
```

---
## Many Values to Multiple Variables

Python allows you to assign values to multiple variables in one line:

```python
a, b, c = "Apple", "Banana", "Carrot"

fruit_with = "Fruit with Name : "

print(fruit_with + a)

print(fruit_with + b)

print(fruit_with + c)

```

> **Note:** Make sure the number of variables matches the number of values, or else you will get an error.

## Unpack a Collection

If you have a collection of values in a list, tuple etc. Python allows you to extract the values into variables. This is called _unpacking_.

```python
fruits = ["apple","banana","cherry"]

x, y, z = fruits

fruits_from_list = "Fruits from List with Letter "

print(fruits_from_list + "A : " + x)

print(fruits_from_list + "B : " + y)

print(fruits_from_list + "C : " + z)
```


---
## Output Variables

The Python `print()` function is often used to output variables.

```python
x = "Python is awesome"  
print(x)
```

In the `print()` function, you output multiple variables, separated by a comma:
```python
x = "Python"  
y = "is"  
z = "awesome"  
print(x, y, z)
```

You can also use the `+` operator to output multiple variables:

```python
x = "Python "  
y = "is "  
z = "awesome"  
print(x + y + z)
```

For numbers, the `+` character works as a mathematical operator:
```python
x = 5  
y = 10  
print(x + y)
```

The best way to output multiple variables in the `print()` function is to separate them with commas, which even support different data types:
#### Best Way to Output

```python
x = 5  
y = "John"  
print(x, y)
```

---
## Global Variables

Variables that are created outside of a function are known as global variables.
Global variables can be used by everyone, both inside of functions and outside.


| TODO | Create a variable outside of a function, and use it inside the function |
| ---- | ----------------------------------------------------------------------- |

```python
x = "awesome"  
  
def myfunc():  
  print("Python is " + x)  
  
myfunc()
```


> If you create a variable with the same name inside a function, this variable will be local, and can only be used inside the function.

| TODO | Create a variable inside a function, with the same name as the global variable |
| ---- | ------------------------------------------------------------------------------ |
```python
x = "Awasome"

def myfunc():
x = "fantastic"
print("Python is " + x)

myfunc()
```


## The global Keyword

Normally, when you create a variable inside a function, that variable is local, and can only be used inside that function.

To create a global variable inside a function, you can use the `global` keyword.
> If you use the `global` keyword, the variable belongs to the global scope:

```python
def my2ndfunc():

global z

z = "Amazing"
my2ndfunc()

print("Python is : " + z)
```




## Sources
1. https://www.w3schools.com/python/python_variables.asp
2. https://www.w3schools.com/python/python_variables_names.asp
3. 