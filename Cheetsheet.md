### :octocat: #1 Removing Leading Zeroes In Dot-separated String

:seedling: **Input**: 
```
"010.020.300.004"
```

:four_leaf_clover: **Output**:
```
"10.20.300.4"
```

:frog: **Example**(javascript):
```javascript
"010.020.300.004".replace(/(^|\.)0*([1-9][^\.$]*)/g, "$1$2")
```

:bug:	 **Caveats**:

The `^` cann't be represented as `[^0]`.

```
"010.020.300.004".replace(/([^0])0*([1-9][^\.$]*)/g, "$1$2") // -> "010.20.300.4"
```
