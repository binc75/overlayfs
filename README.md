# OverlayFS 
Little experiment with overlayfs to understand how it works

## Usage
* Clone this repo: `git clone git@github.com:binc75/overlayfs.git`
* cd into the repo: `cd overlayfs/`
* create these 2 dirs `mkdir work merged`
* execute `sudo mount -t overlay overlay -o lowerdir=./layer1:./layer2,upperdir=./layer3,workdir=./work ./merged`
* `cd merged`

You can now play around editing and adding files and directories to understanding what's going on under the courtains.

## Description
* **layer1** and **layer** are the 2 lowest directories, this are read-only basically
* **layer3** is the upper dir where the writes go 
* **work** is a directory used by overlayfs 
* **merged** is the mount point

## Tips
```bash
$ df -h | grep merged
overlay                    467G  270G  173G  61% /tmp/overlayfs/merged

[nbianchi@nano:/tmp/overlayfs/merged]-[14:20:56][⎈ ][⎇  ]
$ mount | grep merged
overlay on /tmp/overlayfs/merged type overlay (rw,relatime,lowerdir=./layer1:./layer2,upperdir=./layer3,workdir=./work)
```

## Cleanup
`sudo umount ./merged`


