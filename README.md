DONKEY clustering algorithm
---------------------------

**Documentation WIP**

## Setup
1. Clone repo
2. Compile density.f90 to density.[cpython-data].so using F2PY
   (link against your LAPACK and BLAS installations, example provided in build.sh)
3. Import the algorithm and have fun!

The code is compatible with the scikit-learn clustering interface.

## Example
```
from clustering import Donkey  
data = ...  
clus = Donkey()  
clus.fit(data)  
labels = clus.labels_
```

## class `Donkey`

### Description:
`Donkey` class is used to perform calculations and store data throughout the algorithm

### `__init__(alpha=1, beta=1, gamma=1, abramson=True, log=False, name="clusters")`
Creates a `Donkey` instance
- `alpha` (float): widening factor for gaussians g(x) = exp(-1/2 alpha x^T C^-1 x)  
- `beta` (float): gives merging threshold as exp(-beta)
- `gamma` (float): outlier threshold as a fraction of cluster centre height  
- `abramson` (bool): adapt covariances locally  
- `log` (bool): produce a log file  
- `name` (str): root of all created files, <name>.<extensions>

### Methods
