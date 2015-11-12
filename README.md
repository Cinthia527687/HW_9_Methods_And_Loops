# HW_9_Methods_And_Loops 

## Introduction

We are going back to our friend the addition game.
We are now going to rework the addition game using methods and for loops.

## Outline

```
// Import a scanner for user input later on
// Call the addition game method
	AdditionGameMethod();
// Set up the initial difficulty, difficulty levels, and score tracker
// Set the number of rounds
// Get user input with the scanner
// Create a boolean statement to check the user input for the correct answer
// Give user points and harder question for correct answers
// Tell user the correct answer, no points, and give them an easier question if they answer incorrectly
```

## References

Liang, Y. (2014). Introduction to Java programming: Comprehensive version (Tenth ed.)

## Java Code

```
import java.util.Scanner;

public class HW_9_Code {
	public static void main(String[] args) {
		//System.out.println("Hello class.");
		
		//Call the addition game method.
		AdditonGameMethod();
	}
	public static void AdditonGameMethod() {
		//System.out.println("Inside the addition game method.");
		
		int hardness = 5;
		int hardnessStep = 2;
		int score = 0;
		
		// Set up my for loop to go through the number of rounds
		int numberOfRounds = 3;
		for(int roundNumber = 1; 
		roundNumber <= numberOfRounds;  
		roundNumber = roundNumber + 1){
			//System.out.println("Inside the for loop. Round: " + roundNumber);
			System.out.print("Round " + roundNumber + " of " + numberOfRounds + ". ");
			boolean isAnswerCorrect = getAndCheckStudentAnswer(hardness);
			if(isAnswerCorrect){
				System.out.print("Your score was " + score + " and is now ");
				score = score + hardness;
				System.out.print(score + ". ");
				
				if(roundNumber<numberOfRounds){
					System.out.print("Your hardness was " + hardness + " and is now ");
					hardness = hardness * hardnessStep;
					System.out.println(hardness + ".");
				}
			}else{
				System.out.print("Your score is " + score + ". ");
				if(roundNumber<numberOfRounds){
					System.out.print("Your hardness was " + hardness + " and is now ");
					if(hardness>5){
						hardness = hardness / hardnessStep;
					}
					System.out.println(hardness + ".");
					
				}
				
			}
		}
		System.out.print("\nThe game is complete. ");
		System.out.println("Your final score was " + score );
	}
	
	public static boolean getAndCheckStudentAnswer(int hardness) {
		//System.out.println("Inside get and check student answer method.");
		int number1 = (int)(Math.random()*hardness);
		int number2 = (int)(Math.random()*hardness);
		System.out.print("Add " + number1 + " and " + number2 +": ");
		//Scanner input = new Scanner(System.in);
		//int studentAnswer = input.nextInt();
		Scanner get = new Scanner(System.in);
		int studentAnswer = get.nextInt();
		if(studentAnswer == (number1 + number2)){
			System.out.print("Correct. ");
			return true;
		}else{
			System.out.println("Nice try, but the correct answer was " 
					+ (number1 + number2) + ".");
			return false;
		}
	}
}
```

## Console Output


```
What number is 3 + 8?
11

Your answer was correct.
Your score is now: 10
End of first round.

What number is 8+ 91?
100

Your answer was incorrect.
The correct answer was: 99
Your difficulty is now: 10
End of second round.

What number is 9 + 1?
10

Your answer was correct.
Your score is now: 20
End of third round.

What number is 90 +44?
134

Your answer was correct.
Your score is now: 120
End of fourth round.
Your final score is: 120

```

## Command Prompt Output

I had more commands on my command line.
I took a break from working on this assigment, and when I cam back I could no longer see my previous commits on the command line.
I tried scrolling back up and had no luck.

###### Added Introduction and Summary.

```
F:\Computer Science I\Section 1412 Workspace\HW_9_Methods_And_Loops>git push
warning: push.default is unset; its implicit value has changed in
Git 2.0 from 'matching' to 'simple'. To squelch this message
and maintain the traditional behavior, use:

  git config --global push.default matching

To squelch this message and adopt the new behavior now, use:

  git config --global push.default simple

When push.default is set to 'matching', git will push local branches
to the remote branches that already exist with the same name.

Since Git 2.0, Git defaults to the more conservative 'simple'
behavior, which only pushes the current branch to the corresponding
remote branch that 'git pull' uses to update the current branch.

See 'git help config' and search for 'push.default' for further information.
(the 'simple' mode was introduced in Git 1.7.11. Use the similar mode
'current' instead of 'simple' if you sometimes use older versions of Git)

Username for 'https://github.com': Cinthia527687
Password for 'https://Cinthia527687@github.com':
Counting objects: 3, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 574 bytes | 0 bytes/s, done.
Total 3 (delta 2), reused 0 (delta 0)
To https://github.com/Cinthia527687/HW_9_Methods_And_Loops.git
   7846384..2ed3dfe  master -> master
```

###### Cleaned up my markdown outline.


```
F:\Computer Science I\Section 1412 Workspace\HW_9_Methods_And_Loops>git add .

F:\Computer Science I\Section 1412 Workspace\HW_9_Methods_And_Loops>git commit -
m "updated the outline"
[master 085bcdc] updated the outline
 1 file changed, 2 insertions(+)

F:\Computer Science I\Section 1412 Workspace\HW_9_Methods_And_Loops>git push
warning: push.default is unset; its implicit value has changed in
Git 2.0 from 'matching' to 'simple'. To squelch this message
and maintain the traditional behavior, use:

  git config --global push.default matching

To squelch this message and adopt the new behavior now, use:

  git config --global push.default simple

When push.default is set to 'matching', git will push local branches
to the remote branches that already exist with the same name.

Since Git 2.0, Git defaults to the more conservative 'simple'
behavior, which only pushes the current branch to the corresponding
remote branch that 'git pull' uses to update the current branch.

See 'git help config' and search for 'push.default' for further information.
(the 'simple' mode was introduced in Git 1.7.11. Use the similar mode
'current' instead of 'simple' if you sometimes use older versions of Git)

Username for 'https://github.com': Cinthia527687
Password for 'https://Cinthia527687@github.com':
Counting objects: 3, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 310 bytes | 0 bytes/s, done.
Total 3 (delta 2), reused 0 (delta 0)
To https://github.com/Cinthia527687/HW_9_Methods_And_Loops.git
   2ed3dfe..085bcdc  master -> master
```

###### Checked my status.


```
F:\Computer Science I\Section 1412 Workspace\HW_9_Methods_And_Loops>git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean
```

## Summary
I'm not an expert on methods and loops. I still don't quite understand how to make a method on my own without a little help.
I hope that in the comming weeks I can get better at this and improve if not master methods and for loops.
My goal is to learn as much as possible from Computer Science I this semester so that I can use that knowlegde for Computer Science II.
Note: I also learned to not leave the command promp unmonitored. I have no clue why I could no longer see my previous commands.
However, I will be sure to not let this happen again.