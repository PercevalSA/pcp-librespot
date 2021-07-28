# Librespot for piCore Player

This is a tcz extension to install on piCore Player.
The purpose is to gain stability and performance compared to the LMS version.

## installation

```
# create the extension
mksquashfs pcp-librespot pcp-librespot.tcz

# put it on pcp
scp pcp-librespot.tcz tc@pcp.local:
ssh tc@pcp.local
mv -v pcp-librespot.tcz /etc/sysconfig/tcedir/optional

# activate start up on boot
echo pcp-librespot.tcz >> /etc/sysconfig/tcedir/onboot.lst
echo "/usr/local/etc/init.d/librespot start" >> /opt/bootlocal.sh 
pcp bu

```

reboot or launch the extention with `tce-load -i pcp-librespot`

## creation

Librespot must be cross-compiled and placed in the `sbin` folder as `librespot`.

get the librepot submodule
```
git submodule update --init --depth 1
cd librespot

```

### Cross Compilation

You must be on Debian 11 mininmum for the cross compilation to work
