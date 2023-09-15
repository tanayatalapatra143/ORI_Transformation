import os
from osgeo import gdal

# folder path containing .tif files
folder_path = input("Input path : ")

# create an empty list to store the .tif file names
tif_list = []

# loop through each file in the folder and append .tif files to the list
for file in os.listdir(folder_path):
    if file.endswith(".tif"):
        tif_list.append(os.path.join(folder_path, file))

for tif in tif_list:
    print(f"Validating for {tif}")
    ds=gdal.Info(tif,format="json")
    print(ds)
    coordinateSystem = ds['coordinateSystem']['wkt']
    compression = ds["metadata"]["IMAGE_STRUCTURE"]["COMPRESSION"]
    compression_quality = ds["metadata"]["IMAGE_STRUCTURE"]["JPEG_QUALITY"]
    int_compression_quality = int(compression_quality)
    conversion = ds["metadata"]["IMAGE_STRUCTURE"]["LAYOUT"]

    if "WGS 84 / UTM zone 43N" in coordinateSystem:
        pass
        if conversion=='COG':
            pass
            if compression=='YCbCr JPEG':
                pass
                if int_compression_quality>=90:
                    print("VALIDATION SUCSSESFULL")
                else:
                    print('Invalid compression_quality')
            else:
                print('Invalid compression')
        else:
            print('Invalid conversion')
    else:
        print("Invalid coordinateSystem")
