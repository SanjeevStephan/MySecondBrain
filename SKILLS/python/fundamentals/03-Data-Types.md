![[00-Index-of-Python-Fundamentals]]

### Data-Types
Variables can store data of different types, and different types can do different things.
Python has the following data types built-in by default, in these categories:

| Data-Types     | Python Reserved Keywords         |
| -------------- | -------------------------------- |
| Text Type      | `str`                            |
| Numeric Types  | `int`,`float`,`complex`          |
| Sequence Types | `list`,`tuple`,`range`           |
| Mapping Type   | `dict`                           |
| Set Types      | `set`,`frozenset`                |
| Boolean Type   | `bool`                           |
| Binary Types   | `bytes`,`bytearray`,`memoryview` |
| None Type      | `NoneType`                       |
|                |                                  |

#### Getting the Data Type
You can get the data type of any object by using the `type()` function:

```python
x = 5  
print(type(x))
```
## Setting the Data Type

In Python, the data type is set when you assign a value to a variable:

| Example                                      | Data Type  | Try it                                                                          |
| -------------------------------------------- | ---------- | ------------------------------------------------------------------------------- |
| x = "Hello World"                            | str        | [Try-It](https://www.w3schools.com/python/trypython.asp?filename=demo_type_str) |
| x = 20                                       | int        | [Try It](https://www.w3schools.com/python/trypython.asp?filename=demo_type_int) |
| x = 20.5                                     | float      | [Try It]()                                                                      |
| x = 1j                                       | complex    | [Try It]()                                                                      |
| x = ["apple", "banana", "cherry"]            | list       | [Try It]()                                                                      |
| x = ("apple", "banana", "cherry")            | tuple      | [Try It]()                                                                      |
| x = range(6)                                 | range      | [Try It]()                                                                      |
| x = {"name" : "John", "age" : 36}            | dict       | [Try It]()                                                                      |
| x = {"apple", "banana", "cherry"}            | set        | [Try It]()                                                                      |
| x = frozenset({"apple", "banana", "cherry"}) | frozenset  | [Try It]()                                                                      |
| x = True                                     | bool       | [Try It]()                                                                      |
| x = b"Hello"                                 | bytes      | [Try It]()                                                                      |
| x = bytearray(5)                             | bytearray  | [Try It]()                                                                      |
| x = memoryview(bytes(5))                     | memoryview | [Try It]()                                                                      |
| x = None                                     | NoneType   | [Try It]()                                                                      |
|                                              |            |                                                                                 |
