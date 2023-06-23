# ECL-SCC

ECL-SCC is a parallel algorithm for detecting strongly connected components in directed graphs. The CUDA implementation thereof is quite fast, especially on mesh graphs. It operates on graphs stored in binary CSR format. Converters to this format can be found at https://cs.txstate.edu/~burtscher/research/ECLgraph/.

The CUDA code consists of the source files ECL-SCC_10.cu and ECLgraph.h. The paper referenced below explains the ECL-SCC algorithm. Note that ECL-SCC is protected by the 3-clause BSD license.

The code can be compiled as follows:

    nvcc -O3 -arch=sm_70 ECL-SCC_10.cu -o ecl-scc

To compute the SCC of the file mesh.egr, enter:

    ./ecl-scc mesh.egr

The repository includes three sample inputs: star.mesh.egr (6 MB), toroid-wedge.mesh.egr (4 MB), and cold-flow.mesh.egr (57 MB).


### Publication

G. Alabandi, W. Sands, G. Biros, and M. Burtscher. "A GPU Algorithm for Detecting Strongly Connected Components." Proceedings of the 2023 ACM/IEEE International Conference for High Performance Computing, Networking, Storage, and Analysis. November 2021.

*This work has been supported in part by the Department of Energy, National Nuclear Security Administration under Award Number DE-NA0003969 as well as by equipment donations from NVIDIA Corporation.*
