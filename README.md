# ndvi-pipeline-dask

This project generates a time series of NDVI (Normalized Difference Vegetation Index) using PlanetScope imagery clipped to the study area. The analysis is built using Python libraries for efficient raster processing.

### Python Libraries Used

- geopandas  
- pandas  
- rioxarray  
- xarray  
- numpy  
- matplotlib  
- dask

## 🔄 Workflow Steps

1. **Load shapefile** for the study area.
2. **Read TIFF files** and sort by date.
3. **Clip each TIFF** to the study area.
4. **Calculate NDVI** using Red (B3) and NIR (B4) bands.
5. **Stack all NDVI layers** into a single xarray time series.
6. **Compute mean NDVI** over space for each date.
7. **Plot and save** the NDVI time series as a PNG.
8. *(Optional)* Save the full NDVI stack as a NetCDF file.

## 🛰️ Assumptions

- TIFF files are PlanetScope surface reflectance imagery (scale factor 10,000).
- Red = Band 3, NIR = Band 4.
- Filenames begin with a date in `YYYYMMDD` format.

## 🖼️ Output

- `ndvi_time_series.png`: NDVI time series plot
- `ndvi_stack.nc`: (optional) NDVI time stack in NetCDF format

## ⚙️ Notes

- Uses Dask to allow scalable/lazy evaluation (optional).
- Final plot shows mean NDVI across all pixels in the clipped region.

## 👤 Author

**Sabbir Delowar**  
