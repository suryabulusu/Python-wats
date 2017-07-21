# Python-wats
Here's a small collection of wats I have come across while learning [Python](http://www.oreilly.com/programming/free/a-whirlwind-tour-of-python.csp "A Whirlwind Tour of Python by Jake VanderPlas"). This is also an attempt to learn [Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#links "Markdown Cheatsheet").

## True or False?
```python
>>> True is False == False
```
Lets analyse from LHS, ie, (True is False) == False  
`True is False` is **False**  
`False == False` is **True**  
So output should be `True`

Now, from the RHS, ie, True is (False == False)  
`False == False` is **True**  
`True is True` is **True**  
So output should be `True`

But the output is..

```python
False
```
**wat?**

*__Explanation__*:   
`a < b < c` is interpreted as `a < b and b < c`  
All expressions involving two or more operations are interpreted in a similar way.  
So the given expression is equivalent to 
```python
>>> True is False and False == False
```
`True is False` is **False** and `False == False` is **True**  
`False and True` is **False** 
Hence the result is
```python
False
```
## 200 + 200 is 400?
```python
>>> 10 + 10 is 20
True
>>> 20 + 30 is 50
True
>>> 100 + 100 is 200
True
>>> 200 + 200 is 400
False
```
**waaat?**

*__Explanation__*: Identity operator is not checking for equality, it is checking if the operands are pointing to the same memory bucket. For example,
```python
>>> a = 2
>>> b = 2
>>> a is b
True
```
Here, ```a is b``` is **True** because **id(a)** is equal to **id(b)**. That is, both **a** and **b** are pointing to the same memory bucket. This works for small integers. However,

```python
>>> a = 260
>>> b = 260
>>> a is b
False
```
because, **id(a)** is not equal to **id(b)**. For integer values greater than 255, **a** and **b** point to different memory buckets.  

Now we can see why `10 + 10 is 20` is **True** and `200 + 200 is 400` is **False**. **(200 + 200)** does not point to the same location as **400**.





