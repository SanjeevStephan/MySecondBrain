
In this note you will learn, how to create, verify it exists and save content on the file and then display and then delete the file using python. explain with examples.

Here's an example of how to create, verify, save content, display, and delete a file using Python

#### **Create a file**
``` python
# Create a file named "example.txt"
with open("example.txt", "w") as f:
    pass
```

In this example, we use the `open` function to create a file named "example.txt" in write mode (`"w"`). The `with` statement ensures that the file is properly closed when we're done with it, regardless of whether an exception is thrown or not.

#### **Verify that the file exists**
```python

import os

# Check if the file exists
if os.path.exists("example.txt"):   # checks the file in current diectory.
    print("File exists!")
else:
    print("File does not exist.")
    
```
In this example, we use the `os` module and its `path.exists` function to check if the file `"example.txt"` exists. If it does, we print a success message; otherwise, we print an error message.


#### **Save content to the file**
```python
with open("example.txt", "w") as f:
    f.write("Hello, world!")
```

In this example, we open the file "example.txt" in write mode (`"w"`), and use the `write` method to write the string "Hello, world!" to the file.

#### **Display the file content**

```python

with open("example.txt", "r") as f:
    print(f.read())
    
```

In this example, we open the file "example.txt" in read mode (`"r"`), and use the `read` method to read the entire file content. We then print the content to the console.

#### **Delete the file**
```python

import os

os.remove("example.txt")

```

In this example, we use the `os` module and its `remove` function to delete the file "example.txt".


Here's the complete code example:



