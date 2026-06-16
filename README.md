# rockfallveg
rockfallveg is a small R package, that analyses the vegetation on rockfall bodies after the event. It uses multispectral raster data (e.g. Sentinel) and calculates and compares NDVI maps and values 

# Installation
Install this package in R with the command

```r
install.packages("remotes")
remotes::install_github("JAschauerBO/rockfallveg")

# Load package:
library(rockfallveg)

# Uninstall:
remove.packages("rockfallveg")
```

# Usage
Use this package like this:

```r
raw_tiffs <- rfv.import_tiff(raw_data_dir = "C:/Users/jakob/Uni/Erasmus/Telerilevamento/Esame/WD/Raw Data")
roi <- rfv.import_roi(wd_dir = "C:/Users/jakob/Uni/Erasmus/Telerilevamento/Esame/WD")
ndvi_list <- rfv.ndvi(imported_tiffs = raw_tiffs)
v_ndvi_df <- rfv.crop(ndvi_list = ndvi_list, roi = roi)

print(rfv.plot_box())
print(rfv.plot_violin(scale = "width"))
print(rfv.plot_RGB(rast = raw_tiffs[["YYYYMM"]]$stack))
print(rfv.plot_map())
```
