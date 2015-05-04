# Preperation #

Make sure your PC is connected to the IPTV vlan of you fiber ISP. For more information see: http://exarv.nl/mythtv/iptv-recording.

# Download #

Download the latest version from https://drive.google.com/folderview?id=0Bx_sClKPtq8ZYVBCWjRGd1JETk0&usp=sharing

# Installation #

Download the latest tgz as user mythtv
```
su - mythtv
wget "http://tv-grab-nl-glashartmedia.googlecode.com/files/tv-grab-nl-glashartmedia-v0.6.1.tgz"
tar xvzf tv-grab-nl-glashartmedia-v0.6.1.tgz
cd tv-grab-nl-glashartmedia-v0.6.1
```

# Configuration grabber #

Configure the script by choosing which channels should be included in the xml output
```
su - mythtv
cd tv-grab-nl-glashartmedia-v0.6.1
./tv_grab_nl_glashartmedia --configure
```

You can answer the questions about the channels with :
  * d = yes, include the channel in xml output, with all details
  * y = yes, include the channel in xml output, but only with title, no other details
  * n = no, do not include the channel in the xml output

# Configuration MythTV #

In mythtv you must setup a xmltvid for every channel to let mythtv know which channel identifier in the xml corresponds to which channel. You can do this via mythweb (Settings -> TV -> Channel Info).

The xmltvid you must use are the same as the channelcode used by the graber in the confuration with the default suffix ".glashart". Some examples:
  * ned1.glashart for Nederland 1
  * ned2.glashart for Nederland 2
  * ned3.glashart for Nederland 3
  * rtl4.glashart for RTL 4
  * rtl5.glashart for RTL 5
  * sbs6.glashart for SBS 6
  * rtl7.glashart for RTL 7
  * rtl8.glashart for RTL 8
  * net5.glashart for Net 8
  * veronica.glashart for Veronica

# Download data #

Download EPG data and feed it to MythTV
```
su - mythtv
cd tv-grab-nl-glashartmedia-v0.6.1
./tv_grab_nl_glashartmedia --nocacheepg --progress > epgdata.xml
mythfilldatabase --file 1 epgdata.xml
```