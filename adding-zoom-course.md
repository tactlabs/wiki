/ [Home](index.md)

## Downloading Videos from Zoom

* Create a 'tact-videos' folder in Videos.
* Rename each  zoom recording as 'Event - Host - Month date, Year'
* Download the videos with the same filename into '/Videos/tact-videos' folder.
* Save and run this code as app.py from the current folder.


## app.py 
```
import os
# List all files in a directory using os.listdir
basepath = '/home/...../Videos/tact-videos'
for entry in os.listdir(basepath):
    if os.path.isfile(os.path.join(basepath, entry)):
        print(entry)
        
```
-------------------------------------------------

## Uploading in Vimeo:

* Clone 'tact-vimeo-upload' repository and install the packages.

****
```
git clone git@github.com:tactlabs/tact-vimeo-uploader.git
cd tact-vimeo-uploader
pip install -r requirements.txt
```
****

* Add .env and update the 'FILE_BASE_PATH'
* Fill the all the coloumns with the required details in VimeoVideoUpload base sheet.
( Note: Only the filename must be with 'filename.mp4' format)
* Replace the current sheet with the existing sheet in 'tact-vimeo-upload' folder.
* Run app.py and paste all the links in VimeoVideoUpload upload-history sheet.
(Note : After updating in upload-history sheet, the base sheet must be empty)

-------------------------------------------------
Upload a Course:

* Fill the all the coloumns with the required details in Course Migration base sheet.
* Download the sheet and upload it in 'http://admin.featurepreneur.com/' - Courses
* Update the upload-history sheet and the base sheet must be empty.
-------------------------------------------------