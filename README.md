Chapter5Exercises
=================
"6." What happens if the name of the main method in MovingDisk class is mistyped with a capital M?

Because Eclipse is an IDE that tries to help sort out errors in code, the error that is thrown in the console when trying to run the program is the following:

Error: Main method not found in class HelloGraphics, please define the main method as:
   public static void main(String[] args)
   
   
I also ran the same program in Terminal and received the same error. This seems peculiar considering the answer in the PDF sheet is:

The Java interpreter "throws an exception":
Exception in thread "main" java.lang.NoSuchMethodError: main

This might be because there has been an update in java and it better spots the errors.

Either way, the reason an error is thrown, however, is because java is case sensitive. 

"7." I ran the following statement in CodingBat instead of actually using eclipse, because CodingBat was easier because I didn't have to make a class. 

The error thrown was the following:

Syntax error on token "if", ( expected after this token

The braces however were not needed, and a matter of style in this particular case. This does not, however, mean that it works for all cases (ie. if there was more than one statement within the braces). 

"8." When the semicolon is printed just outside the if statement, the applet doesn't run correctly. Instead of being displayed moving across the screen, "Hello, World!" is displayed just outside the range of the screen to the right. It compiles because there is no "else if" or "else" statement following it. Instead of reevaluating the if statement every time, it keeps it constant with the semicolon. 

"9."
public boolean badIndentation (int maxLines) {
   
   int linCount = 3;
   while (lineCount < maxLines) {
   
     System.out.println(lineCount);
     lineCount++;
   }
   
   return true;
}

"11." 
(a) The title bar of the applet is no longer "GUI Demo," it is simply left blank. 

(b) The program does compile but the window is completely empty with no title, color, or text. public HelloGui is no longer treated as a constructor, but actually a method when void is added to it. 

"12." 
(a) roost.wav is missing a quotation mark afterwards. Also, "seBackground" is missing a t, which is crucial. Also, the following code is missing parentheses after Morning:

Morning morning = new Morning;

It should look like:

Morning morning = new Morning();

(b) The code is the following:

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class Morning extends JFrame
implements ActionListener
{
	private EasySound rooster;
	private int time;
  

  public Morning()
   {
    super("Morning");
    rooster = new EasySound("roost.wav");
    
    Container c = getContentPane();
    c.setBackground(Color.WHITE);
 
    time = 0;
    Timer clock = new Timer(5000, this); 
    clock.start();
}

  public void playSound()
  {
	  int m = 120*((time % 2) +1);
	  if (m <= 120)
	  {
		  rooster.play();
	  }
  }
  public void actionPerformed (ActionEvent m)
  {
	  time++;
	  if (time % 2 == 0) rooster.play();
	  repaint(0);
  }
  /**
   *   Constructor
   */

  public static void main(String[] args)
  {
    Morning morning = new Morning();
    morning.setSize(300, 150);
    morning.setDefaultCloseOperation(EXIT_ON_CLOSE);
    morning.setVisible(true);
  }
}  

(c) The code is the following:

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class Morning extends JFrame
implements ActionListener
{
	private EasySound rooster;
	private EasySound moo;
	private int time;
  

  public Morning()
   {
    super("Morning");
    rooster = new EasySound("roost.wav");
    rooster = new EasySound("moo.wav");
    
    
    if (time % 3 == 0) {
      rooster.play();
      Container c = getContentPane();
      c.setBackground(Color.WHITE);
   }
   
   else {
      moo.play();
      Container c = getContentPane();
      c.setBackground(Color.BLACK);
 
    time = 0;
    Timer clock = new Timer(5000, this); 
    clock.start();
   }
   repaint();
}

  public static void main(String[] args)
  {
    Morning morning = new Morning();
    morning.setSize(300, 150);
    morning.setDefaultCloseOperation(EXIT_ON_CLOSE);
    morning.setVisible(true);
  }
}  
