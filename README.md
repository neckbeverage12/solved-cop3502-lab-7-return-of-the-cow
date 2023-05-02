Download Link: https://assignmentchef.com/product/solved-cop3502-lab-7-return-of-the-cow
<br>
<h2>Overview</h2>

This lab’s purpose is to provide students with experience in file I/O. It is recommended that students use command line tools and editors for this lab (though it is not strictly speaking required). This lab will require students to build on their previous lab experience, in which a version of the cowsay utility was created.




<h2>Specification</h2>

Students will update the driver program class (Cowsay) and also add one new class – FileCow. The FileCow class should extend the Cow class. As before, HeiferGenerator.java is provided for you – but updated to handle the new FileCow class. (Please refer to specification for previous lab for a refresher.) <u>Students may implement</u> <u>protected attributes and methods if they chose to do so.</u> This is not required – it is purely optional. No public attributes / methods should be added to the specification!




<h3>Cowsay Class (Program Driver)</h3>

Your program must accept <u>command line arguments</u> as follows:




java cowsay -l                                Lists the available cows

java cowsay MESSAGE   Prints out the MESSAGE using the default Cow java cowsay -n COW MESSAGE          Prints out the MESSAGE using the specified built-in Cow java cowsay -f COW MESSAGE          Prints out the MESSAGE using the specified file Cow




In addition, this version of the utility handles a special set of Cow-derived FileCow objects. The HeiferGenerator will automatically create FileCow objects (using the FileCow constructor) from files in the “cows” directory.

&gt;java Cowsay -l

Regular cows available: heifer kitteh dragon ice-dragon File cows available: moose turkey turtle tux










<h3>Previous Work</h3>

The following classes, developed previously, are required for this lab to function.




<u>Cow</u>

<table width="692">

 <tbody>

  <tr>

   <td width="312">public Cow(String name)</td>

   <td width="380">// Constructor</td>

  </tr>

  <tr>

   <td width="312">public String getName()</td>

   <td width="380">// Returns name of this cow object</td>

  </tr>

  <tr>

   <td width="312">public String getImage()</td>

   <td width="380">// Return image for this cow object</td>

  </tr>

  <tr>

   <td width="312">public void setImage(String image) <u>Dragon (extends Cow)</u></td>

   <td width="380">// Sets the image for this cow object to image</td>

  </tr>

 </tbody>

</table>

public Dragon(String name, String image)       // Constructor public boolean canBreatheFire()                 // Defaults to true




<h4>IceDragon (extends Dragon)</h4>

public IceDragon(String name, String image) // Constructor public boolean canBreatheFire()                 // Returns false







<h3>FileCow Class</h3>

The FileCow class must be derived from the Cow class. In addition, FileCow must add the following behavior:

public FileCow(String name, String filename)

Constructor; creates a new FileCow object with the given name and an image loaded from filename.




If the file cannot be loaded, it should throw a new RuntimeException with the message “MOOOOO!!!!!!” This should be the only public constructor for the FileCow class!




public void setImage()

Should immediately throw a new RuntimeException with the message “Cannot reset FileCow Image”.







<h2>Submissions</h2>

NOTE: Your output must match the example output *exactly*. If it does not, you will not receive full credit for your submission!




Files:  Cowsay.java, Cow.java, Dragon.java, IceDragon.java, FileCow.java, HeiferGenerator.java Method: Submit on Canvas













<h2>Sample Output</h2>




&gt;javac Cowsay.java &gt;java Cowsay Hello World!

Hello World!







^__^

(oo)_______

(__)       )/

||—-w |

||     ||




&gt;java Cowsay -n kitteh Moew-Moew!  Moew-Moew!







(“`-‘  ‘-/”) .___..–‘ ‘ “`-._

` *_ *  )    `-.   (      ) .`-.__. `)

(_Y_.) ‘ ._   )   `._` ;  “ -. .-‘

_.. `–‘_..-_/   /–‘ _ .’ ,4

( i l ),-”  ( l i),’  ( ( ! .-‘




&gt;java Cowsay -l

Regular cows available: heifer kitteh dragon ice-dragon

File cows available: moose turkey turtle tux




&gt;java Cowsay -n ninja Hello world!

Could not find ninja cow!




&gt;java Cowsay -f tux Do you have any herring?




Do you have any herring?         .–.

|o_o |

|:_/ |

//    

(|     | )

/’_   _/`

___)=(___/







&gt;java Cowsay -f alien Earth is ours!

Could not find alien cow!




&gt;java Cowsay -f kitteh MEOW!!!

Could not find kitteh cow!




&gt;java Cowsay -n tux How about tuna? Could not find tux cow!