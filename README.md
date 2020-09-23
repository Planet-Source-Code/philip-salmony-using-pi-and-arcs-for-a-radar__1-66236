<div align="center">

## Using Pi and Arcs for a Radar

<img src="PIC200681011112435.gif">
</div>

### Description

Shows you how to use Pi for drawing Arcs(part of a circle) to use as a radar.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Philip Salmony](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/philip-salmony.md)
**Level**          |Intermediate
**User Rating**    |5.0 (15 globes from 3 users)
**Compatibility**  |VB 6\.0
**Category**       |[Graphics](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/graphics__1-46.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/philip-salmony-using-pi-and-arcs-for-a-radar__1-66236/archive/master.zip)





### Source Code

<H1><font color="#FF0000">Using Pi and Arcs for a Radar</font></H1>
<br><br>
Hi, I'm Philip and I'm going to show you to how to make a great radar for games or other stuff. <br>So...the first thing you need to know is what Pi is ! Pi is a number to calculate stuff with circles. Pi goes on for EVER !!! But of course we only need a few digits :
<p>Pi = 3.14159265358979 (we need a double data type for that!)</p>
<p>You will need to put a Timer (called RadarSearcher) and a PictureBox (called
RadarBox) on the Form .So now we need to declare the globals (Pi and the Arcsize(in degrees)). So just type this
in :</p>
<p><br>
<font color="#008000">
'Globals for radar</font><br><font color="#0000FF">Const</font> PI <font color="#0000FF"> As Double</font> = 3.14159265358979
<font color="#008000">'We need Pi for calculating where the arc should be and at
what angle</font><br><font color="#0000FF">Const</font> ARCSIZE <font color="#0000FF">As Integer</font> = 45
<font color="#008000"> 'Lets take an arc of 45 degrees size</font></p>
<p>Then we need to create the sub for the Timer. This is the main part (the
core) of the program which calculates and displays the radar. Once you've typed
the next block of code in set the Enabled property of the Timer to true (which
is actually the defaut, but just making sure) and the Interval property of the
Timer to 100. Having the Interval property at 100 makes the Radar look
smooth-running. If you want to you can set the Interval property to 1000 and see
what happens. So enough of the boring stuff... Let's get down to business :</p>
<p><font color="#008000">'Timer Sub for calculating and displaying the radar</font></p>
<p><font color="#0000FF">Private Sub</font> RadarSearch_Timer() <font color="#008000"> 'The main Timer (Interval set 100 is
standard)</font><br>
<font color="#0000FF">
Dim</font> X <font color="#0000FF"> As Integer</font>, Y <font color="#0000FF"> As
Integer</font>, r <font color="#0000FF"> As Integer</font> <font color="#008000">'X
and Y Coordinates of the Arc</font><br>
<font color="#0000FF">
  Dim</font> ArcStart <font color="#0000FF"> As Single</font>, ArcEnd<font color="#0000FF"> As Single</font>
<font color="#008000">'The beginning position of the Arc (in degrees)</font><br>
<font color="#0000FF">
  Dim</font> nCount <font color="#0000FF"> As Integer</font> <font color="#008000">'Main
loop variable (used to move the arc)</font><br>
<p>'Make sure that the forecolor is vbRed and the backcolor is vbBlack ! I tried
using a different color combination and it didn't display anything !!!
 RadarBox.FillColor = vbRed
<br>RadarBox.BackColor = vbBlack<p><font color="#008000">'The
next 3 lines make the arc fit into the PictureBox perfectly</font>
<br>
 X = RadarBox.ScaleWidth - 4<br>
 Y = RadarBox.ScaleHeight - 4<br>
 r = X / 2<p><font color="#008000">'The next 4 lines set the drawmode stuff and
draw a circle (NOT AN ARC) for the arc to move in</font>
<br>
 RadarBox.DrawWidth = 1<br>
 RadarBox.DrawMode = vbCopyPen<br>
 RadarBox.FillStyle = vbFSTransparent<br>
 RadarBox.Circle (X / 2 + 2, Y / 2 + 2), r<br>
<p><font color="#008000">'These next 2 lines also do some drawmode
stuff</font>
<br>
 RadarBox.DrawMode = vbXorPen<br>
 RadarBox.FillStyle = vbSolid<br>
<p><font color="#008000">'Now... the big one ! This rotates and draws the arc 1
full rotation.</font>
<br>
<font color="#0000FF">
 For</font> nCount = 0 <font color="#0000FF"> To</font> 360<br>
&nbsp;&nbsp;&nbsp; ArcStart = nCount<br>
&nbsp;&nbsp;&nbsp; ArcEnd = nCount + ARCSIZE<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <font color="#0000FF">If</font> ArcEnd > 360
<font color="#0000FF"> Then</font> ArcEnd = ArcEnd - 360<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; RadarBox.Circle ((X / 2) + 2, (Y / 2) + 2), r, , -ArcStart * PI / 180, -ArcEnd * PI / 180<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; DoEvents<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; RadarBox.Circle ((X / 2) + 2, (Y / 2) + 2), r, , -ArcStart * PI / 180, -ArcEnd * PI / 180<br>
<font color="#0000FF">
 Next</font> nCount<br>
<br>
<font color="#0000FF">
End Sub</font>
<p>&nbsp;</p>
<p>I really hope you liked this tutorial. If you did please vote for me.</p>
<p>Philip</p>

