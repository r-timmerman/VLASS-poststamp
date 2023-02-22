# VLASS-poststamp

vlass_search.py is a simple Python script that allows the user to easily obtain cutouts from the VLA Sky Survey (VLASS; Lacy et al. 2019) from the command line. This code is strongly based on the work by GitHub user annayqho, but is easier to use and returns .fits files rather than color images.

The user can request a poststamp by either delivering:
1. Six numbers (RA hours, minutes and seconds; Dec degrees, minutes and seconds)
2. Two numbers (RA degrees; Dec degrees)
3. A .ms file, in which case the script will grab the coordinates of the pointing center of the data set.

By default, the script identifies the tile and subtile containing the requested coordinate, downloads the selected subtile and crops this subtile to a 256x256 arcsecond (1 arcsecond = 1 pixel) poststamp image. At this point in time, the code will only check Epoch 1 data from VLASS, but will in the (near) future also use Epoch 2 data. By default, the code will also consider QA_rejected data, as this is often found to be usable to some extent.

The code can be easily manipulated to either crop the subtile or return the entire subtile, return a smaller or larger poststamp and consider QA_rejected data or not. This can be done at the top of the code, right below the imports. At this moment, these settings are not configurable from the command line.

N.B.: The script will require the file "VLASS_dyn_summary.php" in the same folder to work, as this file contains the coordinates and names of the VLASS tiles. In future updates, this file can also be obtained from the NRAO servers, but as I've also experienced some problems with this, I decided to include this file in the repo for now.

For more information about the VLA Sky Survey, see the following webpage: https://science.nrao.edu/vlass/data-access/vlass-epoch-1-quick-look-users-guide
