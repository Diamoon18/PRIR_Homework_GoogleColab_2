# PRIR_Homework_GoogleColab_2
#### Install CUDA in Google Colab
![image](https://user-images.githubusercontent.com/72127610/147588670-f24197d2-ce37-4e42-b793-2247491aefdb.png)
### Numeric integration - the method of rectangles, trapezoids and Simpson
Function for tests -> y = x*x in [-4;2]\
Result: 24\
I will generate the algorithm 20 times, to find the optimal execution time.
#### Version cpu 
// table for n=10, 100, 1000, 10000, 100000
![image](https://user-images.githubusercontent.com/72127610/147688264-3281283f-c4a0-4149-a0cb-24408fcff46e.png)\
```Conclusions```:
1. For small n, run times quite short, but the accuracy of the calculation is also low for the rectangles method.\
Also long execution time for large n.
2. The trapezoidal method somewhat improves the situation with accuracy for large n and it reduces times a little.
3. Method Simpsona - the best method for small n.\
We already have a good answer and for a small amount of time.
#### Version gpu
// table for n=10, 100, 1000, 10000, 100000
![image](https://user-images.githubusercontent.com/72127610/147699851-3d585bc9-6ef1-4bb2-8521-bac34b9bca4e.png)\
```Conclusions```:
1. For small n, run time greater than on CPU, and the accuracy of the calculation is low for the rectangles method.\
But for larger n the execution times on GPU are smaller than on CPU.
2. The trapezoidal method somewhat improves the situation with accuracy for large n and it reduces times a little.
3. Method Simpsona - the best method for small n and for CPU.\
We already have a good answer, but in GPU xecution time is greater than in CPU.
#### Charts - comparison
![image](https://user-images.githubusercontent.com/72127610/147756755-66674bd7-72ab-457e-b793-5d511335ff40.png)
![image](https://user-images.githubusercontent.com/72127610/147757623-e8e4bb43-716c-4d82-bf10-0dac0895234d.png)
![image](https://user-images.githubusercontent.com/72127610/147758779-45194174-1998-4cbb-9388-239e88a55a55.png)

#### Final conclusions
As can be seen from the charts, the GPU version turned out to be less efficient than the CPU version for small n.\
The speedup for using GPU increases as n increases.\
This is because the GPU code incurs a large amount of overhead while calling ```malloc``` to allocate the shared memory arrays, and to copy the data between
the CPU and GPU.\
The C++ code does not use any arrays, so it avoids this overhead.\
The cost of the overhead is only amortized when n is very large.
![image](https://user-images.githubusercontent.com/72127610/147759464-d1d1d665-90e9-4b5f-95c9-e6a00f34a6d7.png)

