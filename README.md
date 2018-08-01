# test-regression
testing cms hcal/ecal regression 

## to build
- `git clone <repo>` and `cd <repo>`
- `mkdir build` and `cd build`
- `cmake ../ -DEIGEN_HOME=<path to eigen root dir>` 
- if u r @vinavx2 use: `cmake ../ -DEIGEN_HOME=/data/user/vkhriste/eigen/eigen -DOpenCL_INCLUDE_DIR=/usr/local/cuda/include`
- `cmake ../ -DTHRUST_HOME=<path to thrust root dir>`

## to run
- generate pulses `./gen/gen_data -13`
- run multifit `./multifit_cpu/multifit ../data/mysample_100_-13.000_0.000_10_25.00_10.00_0.00_1.000_1.00_0.00_slew_1.00.root `

## flags to choose decomposition
- SparseQR -> `-DDECOMPOSITION=USE_SPARSE_QR` (default value)
- LLT -> `-DDECOMPOSITION=USE_LLT` 
- HouseHolderQR -> `-DDECOMPOSITION=USE_HOUSEHOLDER`
