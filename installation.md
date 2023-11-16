At present (2023-11-16), I will use hqlx24 for GOTM testing.  

## The following package should be prepared:

refer to this [link](https://gotm.net/portfolio/software/)

- ifort and NetCDF  
  already have that on hqlx24

- Cmake
  Can set it up following this link <https://zhuanlan.zhihu.com/p/110793004>  
  I just copy the compiled package and add the following command to "*~/.bashrc*".
  ![image](https://github.com/ELVIS-CHING/GOTM-notes/assets/62006950/e3f88b98-3eab-433d-bd61-d63917e07e8e)  

- GOTM code  
  > git clone --recursive https://github.com/gotm-model/code.git  
  > git submodule update --init --recursive

## Building GOTM

refer to this [link](https://gotm.net/software/linux/)  
I use the method "**The provided configure/build scripts**"  
There are errors when using the method "**Command line version of CMake**", which may be because I did not set the Fortran compiler.

Following the steps:  
- configure  
  use the "*gotm_configure.sh*" file in "*$GOTM_BASE/scripts/linux/*"  
  "*$GOTM_BASE*" is the directory of the source code  
  create the installation directory in advance  
  modify the "*gotm_configure.sh*" file as shown below  
  ![image](https://github.com/ELVIS-CHING/GOTM-notes/assets/62006950/85b34362-4121-486c-9bf4-f02450c248e6)  
  execute the command  
  > ./gotm_configure.sh

- build  
  use the "*gotm_build.sh*" file in "*$GOTM_BASE/scripts/linux/*"  
  modify the compiler in "*gotm_build.sh*"  
  execute the command  
  > ./gotm_build.sh

- check  
  there should be the executable "*gotm*" file in "*installation_directory/bin/*"
  add this path to "*~/.bashrc*"
  ![image](https://github.com/ELVIS-CHING/GOTM-notes/assets/62006950/f8a410b1-8e77-4391-b120-feaf14ce5933)  
  execute the command  
  > gotm -v  

  ![image](https://github.com/ELVIS-CHING/GOTM-notes/assets/62006950/4f83a0c4-3a74-4f13-8ba7-332407651d49)
