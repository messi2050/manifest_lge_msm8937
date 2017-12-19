# Device repository manifest for the LG Stylo 2 Plus (ph2n).

*For use in tandem with the LineageOS source (or any other appliciable source).*

### Setting up the LineageOS source.
If you are planning to build LineageOS, you will need to setup a build environment for Android. See instructions on how to do that here.

Once you have your build environment setup, go ahead and make a directory for the source code to reside, then enter that directory. In my case:
>mkdir lineage && cd lineage

After you made the directory, go ahead and initialize the LineageOS repository in that folder. I will use LineageOS 14.1 as an example:
>repo init -u git://github.com/LineageOS/android.git -b cm-14.1

Now, once you have done that, you will need to download the manifest from this repository:
>curl --create-dirs -L -o .repo/local_manifests/ph2n.xml -O -L https://raw.githubusercontent.com/messi2050/manifest_lge_ph2n/cm-14.1/ph2n.xml

Finally, start the sync process:
>repo sync


### Building
Once you have synced the source, run the following commands to start building:
>. build/envsetup.sh

>lunch lineage_ph2n-userdebug

>make otapackage
