DONKEY clustering algorithm
---------------------------

**Documentation WIP**

## Setup
1. Clone repo
2. Compile density.f90 to density.[cpython-data].so using F2PY
   (link against your LAPACK and BLAS installations, example provided in build.sh)
3. Import the algorithm and have fun!

The code is compatible with the scikit-learn clustering interface.

## class `Donkey`

### Description:
`Donkey` class is used to perform calculations and store data throughout the algorithm  
The interface is fully compatible with scikit-learn

### Attributes
**`labels_`**
(np.array): label assigned to each sample after fitting

### Methods

**`__init__(alpha=1, beta=1, gamma=1, abramson=True, log=False, name="clusters")`**
Creates a `Donkey` instance  
- `alpha` (float): widening factor for gaussians g(x) = exp(-1/2 alpha x^T C^-1 x)  
- `beta` (float): gives merging threshold as exp(-beta)  
- `gamma` (float): outlier threshold as a fraction of cluster centre height  
- `abramson` (bool): adapt covariances locally  
- `log` (bool): produce a log file  
- `name` (str): root of all created files, <name>.<extensions>
Usage:
```
clus = Donkey(log=True, name="test")
```

**`fit(data, pbc=[], ranges={})`**
Performs DONKEY clustering on the supplied data
- `data` (np.array): data to be clustered with data.shape == (n_samples, n_features)
- `pbc` (list[int]): list all the features that are periodic, 0-indexed
- `ranges` (dict[int, list[float]]): specify the upper and lower bound of a given feature, which will get mapped onto [0, 1]
Usage:
```
# assume feature 0 is angle-like -> periodic with range [-pi, pi]
clus.fit(data, pbc=[0], ranges={0: [-np.pi, np.pi]}
```

**`plot_clusters(*args, **kwargs)`**
Plots clusters obtained from fitting using provided arguments  
Args TBD
Usage
```
clus.plot_clusters()
```


