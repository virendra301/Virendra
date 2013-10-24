Virendra
========
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html>

<head>

<style type="text/css">

.header2
  {
   height: 5px;
   background-color: #0099FF;
   margin:50px 0px 0px 0px;
   width:100%;
   top:0;
   left:0;
   white-space: nowrap;
  }

.image2
  {
   height: 50px;
   margin:0px 0px 0px 0px;
   width:100%;
   top:0;
   left:200;
   white-space: nowrap;
  }

.timer
  {
   margin-top: 20px;
   margin-left:1000px;
   width:100%;
   top:0;
   left:200px;
   white-space: nowrap;
   color: #0099FF;
  }

.footer2
  {
   height: 5px;
   background-color: #0099FF;
   margin:100px 0px 70px 0px;
   width:100%;
   top:0;
   left:0;
   white-space: nowrap;
  }
  
a:link, a:active, a:visited 
  { 
	text-decoration: none;
	color: white; 
  }

a:hover
  {
	text-decoration: none;
	color: #FF0000;
  }
  
.box
  {
    border:1px solid #0099FF;
	margin:20px 0px 0px 200px;
	height:4000px;
	width:950px;
  }

.code
  {
        border:1px dashed #0099FF;
	margin:10px 0px 0px 0px;
	padding:10px;
        background-color:#CCCCCC;
        color:#000000;
  }

.button
   { 
     width:104px; 
     height:35px; 
     background:#0099FF;
     border:1px solid #0099FF; 
     font-family:Arial, Helvetica, sans-serif; 
     font-weight:bold; 
     font-size:16px; 
     color:#FFF; 
     text-align:center; 
     display:inline-block; 
     float:left; 
     padding:0; 
     margin:40px 0px 0px 1050px;
     cursor:pointer;
    }

.option
  {
        margin:10px 0px 0px 0px;
  }
  
.keyword
  {
    color:blue;
  }

.string
  {
    color:red;
  }

.libfun
  {
    color:white;
  }
  
</style>

<script type="text/javascript">

var Timer,TotalSeconds,TotalMinutes,TotalHours,mytimer;
function getAnswer()
  {
    var radioButtons,x,i;
    for(i=1; i<=5; i++)
       {
         var name="Option"+i;
         radioButtons = document.getElementsByName(name); 
         for (x = 0; x < radioButtons.length; x ++) 
            { 
              if (radioButtons[x].checked) 
                { 
                  alert(radioButtons[x].value); 
                } 
             } 
        }
     window.clearTimeout(mytimer);
  } 

function CreateTimer(TimerID, Hour,Min,Sec) 
   {
     Timer = document.getElementById(TimerID);
     TotalSeconds = Sec;
     TotalMinutes = Min;
     TotalHours = Hour;

     UpdateTimer()
     mytimer=window.setTimeout("Tick()", 1000);
   }

function Tick() 
   {
     TotalSeconds -= 1;
     if(TotalSeconds < 0)
        {
          TotalMinutes -= 1;
          if (TotalMinutes == -1) 
            {
              disableall();
              alert("Time's up!")
              return;
            }
          if(TotalMinutes >= 0)
            {
              TotalSeconds = 59;
            }
        }
     UpdateTimer()
     mytimer=window.setTimeout("Tick()", 1000);
   }

function UpdateTimer() 
   {
     if(TotalSeconds < 10)
        {
          Timer.innerHTML = "Time Left: 0" + TotalHours + ":" + TotalMinutes + ":0" + TotalSeconds;
          if(TotalMinutes < 10 && TotalMinutes >= 0)
            {  
              Timer.innerHTML = "Time Left: 0" + TotalHours + ":0" + TotalMinutes + ":0" + TotalSeconds;
            }
        }
     else
        {
          Timer.innerHTML = "Time Left: 0" + TotalHours + ":" + TotalMinutes + ":" + TotalSeconds;
          if(TotalMinutes < 10)
            {  
              Timer.innerHTML = "Time Left: 0" + TotalHours + ":0" + TotalMinutes + ":" + TotalSeconds;
            }
        }     
   }

function disableall()
    {
      var i;
      for(i=1; i<=16; i++)
         {
          var name="Option"+i;
          document.getElementById(i).disabled=true; 
         }
      document.getElementById("submit").disabled=true; 
    }

</script>

<title>Online Test</title>

</head>

<body class="new" bgcolor="#FFFFFF">

<div id="image1" class="image2">

<img src="images/online_test_icon.GIF" align="middle" width="228" hspace="0" height="80" />

</div>

<p>
<font face="Arial" size="4" color="grey">
<div id="header1" class="header2">
</div>

<div id="timer" class="timer">
<script type="text/javascript">
window.onload = CreateTimer("timer", 00,29,59);
</script>
</div>


<div id="content" class="box">
<table>

