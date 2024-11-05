java cAssignment 6
Due Wednesday by 11:59pm
Points 80
Submitting a file upload
Available Oct 28 at 12pm - Dec 31 at 11:59pm
Start Assignment
Assignment 6 (80 Points)
Due November 6 at 11:59 PM
In this assignment, you will create distributed solutions (i.e., with multiple processes) for the two
programs you developed in Assignment 2 (Curve Area Calculation and Heat Transfer) using Message
Passing Interface (MPI). MPI is different from the shared memory model we have used so far, and
requires using APIs to communicate between processes.
Before starting this assignment, you should have completed the Slurm Tutorial
(https://canvas.sfu.ca/courses/84236/pages/slurm-tutorial) , which walks you through how to use our
servers for your code development. Additionally, you should also have completed the MPI tutorial
(https://canvas.sfu.ca/courses/84236/pages/slurm-mpi-tutorial) , which gives an overview of MPI and how
to correctly run MPI programs using slurm.
General Instructions:
1. You are given the serial implementations here (https://canvas.sfu.ca/courses/84236/files/24448350?
wrap=1) (https://canvas.sfu.ca/courses/84236/files/24448350/download?download_frd=1) .
2. MPI permits various communication strategies to pass data between processes. This assignment
uses the point-to-point communication strategy.
3. For simplicity, we only use one thread per process in this assignment. Make sure you
use MPI_Finalize (https://www.open-mpi.org/doc/current/man3/MPI_Finalize.3.php) before exiting
the main() function.
4. MPI uses the distributed model where each process is completely independent and has its own
separate memory space. Re代 写program、python
代做程序编程语言member to set the --mem option appropriately in your script.
5. While testing your solutions, make sure that --cpus-per-task is set to 1 in your slurm job
script, and the --ntasks and --nodes is set based on number of MPI processes and nodes you
want.
#!/bin/bash
#
#SBATCH --cpus-per-task=1
#SBATCH --nodes=1
 Assignment 6
 1/8
#SBATCH --ntasks=4
#SBATCH --partition=slow
#SBATCH --mem=10G
srun ./curve_area_parallel
6. You will be asked to print the time spent by different processes on specific code regions. The time
spent by any code region can be computed as follows:
timer t1;
t1.start();
/* ---- Code region whose time is to be measured --- */
double time_taken = t1.stop();
If you need to time a sub-section inside a loop, you can do that as follows:
double time_taken = 0.0;
timer t1;
while(True){
 /* ---- Code region whose time should not be measured --- */
 t1.start();
 /* ---- Code region whose time is to be measured --- */
 time_taken += t1.stop();
 /* ---- Code region whose time should not be measured --- */
}
std::cout  0) { // not first process
 Receive column "start-1" from the left process world_rank-1, populate local Curr Arr
ay
 Send my column "start" to the left process world_rank-1
 }
 } // even rank
 else { // odd rank
 if (world_rank > 0) { // not first process
 Receive column "start-1" from the left process world_rank-1, populate local Curr Arr
ay
 Send my column "start" to the left process world_rank-1
 }
 if (world_rank /assignment6.tar.gz
Submit via Canvas by the deadline.
 Assignment 6
 8/8

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
