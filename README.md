# tasker-resize-images
Automatically resize images on your Android phone using [Tasker](https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm).

This task can be found on Taskernet [here](https://taskernet.com/shares/?user=AS35m8lp%2FKkm%2B8UbZhHqE5Y4xnByvXtx0JMDOCGm0w6uyiTpJO0jakx9uvUppJnAx%2BE%3D&id=Task%3AResize+Jpeg+Files+And+leave+Originals#).

You should add this to a profile that triggers when files are modified in DCIM/Camera/ or wherever your Camera app places its images. It will create resized copies of the images in DCIM/Resized/ which are more useful for using in Google Photos, or for sharing. The GPS coordinates are saved in the resized files.

# Workflow
I use Syncthing to copy my images to my computer. On my computer I import them into Lightroom. When they are deleted from the synced folder, they are deleted from my phone.
To facilitate that I created a new task called "Backup Photos". That does the following:
* Perform Task: Resize Jpeg Files And Leave Originals
* Run Shell: Command mc /sdcard/DCIM/Camera/*.jpg /sdcard/Download/jpeg/
* Stop

I add that task to my launcher where I periodically tap it. It resizes any remaining files, and moves the original Jpeg files out of the way for backup.

My Download directory is synced so I point Lightroom at the jpeg directory where it finds my camera phone photos for import. Files are moved into Lightroom's directories where they are backed up automatically.
