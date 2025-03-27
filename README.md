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

`**class Donkey**(alpha=1, beta=1, gamma=0, abramson=True, log=False, name="clusters")`
   Creates an instance of Donkey to be used later
   | --- | --- |
   | alpha | widening factor for gaussians g(x) = exp(-1/2 alpha x^T C^-1 x) |
   | beta | gives merging threshold as exp(-beta) |  
   | gamma | outlier threshold as a fraction of cluster centre height|  
   | abramson | adapt covariances locally |
   | log | produce a log file |
   | name | root of all created files, <name>.<extensions> |  
