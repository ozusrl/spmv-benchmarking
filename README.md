# spmv-benchmarking

## Build MatrixMarket IO

```
# Start from spmv-benchmarking root folder

git clone -b dev https://github.com/ozusrl/MMMatrixIO.git

mkdir -p lib/mmmatrixio
cd lib/mmmatrixio

cmake ../../MMMatrixIO/src
make
```



## Build dockopt.cpp

```
# Start from spmv-benchmarking root folder

git clone https://github.com/docopt/docopt.cpp.git

mkdir -p lib/docopt.cpp
cd lib/docopt.cpp

cmake ../../docopt.cpp
make

```


## Build spmv-benchmarking

### Simple build with reference methods only

```
# Start from spmv-benchmarking root folder

mkdir build
cd build

cmake ../src
```


### Enabling code specializer methods

#### Build asmjit

```
# Start from spmv-benchmarking root folder
git clone https://github.com/asmjit/asmjit

mkdir -p asmjit/build
cd asmjit/build

cmake ../
make

```

#### Build spmv-benchmarking with code specializers enabled
```
# Start from spmv-benchmarking root folder
cd build

cmake -DCODEGEN=true ../src
make
```

### Enable ViennaCL

#### Build ViennaCL

Download ViennaCL from http://viennacl.sourceforge.net/viennacl-download.html
to `${VIENNACL_PATH}`

```
cd ${VIENNACL_PATH}/build
cmake ../
make
```

#### Build spmv-benchmarking with ViennaCL

```
# Start from spmv-benchmarking root folder
cd build

cmake -DVIENNACL=${VIENNACL_PATH} ../src
make
```
