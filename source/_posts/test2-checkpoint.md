---
title: numpy-1
date: 2019-10-10 10:00:00
comment: 'waline'
index_img: /img/index.jpg
---

<br>
```python
import numpy as np
np.version.version  # check the version of NumPy
```




    '1.22.3'




```python
a = np.array([1, 2, 3, 4])  # create an array
b = np.array((1, 2, 3, 4))
c = np.array([[1, 2], [2, 3], [3, 4]])  # Create a multidimensional array
a, b, c
```




    (array([1, 2, 3, 4]),
     array([1, 2, 3, 4]),
     array([[1, 2],
            [2, 3],
            [3, 4]]))




```python
a.shape, b.shape, c.shape  # get the dimension of a
```




    ((4,), (4,), (3, 2))




```python
c.shape = 6, 1  # update the dimension of c
print(c)
c.shape = 2, -1  # if the dimension is -1,then calculate the dimension automatically
print(c)
d = a
d[0] = 100  # if you update the element of d,then a will also be updated
print(a)
```

    [[1]
     [2]
     [2]
     [3]
     [3]
     [4]]
    [[1 2 2]
     [3 3 4]]
    [100   2   3   4]



```python
print(a.dtype)  # get the element type in a
a_i32 = np.array([1, 2, 3, 4], dtype=np.int32)  # NumPy also has its own float type(float16，float32，float64， float128)
a_f = np.array((1, 2, 3, 4), dtype=float)
a_c = np.array([[1, 2], [2, 3], [3, 4]], dtype=complex)  # plural type
a.dtype, a_i32.dtype, a_f.dtype, a_c.dtype
```

    int32





    (dtype('int32'), dtype('int32'), dtype('float64'), dtype('complex128'))




```python
print(set(np.sctypeDict.values()))  # get all type of NumPy
print(a.dtype.type)  # get numeric type by dtype.type
```

    {<class 'numpy.complex64'>, <class 'numpy.uint16'>, <class 'numpy.bytes_'>, <class 'numpy.float16'>, <class 'numpy.clongdouble'>, <class 'numpy.int32'>, <class 'numpy.timedelta64'>, <class 'numpy.complex128'>, <class 'numpy.uintc'>, <class 'numpy.int64'>, <class 'numpy.void'>, <class 'numpy.longdouble'>, <class 'numpy.uint32'>, <class 'numpy.int16'>, <class 'numpy.uint64'>, <class 'numpy.intc'>, <class 'numpy.int8'>, <class 'numpy.uint8'>, <class 'numpy.float64'>, <class 'numpy.bool_'>, <class 'numpy.float32'>, <class 'numpy.datetime64'>, <class 'numpy.str_'>, <class 'numpy.object_'>}
    <class 'numpy.int32'>



```python
print(np.arange(0, 1, 0.1))  # (initial value, final value, step size), not include the final value
print(np.linspace(0, 1, 10))  # (initial value, final value, number of elements), include the final value
print(np.linspace(0, 1, 10, endpoint=False))  # not include the final value
print(np.logspace(0, 2, 5))  # (10^0, 10^2), proportional sequence
print(np.logspace(0, 1, 12, base=2, endpoint=False))
```

    [0.  0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9]
    [0.         0.11111111 0.22222222 0.33333333 0.44444444 0.55555556
     0.66666667 0.77777778 0.88888889 1.        ]
    [0.  0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9]
    [  1.           3.16227766  10.          31.6227766  100.        ]
    [1.         1.05946309 1.12246205 1.18920712 1.25992105 1.33483985
     1.41421356 1.49830708 1.58740105 1.68179283 1.78179744 1.88774863]



```python
print(np.empty((2, 3), np.int64))
print(np.zeros(5, np.int32))
print(np.ones(5, np.int32))
print(np.full(4, np.pi))
a = np.array([[2, 3], [3, 4]])
print(np.zeros_like(a))
s = "abcdefg"
print(np.fromstring(s, dtype=np.uint8))
```

    [[0 0 0]
     [0 0 0]]
    [0 0 0 0 0]
    [1 1 1 1 1]
    [3.14159265 3.14159265 3.14159265 3.14159265]
    [[0 0]
     [0 0]]
    [ 97  98  99 100 101 102 103]


    C:\Windows\Temp\ipykernel_18256\2860232501.py:8: DeprecationWarning: The binary mode of fromstring is deprecated, as it behaves surprisingly on unicode inputs. Use frombuffer instead
      print(np.fromstring(s, dtype=np.uint8))



