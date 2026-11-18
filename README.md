# OneiOS S25+ port patch

This repository contains a patch for [xaxaapple/s25ver](https://github.com/xaxaapple/s25ver), based on upstream commit `4b530c7`.

It adds the Galaxy S25+ (SM-S936 / pa2q / SM8750) port notes, a separate S25+ hardware probe mode, and a host regression case for the 1440×3120 display mode. The S25+ changes and research credit the original S25 work by **xaxaapple**.

## Apply the patch

```sh
git clone https://github.com/xaxaapple/s25ver.git
cd s25ver
git checkout 4b530c7
curl -L https://raw.githubusercontent.com/Clysmic590/OneIOS-s25plus/main/patches/s25-plus-port.patch -o /tmp/s25-plus-port.patch
git apply --check /tmp/s25-plus-port.patch
git apply /tmp/s25-plus-port.patch
```

The patch was host-tested for its 1440×3120 display path. OneiOS has not yet been run on an S25+ handset.