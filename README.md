Roadmap
=======

Big refactoring needs !

Structural change
-----------------
- Use MPI for distribution
- Full CPU parallelization
- Full GPU parallelization
- OOP in genome/user classes
- Pointer usage in genome/user class 

Template addition
-----------------
- PARADE
- ASREA(2)
- Parisian algorithms support

Module
------
- Add the monitoring code

Visualization
-------------
- Plug GridVis on or/in EASEA

Code convention
---------------
Indentation
- 2 whitespace
- "Egyptian" bracket

Naming convention:
- Camelcase except for pre-processor directives 
- Globals : g[NAME]
- Class member variable : m[NAME]
- Macro : ue unscore instead 

Variable declaration:
- Class : bottom
- Function : top
- ALL locale variable are defined at the top of the function

Memory allocation:
- The C++ way (new and delete) except in extern C block (huh)

Documentation:
- Doxygen style 

No plateform/library specifics directives in function place them in macro at the
start of the files.
For pointesr put the star * next to the type 
Much more to be added ...

Tools
-----
- Use clanganalyzer (static analyzer) 
- Use valgrind 
- Use gdb/cuda\_gdb for debugging 

Documentation
-------------- 
- How to create template
- Parsed paramaters and section in .ez
- Variable/scope accessibility

Additional info
---------------

- Use the regression tests ("examples/regression.sh")
- Add (for example) in your bashrc: 

```
alias Weierstrass="cd ../.. && make clean && make -j2 && . install.sh && cd examples/weierstrass && make easeaclea && easea weierstrass.ez && make && ./weierstrass"
```
to recompile and install easea from examples/weierstrass


The EASEA-CLOUD platform
========================

Overview
--------------
EASEA and EASEA-CLOUD are Free Open Source Software (under GNU Affero v3 General Public License) developed by the SONIC (Stochastic Optimisation and Nature Inspired Computing) group of the BFO team at Université de Strasbourg. Through the Strasbourg Complex Systems Digital Campus, the platforms are shared with the UNESCO CS-DC UniTwin and E-laboratory on Complex Computational Ecosystems (ECCE).

EASEA (EAsy Specification of Evolutionary Algorithms) is an Artificial Evolution platform that allows scientists with only basic skills in computer science to implement evolutionary algorithms and to exploit the massive parallelism of many-core architectures in order to optimize virtually any real-world problems (continous, discrete, combinatorial, mixed and more (with Genetic Programming)), typically allowing for speedups up to x500 on a $3,000 machine, depending on the complexity of the evaluation function of the inverse problem to be solved.

Then, for very large problems, EASEA can also exploit computational ecosystems as it can parallelize (using an embedded island model) over loosely coupled heterogenous machines (Windows, Linux or Macintosh, with or without GPGPU cards, provided that they have internet access) a grid of computers or a Cloud.

Features
--------------

- Runs can be distributed over cluster of homogeneous AND heterogeneous machines.
- Distribution can be done locally on the same machine or over the internet (using a embedded island model).
- Parallelization over GPGPU cards leading to massive speedup (x100 to x1000).
- C++ description language.

Requirements
--------------
This project required you to have flex and bison installed:
```
$ sudo apt-get install flex bison
```

Installation
-------------
Please refer to INSTALL.txt or the wiki : https://github.com/EASEA/easea/wiki/Building-and-installation
Note that the CMake way is prefered and that the GNU/Makefile one is there for
legacy OSes and distribution lacking CMake in there repositories. 

Sourceforge mirror
--------------

To mirror this repositories on the github one, please add to .git/config:
[remote "sourceforge"]
	url = ssh://USERNAME@git.code.sf.net/p/easea/code easea-code
	mirror = true

Add after pushing, do "git push sourceforge" manually or add a hook.
