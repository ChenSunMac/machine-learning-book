# Numpy

## numpy.ndarray

Parameters:
    - shape
    - dtype
    - buffer
    - offset: 偏移量
    - strides: 数据步长
    - order:  Row-major (C-style) or column-major (Fortran-style) order
    
### From List/Tuple To ndarray

```py
#object is the list
numpy.array(object, dtype=None, copy=True, order=None, subok=False, ndmin=0)
```