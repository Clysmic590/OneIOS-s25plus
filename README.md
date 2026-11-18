# OneiOS S25+ port patch

This repository contains a patch for [xaxaapple/s25ver](https://github.com/xaxaapple/s25ver), based on upstream commit `4b530c7`.

It adds the Galaxy S25+ (SM-S936 / pa2q / SM8750) port notes, a separate S25+ hardware probe mode, and a host regression case for the 1440×3120 display mode. The S25+ changes and research credit the original S25 work by **xaxaapple**.

## Build the manager APK on GitHub

Open **Actions → Build OneiOS S25+ APK → Run workflow**. When it finishes, download the `OneiOS-S25Plus-debug` artifact from that run. The workflow checks the S25+ profile, builds the debug APK, and provides a SHA-256 checksum.

If the build fails while resolving tribalfs packages, add a `GH_PACKAGES_TOKEN` Actions secret with `read:packages`; optionally add `GH_PACKAGES_USER`. The APK is only the manager app: it does **not** contain the OneiOS runtime package or an iOS system image.

## Apply the port patch to the runtime source

```sh
git clone https://github.com/xaxaapple/s25ver.git
cd s25ver
git checkout 4b530c7
curl -L https://raw.githubusercontent.com/Clysmic590/OneIOS-s25plus/main/patches/s25-plus-port.patch -o /tmp/s25-plus-port.patch
git apply --check /tmp/s25-plus-port.patch
git apply /tmp/s25-plus-port.patch
```

The display path was host-tested for 1440×3120. OneiOS has not yet been run on an S25+ handset.