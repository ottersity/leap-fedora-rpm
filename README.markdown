leap-fedora-rpm
===============

# LeapMotion RPM package for Fedora. #

Since alien deb to rpm transformation does not work for fedora 19 (due package conflict) I've decided to make my own RPM packaging for Leap binaries.

## How to generate the RPM ##

Due license issues I can't provide the RPM packaged already, but it's pretty easy to do it!.

Go to https://developer.leapmotion.com/dashboard and download the binaries for Linux.
Once you have the file, open a terminal in the folder where the file was downloaded and type/execute these lines:

### For x86 ###

<code>
git clone git@github.com:atejeda/leap-fedora-rpm.git
tar xzf DeveloperSdk_LM_0.8.0.5300_Linux.gz
cp Leap_Developer_Kit_0.8.0_5300_Linux/*.deb leap-fedora-rpm/SOURCES/
make -C leap-fedora-rpm clean all
</code>

### For x64 ###

<code>
git clone git@github.com:atejeda/leap-fedora-rpm.git
tar xzf DeveloperSdk_LM_0.8.0.5300_Linux.gz
cp Leap_Developer_Kit_0.8.0_5300_Linux/*.deb leap-fedora-rpm/SOURCES/
cd leap-fedora-rpm
make clean all install
</code>

## Install it ##

Generated RPM is located under RPMS folder, e.g.:

<code>
sudo rpm -e Leap-0.8.0 # just in case
sudo yum install -y leap-fedora-rpm/RPMS/i686/Leap-0.8.0-x86.5300.f19.i686.rpm
</code>


## Using it ##

I've demonized the leapd binary, for start the daemon use systemctl, e.g.:

 *   Start the daemon: sudo systemctl start leap.service
 *   Stop it: sudo systemctl start leap.service
 *   Get the status : sudo systemctl start leap.service
 *   Enable it: sudo systemctl start leap.service

 After start the daemon, if the lights of your leap are turned on, so far so good...

Binaries to execute:

 *   Visualizer
 *   Recalibrate
 *   LeapControlPanel
 *   ScreenLocator


## Support? really? ##

If you want to use it, modify, extend it, follow the normal github workflow, means that must be fork it, merge it, or create a ticket if there's any bug.