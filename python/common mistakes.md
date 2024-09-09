
# context managers
- dont use close or finally blocks when opening things but rather use context managers
- if the write call throws an exception the file will never be closed
```python
with open(filename) as f:
	f.write("hello"\n)
```

# Use of default mutable arguments
```python
def append(n, l=[]):
	l.append(n)
	return l

l1 = append(0) # [0]
l2 = append(1) # [0, 1]

####

def append(n, l=None):
	if l is None:
		l = []
	l.append(n)
	return l

l1 = append(0) # [0]
l2 = append(1) # [1]
```

# comprehensions
- use comprehensions when applicable but not always
- main goal is readability
```python
dict_comp = {i: i*i for i in range(10)}
list_comp = [i for i*i in range(10)]
set_comp = {i%3 for i in range(10)}
gen_comp (2*i+5 for i in range(10))
```

# checking for type with ==
- doesn't work when comparing a subclass to a class
```python
# liskov substitution principle
Point = namedtuple('Point', ['x','y'])
p = Point(1, 2)

if isinstance(p, tuple):
		print("It's a Tuple")
```

# range / len pattern
```python
a = [1, 2, 3]
for i in range(len(a)):
	v = a[1]

# if you loop over a list to get the elements instead use 

for v in a:
	...

# if you need index as well

for i, v in enumerate(a):
	...

# get corresponding elements
b = [4, 5, 6]

for av, bv in zip(a, b):
	...
	
# still want index as well

for i, (av, bv) in enumerate(zip(a, b)):
	...
```