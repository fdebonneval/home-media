# home-media
My home server / rPi configurations and tricks

# Mounting my Freebox server disk on my Openelec rPi
````
  mount -t cifs -o username=user,rw //192.168.xx.254/Disque\ dur freebox
````
thanks to : http://www.raspberrypi.org/forums/viewtopic.php?t=19570&p=190670
# Creating a partition on the full extarnal disk
````
  parted -s /dev/sda -- mklabel gpt mkpart primary 0GB -1MB
````
I tried first to create the partition with -1b for the last bloc, but parted did not let me do it. Someday I'll search the explanation :)
# Creating the fs on the fresh partition
````
  mkfs.ext4 /dev/sda1
````

