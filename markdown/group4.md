---
title: Group Activity 4 | Discrete Math, Games, and Family
...

Put your answers for each problem of this activity in this [worksheet](/files/group4.pdf).

# Directions

This activity is designed to be done in a group, whether that's in class, at home with family, or with suite-mates, friends, or people you meet on the bus or in an airport. 

- **If you're working on this in class**, please first form a group of approximately 3 people (+/- 1 person). Once you've done that, grab some cookies! The cookies are nut- and chocolate-free. Unfortunately we have no gluten-free, dairy-free, egg-free, or vegan options today. If you have dietary restrictions that prevent you from being able to enjoy today's treat, just let Nathan Brunelle know and he can make it up to you on a future date.

- **If you're working on this elsewhere**, find at least 1 other person (but ideally 2) to participate in this activity with you. Your partner(s) definitely don't need to have any math/cs background, but be prepared to teach some discrete math to someone! We tried to pick topics that would be fun to discuss, hopefully this is an overall positive experience. When completing your activity you may print our the worksheet above, or roughly reproduce it on your own paper. To submit, upload an image of your answers to the quiz site under Group4.

Below you will see that there are 4 different activities available. You're welcome to work through these in any order you please, and are not expected to finish all of them. Regardless of where/when you're working, please spend at least 50 minutes on the activity. Indicate your start time (**problem 1**) and end time (**problem 2**) on your sheet.


# Introduce Your Team/Family!

Give the names of all members of your group. Indicate the your relation to each group member and how much Math/CS experience/education they have. (**problem 1**).

# Select an Activity

## Activity A: Propositions to Computing

*Goals of this activity*:  
- See how math makes computers "go". Build a simple computer circuit using propositions and boolean operators. We'll walk you through how computers use boolean algebra to add numbers together.

*What your group members will need to know/What you may need to teach*:  
- Propositions, elementary school arithmetic, Boolean operators.

### Electricity to Binary

Before we get started, we first need to see how computers represent information. Computers run on electricity. How is it that we can actually do computation using electricity? The first piece of an answer to this question is something called a transistor. Transistors are super tiny devices that sometimes conduct electricity, and sometimes don't, allowing them to act like microscopic electrical switches

You can think of transistors as having two wires connected to them, called the source and the gate. If there is electricty flowing through the gate wire, the transistor will act as a conductor, and allow electricy from the source to pass through. If the gate does not have any electricty flow, then the transistor will resist electrical current from the source, causing it to block that electrical flow. (If you're curious about the physics for how this is acheived, I recommend [this video](https://www.youtube.com/watch?v=IcrBqCFLHIY) from the Youtube channel Veritasium)

If we consider a wire having electrical flow across it to carry the value 1 and a wire not having electrical flow across it to carry the value 0, a transistor behaves somewhat like a logical AND operator, since electricity will only flow out of a transistor if both the source and the gate have electricity flowing in. Using just simple devices like this (there are other arrangements we can have for transistors that perform other operations, like negation), we are able to do fantastically complex calculations by simply linking billions of them together in clever ways. 

Throughout this activity, we'll walk through how we can use electricity to add two numbers together by using 1s and 0s (electrical charge or no electrical charge, respectively) to represent numbers

### Binary Representations

To work through this, we first need to see how to represent numbers using just 1s and 0s. By way of example, let's look at what we mean when we write the number 2120. 

The first thing to recognize here is that while we are likely super comfortable with 2120 just meaning "two-thousand one-hundred and twenty", there is nothing that's forcing us to write 2120 in that way. The Roman empire got along just fine writing that number as MMCXX, and the Incan empire got along just fine representing numbers like that using a [chain of knots](https://www.youtube.com/watch?v=OFbbiAf8kUo). The reason most of the world has now settled on representations of numbers like 2120 is that it is easier to do arithmetic with this sort of representation. Let's look at why.

When we write 2120, we are actually describing a number via procedure. In this procedure we know the value is going to be determined by the sum of the following:

- The digit in the 1's place (the rightmost digit) multiplied by $10^0 = 1$ (0 in this example)
- The digit in the 10's place (the next digit from the right) multiplied by $10^1 = 10$ (20 in this example)
- The digit in the 100's place (the next digit from the right) multiplied by $10^2 = 100$ (100 in this example)
- The digit in the 1000's place (the next digit from the right) multiplied by $10^3 = 1000$ (2000 in this example).

In other words, 2120 is the result of the sum 0+20+100+2000. The advantage this gives us is that we can represent whatever number we'd like, whether or not we know the name of it, just by using the small set of symbols 0-9 listed in some order. (Compare this to Roman numerals, for example, where to come up with a new super-large number they'd need to invent a new word/symbol for it).

Computers represent numbers in the same way that we humans do, except that instead of using the values 0-9 in various positions to identify numbers, computers just use the values 0 and 1 to do so (represented by no electricity vs electricity, respectively). We call the method of representing using the values 0-9 decimal representation, and the method using only 0 and 1 binary representation.

To illustrate how this works, Consider the binary value 1011. This number represents sum of:

- The digit in the 1's place (the rightmost digit) multiplied by $2^0 = 1$ (1 in this example)
- The digit in the 2's place (the next digit from the right) multiplied by $2^1 = 2$ (2 in this example)
- The digit in the 4's place (the next digit from the right) multiplied by $2^2 = 4$ (0 in this example)
- The digit in the 8's place (the next digit from the right) multiplied by $2^3 = 8$ (1 in this example)

Therefore 1011 represents that number $1+2+0+8=11$. Notice that the procedure for finding the value of a binary number is exactly the same as the procedure for finding the value of a decimal number, except that everywhere we saw a 10 before, we see a 2 now. 

Check that you understand binary representations by giving the value represented by 110101 (**Problem A1**) and by giving the binary represntation of 63 (**Problem A2**).



## Activity B: "Do you have a crush on me?"

*Goals of this activity*:
- To see some ideas realted to cryptography. Namely, we'll be exploring an illustration of a cryptography topics called secure computation. Check whether that crush who you're seeing for the first time since before the pandemic still has feelings for you, too.

*What your group members will need to know/What you may need to teach*:  
- Propositions, Boolean algebra, functions.

## Activity C: The Secret of NIM

*Goals of this activity*:
- Help you finally get one up on your older sibling/smarty-pants family member by playing a game against them that they cannot win. Then give you the opportunity to make yourself look even smarter by explaining to them precisely how you're winning every time.

*What your group members will need to know/What you may need to teach*:  
- Counting (from 1 to 5), Induction/recursion (or related ideas), how to lose a game gracefully.

## Activity D: Centrifuges

*Goals of this activity*:
- Revisit a problem that we looked at during the first week of class so that we can see how far exactly we've come in honing our skills for careful thought and problem solving. Demonstrate how formal reasoning can help you to be convinced of counter-intuitive facts. Give yourself an excuse to load up the lazy-susan with turkey, mashed potatoes, and on the fixin's, then give it a whirl *as fast as you can*!

*What your group members will need to know/What you may need to teach*: How to read an analog clock, what a centrifuge is, what a test-tube is, problem-solving skills.
