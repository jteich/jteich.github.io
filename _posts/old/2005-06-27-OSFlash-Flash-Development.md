---
redirect_from:
  /blog/2005/06/with-regard-to-my-last-post-about.html
---
With regard to my [last post]({% post_url old/2005-06-08-Flash %}) about [MTASC](http://tech.motion-twin.com/mtasc.html), I realized that an actions compiler is only part of the story for creating flash content. You also need to be able to create a resource file with items that include images and flash movies. You also need to have a development environment that will allow you to do all this efficiently. [OSFlash](http://osflash.org/doku.php) is a great resource that has a collection of open-source projects for creating and editing flash content. As far as a development environment goes, it looks like plug-ins for [Eclipse](http://www.eclipse.org/) are the way to go. One tool, [swfmill](http://swfmill.org/), looks very promising but it is in a state of flux. It converts between an XML format and a SWF format. 

One piece of the puzzle that is still missing is a graphical timeline editor like what would be found in Flash MX. I anticipate that someone will step up to the plate to start work on such a project. It may be developed as a front-end to swfmill, creating a XML document that swfmill will compile to a SWF file. 

Update: There is a timeline animation editor similar to Macromedia Flash out there. It is a project called [KToon](http://ktoon.toonka.com/). I don't know how developed it is, but it looks good and can export to Flash format amongst other formats. It is not designed specifically for Flash development, and I have not played with it, so I don't know if it fills the gap for a complete open source Flash development platform.
