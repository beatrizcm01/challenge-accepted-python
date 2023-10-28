# Recruiting Process - Data Engineer Jr (Python Challenge)

To approach this challenge I chose to work with the Xarray library because it's very efficient to work with labelled multidimensional data such as the one in this challenge.
## Initial Steps

Proceed by cloning or forking my repository. Then, make sure to have the requirements installed as instructed below.

### Requirements (Python 3.8.10)
The following libraries are present in the requirements.txt file:
- NETCDF4==1.6.5
- Xarray==2023.1.0
- Numpy==1.24.4
- Matplotlib==3.7.3
- Seaborn==0.13.0

They can be installed following the command (locally or in a virtual enviroment):
````
pip install -r requirements.txt
````
## Code Execution    
All of my work is present in the challenge.ipynb JupyterNotebook. After the requirements are installed you can proceed with the cells execution. The steps are explained in the notebook itself, but below follows a summary of my work.
### Data Loading

The following files were loaded as xarray datasets:
- forecast.nc
- observation.nc

They are both multidimensional data arrays containing three attributes (latitude, longitude, time) and one variable (temperature). The dimensions are 25 (lat) x 37 (lon) x 72 (time), making a total of 66600 data points for each matrix.

### Data Transformation

Some data transformation was performed with the datasets to rename attributes, dimensions, convert unities and replace values in order to calculate the RMSE index. One important note is that, because I noticed that not all correspondent latitudes and longitudes were exactly the same in the forecast and observation datasets, I considered the true coordinates to be the ones present in observation.nc. This point is also ellaborated in the Jupyter Notebook.

The results for the RMSE index calculated for every six hours are stored in the rmse.nc file. 

### Data Visualization
The data visualization was performed with Matplotlib and Seaborn. I presented the two-dimensional heat maps for the RMSE index for the given time period, where the coordinates are the latitude and longitude. I also presented the RMSE in São Paulo for each given period with a bar plot and a line graph of RMSE through time both for the period of 6h and for the RMSE calculated hourly.
