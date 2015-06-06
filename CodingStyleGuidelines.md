# Introduction #

If any other developers join me in coding this project, this is my system for writing code at least somewhat readably. I'd hope any other developers would adhere to these guidelines, and if they disagree with any of them they may comment on it.

# Code Editors and IDEs #

I use the following programs in my development process.

  * Microsoft Windows - any version from XP onwards (I'm still using XP Professional)
  1. JDK v1.6 - the Java Development Kit for compiling Java code.
  1. JGrasp - a splended, free IDE specialized for Java.
  1. Windows Notepad - simple text editor for quick adjustment or reading of code. Uses no control codes or text formatting.

  * Android - in case you feel like coding on the go. Any version from 1.6 onwards should be fine (it's what I'm stuck on for now)
  1. Touchqode - free app available in the Android Market. Essentially a text editor with syntax highlighting. I'm using it to write this wiki page!
I don't know of any app which will compile code to run on your phone/tablet on the fly.

## Coding Style & Guidelines ##
These are not rules set in stone, but it's the way I've been writing my code so far.

Example class:
```
// First is the file header
// Basically a few comments stating the class name and a brief description of what it does.

#import java.Needed.Library.*;
#import java.Try.To.Use.The.Specific.Library.You.Need;
#import java.Avoid.Using.Asterisk.Wildcards;

public class ClassnameStartingCapitalizedLikeEveryOtherClassInJava {
	// indent inside classes
	// Indent using tabs, not spaces
	
	// INITIAL DATA DECLARATION AND DEFINITION OF CONSTANTS
	
	public static final boolean CONSTANTS_ARE_PUBLIC = true;
	public static final int CONSTANTS_ARE_ALL_CAPS_AND_USE_UNDERSCORES = 1337;
	
	private int dontCapitalizeFirstWord;
	private Scanner keyboard; // don't initialize here unless you have to
	private String makeAllGlobalVariablesPrivate;
	
	// CONSTRUCTORS
	
	// What does this constructor do?
	public ClassnameStartingCapitalizedLikeEveryOtherClassInJava() {
		// default constructor here
	}
	
	// Read the data from an array of doubles
	public ClassnameStartingCapitalizedLikeEveryOtherClassInJava(float[] omgParams) {
		for(int i=0; i<omgParams.length; i++) { // Use postfix incrementors on iterators
			for(int j=0; j<4; j++) { // Always count up
				omgParams[i] += j; // Use i, j, k, l, etc. for iterators
			}
		}
	}
	
	// METHODS
	
	// +myFunction(boolean)
	// Somewhat detailed description of function and what it does. Make
	// your lines a sane length. Use + for public functions and - for
	// private ones. Like pseudocode!
	public void myFunction(boolean myFunctionParam) { // Opening brace on same line as method
		if (myFunctionParam) {                         // and on same line as if statements
			;                                           // if it does nothing, put a single semicolon
		} else {                                       // Else statements on same line as closing
			do.someStuff();                             // brace of its parent "if". Also if comment
			                                            // lines are getting too long, do this. Use
			                                            // three spaces for every tab, since that's
			                                            // how much space JGrasp and Touchqode give
			                                            // to a tab.
		}
	}
	
	// -anotherFunction(int, int, int, int, int, int, double)
	// returns: double
	// Be sure to say what the function does with the parameters and
	// what it returns. If it's very important to know how inefficient
	// or slow the process is, say an analysis in Big-O notation to
	// clarify and maybe explain why.
	private double anotherFunction(int try, int to, int avoid, int using, int too, int many, double parameters) {
		double tryToAvoidUsingSinglePrecisionFloats=9.352; // You can comment after a line.
		
		// Use comments like this.
		/* Don't comment like this
		   unless it's a big block
		   of broken code or something,
		   in which case explain. */
		// No, use comments
		// like
		// this
		// for normal things.
		
		SomethingElse someOtherObject = new SomethingElse("Omg constructor");
		int withNumbers=92;
		char andALetter='p';
		double result = someOtherObject.doSomethingWiggy(withNumbers, andALetter); // give a brief description what this is doing
		if (youUse==inconsistentSpacing) {
			tryToMakeItClear();
		}
		
		return result;
	}
	
	// ACCESSORS AND MUTATORS
	// These let the outside world grab or change instance data without making it public
	public void setSomething(int in) { // Mutators always start with "set"
		if(in>=0) { // Mutators allow for error checking of input data
			something=in;
		} // You could use an else here to throw an exception or return a false boolean
	}
	
	public int getSomething() { // Accessors always start with "get"
		return something;
	}
	
	public double getSpecificSomething(int index) {
		return somethingsArray[index];
	}
}
```

# See Also #
http://en.wikipedia.org/wiki/Big_O_Notation