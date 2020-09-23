<div align="center">

## Converting Notes to Frequencies


</div>

### Description

here i describe how can convert notes used in music (like c, d, e, f, g, a, b, c sharp, g flat,...) into frequencies you can use e.g. for the pc-speeker or whatever you like. if you think it's usefull, please vote!
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Lawilog](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/lawilog.md)
**Level**          |Beginner
**User Rating**    |4.9 (44 globes from 9 users)
**Compatibility**  |C, C\+\+ \(general\), Microsoft Visual C\+\+, Borland C\+\+, UNIX C\+\+
**Category**       |[Graphics/ Sound](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/graphics-sound__3-15.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/lawilog-converting-notes-to-frequencies__3-8118/archive/master.zip)





### Source Code

<h1>Converting Notes to Frequencies</h1>
<p>OK. To calculate any frequency, you need to know three things:<ul>
<li>First: The fact, that a tone (note ?, i'm from germany...), that sounds one octave higher has a dobbeld frequency.<br>So, if e.g. <b>C</b> has a frequency of <tt>264 Hz</tt>, <b>C</b> one octave higher has <nobr><tt>264 Hz * 2 = 528 Hz</tt></nobr>...still one octave higher it is <nobr><tt>528 Hz * 2 = 1056 Hz</tt></nobr> - and so on.
<li>Second, you need a start frequency of one special tone to create a function that calculates all the others.<br>
e.g. <nobr>("concert pitch") <tt><b>A</b> = 440 Hz</tt></nobr>
<li>And last but not least: in music it is said, that one octave has <b>12 halftones</b>. (7 white and 5 black keys ;-)... )
</ul></p>
<p>Now, it is up to you, which halftone you suppose your concert pitch to be. On an normal (non-professional) piano keyboard concert pitch <b>A</b> would be the <b>58th</b> one. which means, that there are still 4 lower octaves. (A is the 10th out of the 12, and <nobr><tt>10 + 4*12 = 58</tt></nobr>)</p>
<p>...all these mathamitical and musical theorie, sorry...<br>
Growing exponentially, the function has the following form: <tt>f(n) = k * a^n</tt>.<br>
You know, the <b>58th</b> halftone has a freq of <b>440</b>.
One octave higher, the <b>70th</b> halftone (<tt>58+12=70</tt>) has a dobbeled freq of 880.<br>
good. that means:<br>
<tt>440 = k * a^58</tt> and<br>
<tt>880 = k * a^70</tt><br>
Now you transform both equqtions to "<tt>k = ...</tt>", set them equal, and calculate <b>a</b> with <b>2^(1/12)</b>. Now you use the caclulated <b>a</b> in one equation to get <b>k</b> with <tt>440 * 2^(-58/12)</tt>.<br>
Now, you have your equation <nobr><tt>f = 440 * 2^(-58/12) * (2^(1/12))^n</tt></nobr> which is equal to:<br>
<nobr><tt><h4>f = 440 * 2^((n - 58)/12)</h4></tt></nobr>
And that's it !</p>
<p>I will give you some examples:<br>
<table border="1">
<tr><th>note / tone</th> <th>n</th> <th>frequency in Hz</th></tr>
<tr><td>...</td><td>...</td><td>...</td></tr>
<tr><td>B (one octace below)</td><td>48</td><td>246.9</td></tr>
<tr><td>C</td><td>49</td><td>261.6</td></tr>
<tr><td>C sharp (D flat)</td><td>50</td><td>277.2</td></tr>
<tr><td>D</td><td>51</td><td>293.7</td></tr>
<tr><td>D sharp (E flat)</td><td>52</td><td>311.1</td></tr>
<tr><td>E</td><td>53</td><td>329.6</td></tr>
<tr><td>F</td><td>54</td><td>349.2</td></tr>
<tr><td>F sharp (G flat)</td><td>55</td><td>370.0</td></tr>
<tr><td>G</td><td>56</td><td>392.0</td></tr>
<tr><td>G sharp (A flat)</td><td>57</td><td>415.3</td></tr>
<tr><td>A</td><td>58</td><td>440</td></tr>
<tr><td>A sharp (B flat)</td><td>59</td><td>466.2</td></tr>
<tr><td>B</td><td>60</td><td>493.9</td></tr>
<tr><td>C (next octave)</td><td>61</td><td>523.3</td></tr>
<tr><td>...</td><td>...</td><td>...</td></tr>
</table></p>
<p>So far, so good.<br>
Now, it is up to you, to create a code, that can play meldoies. Maybe you would like to have a function first, that converts the note-string ("c", "g", "d flat", "g sharp",...) to a frequency. Than you may need a good way of storing the melodie-data (with note length and so on); a playing engine; even a midi-driver is possible... :D<br>
But this is not what I am going to do for you. :D</p>

