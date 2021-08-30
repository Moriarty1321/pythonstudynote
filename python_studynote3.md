```python
#汉诺塔问题
import sys
 
sys.setrecursionlimit(1000)
def move(n,a,b,c):
    if n==1:
        print(a,'go to',c)
        return #这里要加return负责即使n为1也会继续执行后面语句，会报错
    move(n-1,a,c,b)
    move(1,a,b,c)
    move(n-1,b,a,c)
move(2,'a','b','c')
```

    a go to b
    a go to c
    b go to c
    


```python

    
    
```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```