<tr>
<td></br>1.&nbsp;</td>
<td></br>What will the SWAP macro in the following program be expanded to on preprocessing? Will the code compile?</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<pre class="code"><code>#include&lt;stdio.h&gt;
#define SWAP(a, b, c)(c t; t=a, a=b, b=t)
<span class="keyword">int</span> main()
{
    <span class="keyword">int</span> x=10, y=20;
    SWAP(x, y, <span class="keyword">int</span>);
    <span class="libfun">printf</span>(<span class="string">"%d %d\n"</span>, x, y);
    <span class="keyword">return</span> 0;
}
</code></pre></td>
</tr>
<tr>
<td><div class="option"></div>&nbsp;</td>
<td><div class="option"></div>
<table width=100%;>
<tbody>
<tr>
<td width=1%;><input type="radio" name="Option1" value="A"    id="1"></td>
<td width=1%;>A.</td>
<td width=48%;>It compiles</td>
<td width=1%;><input type="radio" name="Option1" value="B" id="2"></td>
<td width=1%;>B.</td>
<td width=48%;>Compiles with an warning</td>
</tr>
<tr>
<td><input type="radio" name="Option1" value="C" id="3"></td>
<td>C.</td>
<td>Will not compile</td>
<td><input type="radio" name="Option1" value="D" id="4"></td>
<td>D.</td>
<td>Compiles but will not print anything</td>
</tr>
</tbody>
</table>
</td>
</tr>
<tr>
<td></br>2.&nbsp;</td>
<td></br>What will the output of following program?</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<pre class="code"><code>#include&lt;stdio.h&gt;
#include&lt;string.h&gt;

<span class="keyword">int</span> main()
{
    <span class="keyword">char</span> str[] = "Online\0Test\0";
    <span class="libfun">printf</span>(<span class="string">"%s\n"</span>, str);
    <span class="keyword">return</span> 0;
}
</code></pre></td>
</tr>
<tr>
<td><div class="option"></div>&nbsp;</td>
<td><div class="option"></div>
<table width=100%;>
<tr>
<td width=1%;><input type="radio" name="Option2" value="A" id="5"></td>
<td width=1%;>A.</td>
<td width=48%;>Test</td>
<td width=1%;><input type="radio" name="Option2" value="B" id="6"></td>
<td width=1%;>B.</td>
<td width=48%;>Online</td>
</tr>
<tr>
<td><input type="radio" name="Option2" value="C" id="7"></td>
<td>C.</td>
<td>Online Test</td>
<td><input type="radio" name="Option2" value="D" id="8"></td>
<td>D.</td>
<td>Online\0Test</td>
</tr>
</table>
</td>
</tr>
<tr>
<td></br>3.&nbsp;</td>
<td></br>Usually recursion works slower than loops.</td>
</tr>
<tr>
<td><div class="option"></div>&nbsp;</td>
<td><div class="option"></div>
<table width=100%;>
<tr>
<td width=1%;><input type="radio" name="Option3" value="A" id="9"></td>
<td width=1%;>A.</td>
<td width=48%;>True</td>
<td width=1%;><input type="radio" name="Option3" value="B" id="10"></td>
<td width=1%;>B.</td>
<td width=48%;>False</td>
</tr>
</table>
</td>
</tr>
<tr>
<td></br>4.&nbsp;</td>
<td></br>When we allocate memory dynamically, is there any way to free the allocated memory runtime?</td>
</tr>
<tr>
<td><div class="option"></div>&nbsp;</td>
<td><div class="option"></div>
<table width=100%;>
<tr>
<td width=1%;><input type="radio" name="Option4" value="A" id="11"></td>
<td width=1%;>A.</td>
<td width=48%;>Yes</td>
<td width=1%;><input type="radio" name="Option4" value="B" id="12"></td>
<td width=1%;>B.</td>
<td width=48%;>No</td>
</tr>
</table>
</td>
</tr>
<tr>
<td></br>5.&nbsp;</td>
<td></br>What will the output of following program?</td>
</tr>
<tr>
<td>&nbsp;</td>
<td>
<pre class="code"><code>#include&lt;stdio.h&gt;
<span class="keyword">int</span> main()
{
    <span class="keyword">float</span> a=0.7;
    <span class="keyword">if</span>(a < 0.7)
        <span class="libfun">printf</span>(<span class="string">"C\n"</span>);
    <span class="keyword">else</span>
        <span class="libfun">printf</span>(<span class="string">"C++\n"</span>);
    <span class="keyword">return</span> 0;
}
</code></pre></td>
</tr>
<tr>
<td><div class="option"></div>&nbsp;</td>
<td><div class="option"></div>
<table width=100%;>
<tr>
<td width=1%;><input type="radio" name="Option5" value="A" id="13"></td>
<td width=1%;>A.</td>
<td width=48%;>C++</td>
<td width=1%;><input type="radio" name="Option5" value="B" id="14"></td>
<td width=1%;>B.</td>
<td width=48%;>C</td>
</tr>
<tr>
<td><input type="radio" name="Option5" value="C" id="15"></td>
<td>C.</td>
<td>Compiler Error</td>
<td><input type="radio" name="Option5" value="D" id="16"></td>
<td>D.</td>
<td>None of these</td>
</tr>
</table>
</td>
</tr>

</table>
</div>

<input id="submit" class="button" name="submit" type="submit" value="Submit" onclick="getAnswer()" />

<div id="footer1" class="footer2">
</div>
</font>
</p>

</body>

</html>
