tv_grab_nl_glashartmedia
========================

Author: Robert Verspuy
Website: http://exarv.nl
Project Site: http://code.google.com/p/tv-grab-nl-glashartmedia

How to use
==========

Mythtv
------

Setup a Cronjob for the user mythtv 

0 6 * * * cd ~/tv-grab-nl-glashartmedia; ./tv_grab_nl_glashartmedia.php --nocacheepg --progress > epgdata.xml; mythfilldatabase --file 1 epgdata.xml

