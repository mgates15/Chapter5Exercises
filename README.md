Chapter5Exercises
=================
"6." What happens if the name of the main method in MovingDisk class is mistyped with a capital M?

Because Eclipse is an IDE that tries to help sort out errors in code, the error that is thrown in the console when trying to run the program is the following:

Error: Main method not found in class HelloGraphics, please define the main method as:
   public static void main(String[] args)
   
   
I also ran the same program in terminal and received the same error. This seems peculiar considering the answer in the PDF sheet is:

The Java interpreter "throws an exception":
Exception in thread "main" java.lang.NoSuchMethodError: main

This might be because there has been an update in java and it better spots the errors.

"7." I ran the following statement in CodingBat instead of actually using eclipse, because CodingBat was easier because I didn't have to make a class. 

The error thrown was the following:

Syntax error on token "if", ( expected after this token

The braces however were not needed, and a matter of style in this particular case. This does not, however, mean that it works for all cases (ie. if there was more than one statement within the braces). 

"8." When the semicolon is printed just outside the if statement, the applet doesn't run correctly. Instead of being displayed moving across the screen, "Hello, World!" is displayed just outside the range of the screen to the right. It compiles because there is no "else if" or "else" statement following it. Instead of reevaluating the if statement every time, it keeps it constant with the semicolon. 
