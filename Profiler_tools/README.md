# What is profiling
Sometimes, when we need to achieve a new function or run a demo, we can develope quickly to build a simple framework to make sure the route is correct.However, many tiny bugs will result in big problem during a quick programing, such as circular reference which will result in OOM.  
Also, such problem will not just appear in our coding program, some 
# How to realize profiling qulickly!
## Use memory_profiler
You can use pip to install memory_profiler  
``pip install memory_profiler``  
Then we started!  
Use ``mprof run demo.py`` will run your python file and create a file, that file store the memory change during the running time  
Use ``mprof plot`` will use matplotlib tools to draw a image by the latest memroy changing records

## Use nvidia-smi
