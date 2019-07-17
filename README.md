# PAMPAR
In this project we aim to build a parallel benchmark to evaluate parallel programing interfaces (or parallel APIs).

In our research we found out that there is no benchmark focused on comparing parallel programing interfaces.

This is a initial work and we still updating these applications. Currently the benchmark consists of 13 parallel pseudo-applications, each parallelized using PThreads, OpenMP, MPI-1, and MPI-2 (dynamic processes creation).

The pseudo-aplications are:
  - Pi Caluculation       (PI);
  - Dot Produtct          (DP);
  - Numeric Integration   (NI);
  - Odd-Even Sort         (OE);
  - Harmonic Sums         (HA);
  - Disc. Fourier Transf. (DFT);
  - Turing Ring           (TR);
  - Dijkstra Shortest Path(DJ);
  - Jacobi Method         (JA);
  - Matrix Multiplication (MM);
  - Gram-Schmidt Process  (GS).
  - Histograms Similarity (SH);
  - Game of Life          (GL);
  
  (GL and SH still need some polishment)

The goal is to paralelize the set using more interfaces and add new pseudo-aplications according to the demand.

More details and studies on these applications can be found at: https://www.researchgate.net/project/A-Parallel-Benchmark-for-Performance-Evaluation-and-Energy-Consumption-in-Multicore-and-Manycore-Architectures

How to run:
  
  - To compile all the pseudo-applications, go to the PAMPAR root directory and run:
  
	~$ make
    
  - You can run the 'run.sh' script and follow the steps to setup and run the benchmark.
  
  	~$ bash run.sh
    
  It will run the pseudo-applications according to the setup and give the execution time for each case.
  
How to run manually:

  - Compile the applications using the Makefile
  
  - To run a PThread or OpenMP application, run:
    
    	~$ ./<executable> <number_of_threads> <input_problem>
    
    Example: 
    	~$ ./pthread 4 2048
   
    
  - To run a MPI-1 application, run:
  
  	~$ mpirun -np <number_of_processes> <executable> <input_problem>
    
    Example: 
    	~$ mpirun -np 4 ./mpi1 2048
    
    
  - To run a MPI-2 application, run:
 
 	~$ mpirun -np 1 <executable> <number_of_child_processes> <input_problem> <child_executable>
    
    Example: 
    	~$ mpirun -np 1 ./pai 3 2048 ./filho
    
  Examples of medium sized values of <input_problem> for each application:
  
  	DFT: 32368
	 DJ: 2048 2048_matrix.txt
	 DP: 15000000000
	 GS: 1024
	 HA: 100000 100000
	 JA: 2048
	 MM: 4096
	 NI: 1000000000
	 OE: 225000
	 PI: 4000000000
	 TR: 2048
