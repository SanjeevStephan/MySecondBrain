

![[00-Index-of-Python-Fundamentals]]



## Strings

Strings in python are surrounded by either single quotation marks, or double quotation marks.

'hello' is the same as "hello"

## Assign String to a Variable

Assigning a string to a variable is done with the variable name followed by an equal sign and the string:

```python
a = "Hello"
print(a)
```

## Multiline Strings

You can assign a multiline string to a variable by using three quotes:

```python


# You can use three double quotes:

a = """Lorem ipsum dolor sit amet,  
consectetur adipiscing elit,  
sed do eiusmod tempor incididunt  
ut labore et dolore magna aliqua."""  

print(a)

# Or three single quotes:

a = '''Lorem ipsum dolor sit amet,  
consectetur adipiscing elit,  
sed do eiusmod tempor incididunt  
ut labore et dolore magna aliqua.'''  
print(a)

```

## Looping Through a String

Since strings are arrays, we can loop through the characters in a string, with a `for` loop.

