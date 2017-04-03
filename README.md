# QUEST

A library for simulating operations on sets of qubits. 

Operations implemented:
* Rotations of a single qubit
* TODO: Measure if a single qubit is in the zero state
* TODO: Two qubit phase gate

# Getting started

With git: clone the root directory to your device

git clone https://github.com/aniabrown/QUEST.git [QUESTHOME]

Without git: download the directory manually

'Clone or download' > 'Download zip'

In the root directory, run a simple 8 qubit example on one node with
make
./demo 8

This will report some information about the size of the system, perform rotations and verify that
the state vector of probability amplitudes is still normalized. 

# Building other examples

There are other examples of codes using the QUEST library in the examples folder. To use one of these,
copy from the examples folder into the root folder, eg:
cp examples/timingDemo.c timingDemo.c

Edit the COMMON CONFIG section at the beginning of makefile. Change MY_FILE_NAME to the name of the file without
any extension, eg MY_FILE_NAME=timingDemo 
Change the name of the executable as desired eg EXE=myProg.

Run with:
make clean
make
./myProg [NUMBER OF QUBITS]

To run on arcus-b on one node, use the job submission script examples/ompJob.sh

# Multi node code

To run over several nodes with MPI, edit the COMMON CONFIG section at the beginning of makefile. 
Change USE_MPI=0 to USE_MPI=1.

Run with:
make clean
make

mpirun -np [NUMBER OF PROCESSES] ./demo [NUMBER OF QUBITS]

To run on arcus-b, use the job submission script examples/mpiJob.sh

# API Documentation

Copy Doxygen_doc/html to a device with an internet browser. Open Doxygen_doc/html/index.html

