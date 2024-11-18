# Hello Three Times file

```
dkernel<<<1,1>>>();
dkernel<<<1,1>>>();
dkernel<<<1,1>>>();

cudaDeviceSynchronize();

printf("On CPU.\n");
```

The CPU will call each kernel one at a time. These kernels will be in a kind of queue or stream. 
So they will be running serially, one after the other. After, CDS (Cuda Device Synchronize) will
bring everything together and only after this the message "On CPU" will be showed. 

So, kernels, by default, are executed one after another. But we can change this.