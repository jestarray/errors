## Application crashing x11:
```
X Error of failed request:  GLXBadFBConfig
  Major opcode of failed request:  150 (GLX)
  Minor opcode of failed request:  21 (X_GLXGetFBConfigs)
  Serial number of failed request:  169
  Current serial number in output stream:  169
```
I got this error when trying to run my game's cross compiled binary(`x86-64` -> `aarch64-unknown-linux`). These specific numbers (150, 21, 169, 169), I can say have nothing to do with x11 but the binary linking to my local x86-64 /usr/lib/x11 libs rather than the aarch64 x11 libs. 

Solution: Doublecheck your builds log file(in my case cmakes generated make) and make sure they aren't linking to your the wrong x11
