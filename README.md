# HW_9_Methods_And_Loops 

## Introduction

We are going back to our friend the addition game.
We are now going to rework the addition game using methods and for loops.

## Outline



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

## Summary
I'm not an expert on methods and loops. I still don't quite understand how to make a method on my own without a little help.
I hope that in the comming weeks I can get better at this and improve if not master methods and for loops.
My goal is to learn as much as possible from Computer Science I this semester so that I can use that knowlegde for Computer Science II.