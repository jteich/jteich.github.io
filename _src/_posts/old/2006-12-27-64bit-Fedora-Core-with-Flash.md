---
redirect_from:
  /blog/2006/12/about-using-64-bit-version-of-fedora.html
---
About using the 64 bit version of Fedora Core and Web browsing using the Flash plugin.
I have an 64-bit AMD Athlon processor so when I wanted to install Fedora, I took the 64 bit version. The 64 bit version is great, but you run into a problem. For web browsing, there are some Firefox plugins that I use. The most important one to me is that flash plugin, which is required in order to view a lot of web content that is out there. Here is the problem: You can't use the flash plugin, which is distributed as a 32 bit binary together with a browser that is running off of a 32 bit binary. So, I went and ran 'yum download firefox.i386'. Good, now you have the 32 version also installed. I tried to run Firefox, but that 64 bit version started up.
First I tried to uninstall Firefox by typing 'yum remove firefox.x86_64', but that tried to remove too many other important packages.
Turns out that the file through which Firefox starts up from on Fedora is actually a script. I edited this script and commented out lines 40-43 in order through which the script will select the 64 bit executable to run. Here are the lines of code that need to be commented with pound ('#') symbols in order for this to work:

~~~ bash
if [ -x "/usr/lib64/firefox-1.5.0.9/firefox-bin" ]
then
MOZ_LIB_DIR="/usr/lib64"
fi
~~~

The 32 bit version of Firefox will now startup and be able work with the 32 bit plugins. BTW, I am using the beta version of Flash 9 for Linux, you can get it [here](http://labs.adobe.com/technologies/flashplayer9/). It is able to display new content that can't be seen with Flash 7, the current release version for Linux. It may have some stability problems though.
