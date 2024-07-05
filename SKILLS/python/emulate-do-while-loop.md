At times, we encounter situations that require us to use the `do-while` loop in Python. A **do-while loop** is important because it is a **post-test loop**, meaning that it checks the condition _only_ after executing the code in the loop block.

> Even though Python doesn’t explicitly have the `do-while loop`, we can emulate it.

### General syntax


### Emulating a `do-while` loop in Python

There are two scenarios in which a loop terminates:

- The loop condition is no longer true/false (depending on the type of loop).
- A `break` statement is executed from within the code in the loop body.

> If the condition is to be checked after executing the loop block, we can bring the condition _inside_ the loop block, set the loop condition to be always `true`, and `break` the loop once the condition is met _inside_ ​the code block.

Have a look at the code,for printing the first 3 integers,below:

```python
i = 1

while True:
	print(i)
	i = i + 1
	if(i > 3):
		break
```

The `do-while` loop in C++ and the emulation of the same loop in Python result in the same output. In the Python emulation, `i` is being printed before the condition is checked, just ​like in the `do-while` loop in C++.

Sources
- https://www.educative.io/answers/how-to-emulate-a-do-while-loop-in-python
- 