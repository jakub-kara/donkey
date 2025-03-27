DONKEY clustering algorithm
---------------------------

Documentation WIP

Steps to run:
1. Clone repo
2. Compile density.f90 to density.[cpython-data].so using F2PY
   (link against your LAPACK and BLAS installations, example provided in build.sh)
3. Import the algorithm and have fun!

The code is compatible with the scikit-learn clustering interface.

**Example:**
```
from clustering import Donkey  
data = ...  
clus = Donkey()  
clus.fit(data)  
labels = clus.labels_
```

**class Donkey**  
Creates an instance of Donkey to be used later  
_Parameters_  
`alpha` (float): widening factor for gaussians g(x) = exp(-1/2 alpha x^T C^-1 x)  
`beta` (float): gives merging threshold as exp(-beta)  
`gamma` (float): outlier threshold as a fraction of cluster centre height  
`abramson` (bool): adapt covariances locally  
`log` (bool): produce a log file  
`name` (str): root of all created files, <name>.<extensions> 


## Function: `calculateSum`

### Description:
The `calculateSum` function takes two numbers as input and returns their sum.

### Parameters:
- `num1` (number): The first number to be added.
- `num2` (number): The second number to be added.

### Return Value:
- Returns a number that is the sum of `num1` and `num2`.

### Example:

```javascript
const result = calculateSum(5, 10);
console.log(result);  // Output: 15

