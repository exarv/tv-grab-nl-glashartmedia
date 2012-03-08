tv_grab_nl_glashartmedia
========================

Author: Robert Verspuy
Website: http://exarv.nl

How to use
==========

Mythtv
------

Setup a Cronjob for the user mythtv 

0 6 * * * cd ~/tv-grab-nl-glashartmedia; ./tv_grab_nl_glashartmedia.php --nocacheepg --progress > epgdata.xml; mythfilldatabase --file 1 epgdata.xml

