1. Before running the system, you will want to download Panoply for visualizing the output files if you don't already have it. 
It is available at https://www.giss.nasa.gov/tools/panoply/
Scroll down to the "Get Panoply" section and click "Download Panoply", extract the files, and run the executable.

2. Before building, you will need to get the YAKL submodule. To do this run the command "git submodule update --init --recursive".
To build and compile the system, cd to miniWeather/cpp/build/scripts and run build.sh. 
This script will also run the provided test suite to make sure everything is working properly.

3. Now, to start gathering performance metrics, you can run the "run_THERMAL_x.sh" scripts, with "x" representing the number of MPI ranks used.
If you run 1-16, you should be able to recreate our timing results mentioned in the table in our draft. 
After each run, the CPU Time will be shown just under the last *** OUTPUT *** line (as you use more MPI ranks, you'll need to scroll up through more redundant output).

4. To visualize the output you've just created, navigate back to the build directory and download one of your "output_THERMAL_x.nc" files to your local machine. 
If you're in VSCode, you can just right-click on it and click "download" to transfer it.
Otherwise, you'll need to use SCP or a similar file transfer protocol to get it out of the cluster and onto your local machine.

Once it's downloaded, head over to Panoply and open the file in there. It will show 5 different datasets, but we're only interested in 
the one named "theta". Double-click on that one, and when Panoply asks you what type of plot you want to create, use the "color contour" option,
then change the X axis so it uses x and change the Y axis so it uses z. Click "create", and it will bring up the result. Now, you can increase t 
so the plot shows a time-lapse of the weather simulation. For THERMAL, it will look like a circle at the bottom of the plot that morphs into a 
mushroom-cloud-like shape and expands.
