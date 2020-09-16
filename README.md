1. Install NVIDIA Driver on Ubuntu 18.04
   https://medium.com/@antonioszeto/how-to-install-nvidia-driver-on-ubuntu-18-04-7b464bab43e6
   
2. Install CUDA
* Download and install: https://developer.nvidia.com/cuda-toolkit-archive
* To configure the CUDA environment for all users (and applications) on your system create the file (use sudo and a text editor of your choice)

`$ sudo gedit /etc/profile.d/cuda.sh`

with the following content,

```
export PATH=$PATH:/usr/local/cuda/bin
export CUDADIR=/usr/local/cuda
```

Also create the file,

`$ sudo gedit /etc/ld.so.conf.d/cuda.conf`

and add the line,

`/usr/local/cuda/lib64`

Then run

`sudo ldconfig`

The next time you login your shells will start with CUDA on your path and be ready to use. If you want to load that environment in a shell right now without logging out then just do, `$ source /etc/profile.d/cuda.sh`. Check if the system can find cuda by `$ nvcc -V`
