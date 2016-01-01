---
redirect_from:
  /blog/2005/01/yesterdays-big-project-involved.html
---
Yesterday's big project involved creating a PDF programmaticaly in Perl. It seemed that the best API to use was PDF::API2. The big problem with getting started with this API is that it is so poorly documented. I had to figure out how to use the module by examining a few example scripts, none of which covered everything that I needed to do. So, I am writing up a 10 second primer that I would have found useful when I was trying to get started using PDF::API2. 

First you create a new PDF document object with the call 

    my $pdf=PDF::API2->new; 
 
You then create a page in the PDF document by calling $page=$pdf->page; You will also need resources such as images and font objects to work with in you document. These resources are created from the PDF object like such: 

    $font=$pdf->corefont('Helvetica',-encode=>'latin1'); 
    $boldfont = $pdf->corefont('Helvetica-Bold', -encode=>'latin1'); 
 
You will need to set the page size. You do this by specifying the size in points (a point is 1/72 of an inch). You can also use an alias such as 'LETTER' or 'A4' to specify the page size. The following to statements are equivalent: 

    $pdf->mediabox(612,792); 
    $page->mediabox('LETTER'); 
 
There are two approaches that you can use to draw text on the screen. One is to use a text object that you get from the page object. Here is an example: 

~~~~ perl
#get the text object 
my $text=$page->text; 
#select the font object and the font size 
$text->font($font,20); 
#specify where this text is going to go 
$text->translate($x , $y); 
#print some text 
$text->text($aString); 
#print it to the left of the chosen location (for right justified text) 
$text->text_right($aString); 
#You can use the textlabel method instead, which is more compact: 
#(this doesn't work for right justified text) 
$text->textlabel($x, $y, $font, $fontsize, $aString); 
#If you want to do some graphics work, you will need to get the graphics object from the page: 
$gfx=$page->gfx; 
$gfx->strokecolor('blue'); 
$gfx->move($x, $y); 
$gfx->line($x2, $y2); 
#dunno why the next line is necessary, but it is - or you wont see the line. 
$gfx->stroke; 
#you can add more pages 
$newpage->$pdf->page; 
#You will have to get the text object and graphics object separately, 
#and set the mediabox (although I think that the media box can 
#be set globally from the PDF object); 
..... 
#Once you are finished, you may want to save your PDF like such: 
$pdf->saveas($pdffile); 
#or you may want to print it directly: 
open PRINTER, "|lpr"; 
print PRINTER $pdf->stringify; 
close PRINTER; 
#once you are done, destroy the document object: 
$pdf->end(); 
~~~~

I still have to write up how I added a barcode to the document. 
