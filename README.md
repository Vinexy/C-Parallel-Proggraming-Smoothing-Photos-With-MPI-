# C-Photo-Smoothing-Code
 
**Sequential and Parallel Image Smoothing**

In this program, we used parallel computing. Our purpose is high performance computing and gaining time with using data parallelism. We write 2 different code firstly sequential and secondly parallel codes also we learn that how can we smooth image. We understand that using 1,2, and 4 MPI Processes how it changed elapsed timings, speed-ups and efficiencies according to our parallel algorithms.

**Pseudocode of Sequential Algorithms**

- Rgb_image = stbi_load() → Taking the picture’s height and width.
- printf("Width: %d Height: %d) → Writing picture’s height and width.
- start=clock() Time calculator started.
- for(int k=start1;k<stop1-1;k++) for(int l=start2;l<stop2-1;l++)
int sum=0 for(int m=k-1;m<=k+1;m++) for(int n=l-1;n<=l+1;n++)
sum = sum + rgb_image, rgb_image=sum/9 → Calculate the average of each pixel's value and its eight neighbors
- time=(double)(end-start)/CLOCKS_PER_SEC → Time calculator finished
- stbi_write_jpg() - stbi_image_free() → Storing the value.
- MPI_Finalize() → Finishing it.

**Pseudocode of Parallel Algorithms**

- Rgb_image = stbi_load() → Taking the picture’s height and width.
- MPI_Init() → Initializing mpi and taking rank and size.
- printf("Width: %d Height: %d) → Writing picture’s height and width.
- start=clock() → Time calculator started
- Calculating count1= height/size, remainder1=height%size
- if(rank<remainder1)→The first 'remainder' ranks get count + 1 tasks each.
- else: The remaining 'size - remainder' ranks get 'count' task each.
- if(rank<remainder2)→The first 'remainder' ranks get count + 1 tasks each.
- else: The remaining 'size - remainder' ranks get 'count' task each.
- for(int k=start1;k<stop1-1;k++) for(int l=start2;l<stop2-1;l++)
int sum=0 for(int m=k-1;m<=k+1;m++) for(int n=l-1;n<=l+1;n++)
sum = sum + rgb_image, rgb_image=sum/9 → Calculate the average of each pixel's value and its eight neighbors
- time=(double)(end-start)/CLOCKS_PER_SEC → Time calculator finished
- stbi_write_jpg() - stbi_image_free() → Storing the value.
- MPI_Finalize() Finishing it.


![image](https://user-images.githubusercontent.com/85889196/172705788-6a7f829f-518f-484f-91f9-2b547a498021.png)



![image](https://user-images.githubusercontent.com/85889196/172705658-cc349222-4f6b-4f69-9ed9-90240501f193.png)

