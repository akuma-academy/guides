### Conditional logic is all about the IF word. 
It's practically impossible to program effectively without using IF. Sure, you can write simple programs like the kinds you would see on a calculator without ever using the word. But for anything more complicated, you need to get the hang of **conditional logic**.

#### Conditional logic example

As an example, take the calculator program you have just written. It only has a Plus button. We'll be adding another button soon, a Subtract button. Now, you can't say beforehand which of the two buttons your users will click. Do they want to add, or subtract? You need to be able to write code that does the following:

> **IF** the Plus button was clicked, add up

> **IF** the Minus button was clicked, subtract

You can rearrange the two statements above.

> Was the Plus button clicked? Yes, or No?

> Was the Minus button clicked? Yes, or No?

So the answer for each is either going to be Yes, or No - the button is either clicked, or not clicked. We consider such yes/no, true/false, or 0/1 relationships to be Boolean relationships (consisting of Boolean values). More on this soon.


## IF Statements


To test for YES or NO values, you can use an IF statement. You set them up like this:
```
if ( )
{

}
```
In the parentheses, type what you want to check for. In this case we would check: *Was the button clicked?*  After the parentheses, it's convenient (but not strictly necessary) to add a pair of curly brackets. In between your curly brackets, you type your code, which dictates what you want to happen IF the answer to your question was YES. Here's a coding example:

```
bool buttonClicked = true;

if (buttonClicked = = true)
{

MessageBox.Show(“The button was clicked”);

}
```

Notice the first line of code:

```
bool buttonClicked = true;
```

This is a variable type you haven't met before - bool, which is short for Boolean. You use a Boolean variable type when you want to check for true or false values (YES, or NO, if you prefer). This type of variable can only ever be true or false. The name of the bool variable above is buttonClicked. We've set the value to true.

The next few lines are the IF Statement:

```
if (buttonClicked == true)
{

MessageBox.Show(“The button was clicked”);

}
```

The double equals sign (` == `) is a common convention in IF statements in most languages. It means "Has a value of."  The double equals sign is known as a **conditional operator**. More on these shortly. But the whole of the line reads:

 > "IF buttonClicked has a value of true"

This is the condition that we are checking!

#### == vs. =

Note that if you miss out one of the equals signs, you'd have this:

```
if (buttonClicked = true)
```

This statement **is not** checking if buttonClicked "Has a value of" true. What you're doing here is assigning a value of true to the variable buttonClicked. However assignment is rarely (if ever) allowed in conditional statements. The difference between `=` and `==` is key to handling logical operations. You will undoubtedly see lots of problems whenever you get this syntax wrong!

In between the curly brackets of the IF statement, we have a simple MessageBox line. But this line will only get executed IF buttonClicked has a value of true.

#### Testing the example

Let's try it out. Start a new project for this (File > New Project). Add a button to your new form, and set the Text property to "IF Statement". Double click the button, and add the code from above. So your coding window will now look like this:

![alt text](http://i.imgur.com/5nXedhe.png)

Run your program and click the button. You should see a message box with the words: "The button was clicked".

Now halt the program and change this line:

```
bool buttonClicked = true;
```

to this

```
bool buttonClicked = false;
```

Our boolean is now false. Run your program again, and click the button. What happens? Nothing!

This is because our IF Statement is checking if `buttonClicked` has a value of true:

```
if (buttonClicked == true)
```

C# executes the code between the curly brackets IF buttonClicked has a value of true. Since `buttonClicked` is now false, the interpreter doesn't bother with the lines within the curly braces, since the conditional statement does not end up being true. Instead of handling the MessageBox code, the program skips the stuff in the braces and moves to the rest of the code. Since the code ends after the first if-statement, we don't output anything.

## Else

You can also say what should happen if the answer was false. All you need to do is make use of the `else` word. You do it like this:

```
if (buttonClicked == true)
{

}
else
{

}
```

So you just type the word else after the curly brackets of the IF Statement. Then, just like with IF, add another pair of curly braces. In these, write the commands that should be run if the conditional statement `if (buttonClicked == true)` is false. Change your code to this:

```
if (buttonClicked == true)
{

MessageBox.Show("buttonClicked has a value of true");

}
else
{

MessageBox.Show("buttonClicked has a value of false");

}
```

So the whole thing reads:

> "`if` it's true that buttonClicked has a value of true, do one thing. Otherwise (`else`), do something else."

Run your program, and click the button. You should see the second MessageBox display. Halt the program, and change the first line back to true. 

So `bool buttonClicked = true;` becomes `bool buttonClicked = false;`

Run the program again, and click the button. This time, the second message box will display. Do you understand why this happens?

The whole point of using If...Else Statements, though, is to execute one piece of code instead of some other piece of code. Let's go back to the initial example of the calculator. Suppose our calculator only has two buttons: `+` and `-`. Then if the user presses the `+` button, we know that the `-` button was NOT pressed. Therefore, for some variable `plusButtonClicked`, we can check the condition `plusButtonClicked == true` and perform the addition `if` that condition is met. `else` we can perform subtraction. This simple block of code would drive our calculator. Pretty neat.

As an exercise, I leave you to work on addition, subtraction, and multiplication functions in C# and choosing between which functions to use. (Hint: `else if` may come in handy.) 
____

Hopefully you found this tutorial helpful as you tackle more difficult problems in C#. 

Also feel free to leave comments and feedback at the bottom of the page!