```python
def func(i):
    return i % 4 + 1
print(np.fromfunction(func, (10, )))
def func2(i, j):
    return (i+1) * (j+1)
print(np.fromfunction(func2, (3, 10)))
```

    [1. 2. 3. 4. 1. 2. 3. 4. 1. 2.]
    [[ 1.  2.  3.  4.  5.  6.  7.  8.  9. 10.]
     [ 2.  4.  6.  8. 10. 12. 14. 16. 18. 20.]
     [ 3.  6.  9. 12. 15. 18. 21. 24. 27. 30.]]



```python
a = np.arange(10)
print(a, a[5], a[3:5], a[:5], a[:-1])
print(a[1:-1:2], a[::-1], a[5:1:-2])
b = a[2:4]
b[1] = 100
print(b)
print(a)
```

    [0 1 2 3 4 5 6 7 8 9] 5 [3 4] [0 1 2 3 4] [0 1 2 3 4 5 6 7 8]
    [1 3 5 7] [9 8 7 6 5 4 3 2 1 0] [5 3]
    [  2 100]
    [  0   1   2 100   4   5   6   7   8   9]



```python
x = np.arange(10, 1, -1)
a = x[[3, 3, -3, 8]]
print(a)
a[2] = 100
print(a, x)
x[[3, 5, 1]] = -1, -2, -3
print(x)
```

    [7 7 4 2]
    [  7   7 100   2] [10  9  8  7  6  5  4  3  2]
    [10 -3  8 -1  6 -2  4  3  2]



```python
x = np.arange(10, 1, -1)
a = x[np.array([3, 3, 1, 8])]
b = x[np.array([[3, 3, 1, 8], [3, 3, -3, 8]])]
c = x[np.array([3, 3, 1, 8, 3, 3, -3, 8])].reshape(2, 4)
print(a, b, c)
a[1] = 100
print(x, a, b, c)
```

    [7 7 9 2] [[7 7 9 2]
     [7 7 4 2]] [[7 7 9 2]
     [7 7 4 2]]
    [10  9  8  7  6  5  4  3  2] [  7 100   9   2] [[7 7 9 2]
     [7 7 4 2]] [[7 7 9 2]
     [7 7 4 2]]



```python
x = np.arange(5, 0, -1)
a = x[np.array([True, False, True, False, True])]
b = x[([True, False, True, False, True])]
print(a, b)
```

    [5 3 1] [5 3 1]



```python
x = np.random.randint(0, 10, 6)
y = x[x > 5]
print(x, y)
```

    [4 7 4 5 1 0] [7]



```python
a = np.arange(0, 60, 10).reshape(-1, 1) + 10
b = np.arange(0, 60, 10).reshape(-1, 1) + np.arange(0, 6)
print(a, b)
```

    [[10]
     [20]
     [30]
     [40]
     [50]
     [60]] [[ 0  1  2  3  4  5]
     [10 11 12 13 14 15]
     [20 21 22 23 24 25]
     [30 31 32 33 34 35]
     [40 41 42 43 44 45]
     [50 51 52 53 54 55]]



```python
print(b[0, 3:5], b[4:, 4:], b[:, 2], b[2::2, ::2])
c = b[0, 3:5]
c[:] = 100, 100
print(b)
```

    [3 4] [[44 45]
     [54 55]] [ 2 12 22 32 42 52] [[20 22 24]
     [40 42 44]]
    [[  0   1   2 100 100   5]
     [ 10  11  12  13  14  15]
     [ 20  21  22  23  24  25]
     [ 30  31  32  33  34  35]
     [ 40  41  42  43  44  45]
     [ 50  51  52  53  54  55]]



```python
idx = slice(2, None, 2), slice(None, None, 2)
print(b[idx])
idx1 = np.s_[2::2, ::2]
print(b[idx1])
print(b[(0, 1, 2, 3), (1, 2, 3, 4)])
```

    [[20 22 24]
     [40 42 44]]
    [[20 22 24]
     [40 42 44]]
    [ 1 12 23 34]



```python

```
