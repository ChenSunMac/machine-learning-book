# Numpy

## numpy.ndarray

Parameters:
    - shape
    - dtype
    - buffer
    - offset: 偏移量
    - strides: 数据步长
    - order:  Row-major (C-style) or column-major (Fortran-style) order
    
### 创建NDARRAY

- From List/Tuple To ndarray


```py
#object is the list
numpy.array(object, dtype=None, copy=True, order=None, subok=False, ndmin=0)
```


- arange & linsapce 创建

```py
numpy.arange(start, stop, step, dtype=None)
numpy.linspace(start, stop, num=50, endpoint=True, retstep=False, dtype=None)
```