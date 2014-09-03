# Linux Command Set for Architecting
--------------------------------------------------------------------------------

- tree
- lsusb
- spawn和expect
- ssh
- sync
- rsync
- losetup
- sfdisk


Let's create an empty image that we format with a filesystem and mount it.

    dd if=/dev/zero of=loopback.img bs=1G count=3
    mkfs.ext3 loopback.img
    sudo mount -o loop loopback.img mnt-loop

