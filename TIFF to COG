from osgeo import gdal
import os
#input_file_path='E:\\LOT_6\\4. DSM-ORI\\DSM'
#output_file_path='\\media\\upor5/2838202c-b59c-4491-973c-1391ae62911f\\ARALAPURA_00308_191_ORTHO123.tif'

#print('Use "\\\\" instead of "\\\"')
      
folder_path = input('Input folder path (Use "\\\\" instead of "\\\"):')
folder_path_output = input('Output folder path (Use "\\\\" instead of "\\\"):')

for file_name in os.listdir(folder_path):
    if file_name.endswith('.tif'):
        input_file_path=os.path.join(folder_path, file_name)
        print(input_file_path)
        output_file_path=os.path.join(folder_path_output, file_name)
        print(output_file_path)
        
        #gdal_translate -of COG input.tif output.tif

        
        gdal.Warp(output_file_path,input_file_path,format='cog',creationOptions=['COMPRESS=JPEG','QUALITY=90'])
    
