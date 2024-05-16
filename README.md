# Use-pandarallel-for-geopandas
`pandarallel` (https://github.com/nalepae/pandarallel) is an effective tool for multi-processing in Pandas. However, Geopandas's spatial computation is not supported. This project provides a quick instruction for a solution to make Geopandas available.

## Warnings
1. The method will create a new folder named "/mnt/ramdisk", and the files in "/mnt/ramdisk" and "/dev/shm" will be deleted. 
1. The method can only be used for Linux systems because `pandarallel` doesn't support Windows.
2. You need to have a large RAM space, e.g., 32G.
## The ideas of the solution
1. Create a virtual RAM disk for quick IO.
2. Calculate each feature in a function and save them in the RAM disk.
3. Combine all of them into one file and save it as a shapefile.
## Others
After testing, the solution has no RAM overflow problem and also doesn't have a "No space left on device" problem.

