# OverlayFS 
Little experiment with overlayfs to understand how it works

## Usage
* Clone this repo
* cd into the repo
* create these 2 dirs `mkdir work merged`
* execute `sudo mount -t overlay overlay -o lowerdir=./layer1:./layer2,upperdir=./layer3,workdir=./work ./merged`

You can now play around editing and adding files and directories to understanding what's going on under the courtains.

## Description
* **layer1** and layer2 are the 2 lowest directories, this are read-only basically
* **layer3** is the upper dir where the writes go 
* **work** is a directory used by overlayfs 
* **merged** is the mount point



