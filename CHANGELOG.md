# Changelog

Made a new file because there have been a few changes recently.
   
# Changes 26/07/2020

## Multi tracker support
Adds support for OPS to smoked-salmon  
use --tracker or -t option to specify which tracker to upload to.  
adds options DEFAULT_TRACKER and TRACKER_LIST (have a gander at config.py.txt example)    
The script will offer the choice to upload to multiple trackers with one command.
This can be disabled with MULTI_TRACKER_UPLOAD=False
So far only RED and OPS are supported but the groundwork is there for other gazelle sites.
(Setup documentation may need updating)    

## Requests checking
Added the option to input a request id to be filled as you upload. (-r)   
The script now searches site requests as you upload and offers a choice to fill one of the requests found.  
This can be disabled with CHECK_REQUESTS=False  

## Added recent upload dupe check
The script now searches for recent uploads similar to the release being uploaded in the site log.  
This is particularly useful for special chararacters in recent content on RED or anything not yet showing up in the regular search due to sphinx.  
This function might be a little slow.
It usses a similarity hueristic with an adjustable tolerance (default is LOG_DUPE_TOLERANCE=0.5)  
This extra dupe check can be disabled with CHECK_RECENT_UPLOADS=False  

## Added option USE_UPC_AS_CATNO
The script now uses the upc as the catalogue number on site if a catalogue number is not found.  
This function will also append the UPC to whatever catno is found.  
This can be disabled with USE_UPC_AS_CATNO=False  

## Spectrals afer upload option. (-a)
This option will tell the script to only generate spectrals after the upload is complete.   
It is advised that you only use this if you are in a hurry to get the torrent uploaded.  
It important that you still always check your spectrals!
This feature then edits the existing torrent to add the spectrals to the description (and makes a report if asked to).
It might be advisable good idea to only seed your torrents after you have checked your spectrals.


## checkspecs
Added command to check spectrals for a torrent on site.  
This is a standalone command that can check and add spectrals to the description of an already uploaded torrent. This requires you to have the files locally.
(see checkspecs -h for more info)  

# Other Changes
The script can use an API key for uploading on RED (full support still pending API coverage)  
Streamlined the way a torrent group id is picked as you upload.
A library is used for rate limiting (requirements.txt has been updated)
Added choice to test 24 bit flac for upconverts as you upload.  


