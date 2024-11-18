# HELLO file

### The header file

```
#include<cuda.h>
 ```

CUDA header file for CUDA functions and directives. 


### The "global" directive

```
___ global ___ void //without spaces between "global"
```

Specifies that this function will be executed in GPU. 


### dkernel function

It's a kernel function or a named function that will be running on GPU.

### dkernel arguments

```
dkernel<<<1,1>>>();
```

It's something like "I want to execute this kernel/this GPU function with 1 to 1 threads (only 1 thread)";


### Wait until GPU come back

```
cudaDeviceSynchronize();
```

We need this function because, without this, the Hello World just won't appear with printf. 
When CPU is running, it calls the kernel and just go to the next instruction. In other words, 
the CPU does not wait until GPU print the message. We need to guarantee that both CPU and GPU will stay synchronized. 
Then, CPU will be able to wait until GPU come back from running its code. 