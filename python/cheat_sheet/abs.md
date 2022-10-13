
```python
# Absolute Value
# abs()

class ImplementAbs:
	def __init__(self, string):
		self.string = string
	def __abs__(self)
		return self.string.lower()

custom_obj = ImplementAbs("HELLO")

x = abs(-9)
y = abs(-100.876)
z = abs(custom_obj)

print(x)
print(y)
print(z)
```

```
9
100.876
hello
```