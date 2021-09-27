
# Review Session for Section 9 and 10

## Correction and Clarification
- In the Coding Exercise 14, the solution can be further improved as 
``` cpp
int calculate_sum() {

    int sum{0};
    for (int i {0}; i<=15; ++i){
        sum += (i%2) * i;
        
    }
    return sum;
}
```
- In the Coding Exercise 15, the solution can be further improved as 

``` cpp

#include <vector>
using namespace std;

int count_divisible() {
    
    vector<int> vec {1,3,5,15,16,17,18,19,20,21,25,26,27,30,50,55,56,58,100,200,300,400,500,600,700};

    int count{};
    for (auto i: vec){
        count += (i % 3 ==0 || i % 5 == 0);
    }
    return count;
}

```

## Review Questions
Q1. Using `while`-loop Write an input validation loop that asks the user to enter a number in the range of 10 through 25.

Q2. Using `do-while`-loop to write an input validation loop that asks the user to enter ‘Y’, ‘y’, ‘N’, or ‘n’.

Q3. What will the following program segments display?

A) 
``` cpp
int count = 10;
do
{
  cout << "Hello World\n";
  count++;
} while (count < 1);
``` 
B) 

``` cpp
int v = 10;
do
cout << v << endl;
while (v < 5);
```

C) 
``` cpp
int count = 0, number = 0, limit = 4;
do
{
  number += 2;
  count++;
} while (count < limit);
cout << number << " " << count << endl;
```

Q4. Name the three expressions that appear inside the parentheses in the for loop’s header.

Q5. You want to write a for loop that displays “I love to program” 50 times. Assume that you will use a counter variable named `count` . Write the loop. 

Q6. What will the following program segments display?

A) 
``` cpp
for (int count = 0; count < 6; count++)
  cout << (count + count);
```

B) 
``` cpp
for (int value = −5; value < 5; value++)
  cout << value;
```

C) 
``` cpp
int x;
for (x = 5; x <= 14; x += 3)
  cout << x << endl;
  cout << x << endl;
```
Q7. Write a for loop that displays your name 10 times.

Q8. Write a for loop that displays all of the odd numbers, 1 through 49.

Q9. In the following program segment, which variable is the counter variable and which is the accumulator?
``` cpp
int a, x, y = 0;
for (x = 0; x < 10; x++)
{
  cout << "Enter a number: ";
  cin >> a;
  y += a;
}
cout << "The sum of those numbers is " << y << endl;
```
Q10. Write a statement that will convert the contents of the char variable `big` to lowercase. The converted value should be assigned to the variable `little` .

Q11. Write an if statement that will display the word “digit” if the char variable `ch` contains a numeric digit. Otherwise, it should display “Not a digit.”

Q12. What is the output of the following statement?
```cpp
  cout << toupper(tolower('A'));
```
Q13. Write a loop that asks the user "Do you want to repeat the program or quit? (R/Q)" . The loop should repeat until the user has entered an R or Q (either uppercase or lowercase).

Q14. What will the following program segment display?
```cpp
char dog[] = "Fido";
cout << strlen(dog) << endl;
```
Q15. What will the following program segment display?
``` cpp
char string1[16] = "Have a ";
char string2[9] = "nice day";
strcat(string1, string2);
cout << string1 << endl;
cout << string2 << endl;
```

Q16. Write a statement that will copy the string “Beethoven” to the array `composer` .


Q17. 
``` cpp
// This program has the user input a number n and then finds the
// mean of the first n positive integers

// PLACE YOUR NAME HERE

#include <iostream>
using namespace std;

int main()
{
	int value;		// value is some positive number n
	int total = 0;	// total holds the sum of the first n positive numbers 
	int number;		// the amount of numbers
	float mean;		// the average of the first n positive numbers

	cout << "Please enter a positive integer" << endl;
	cin >> value;

	if (value > 0)
	{
		for (number = 1; number <= value; number++)
		{
			total = total + number;
		}	// curly braces are optional since there is only one statement

		mean = static_cast<float>(total) / value;	// note the use of the typecast
													// operator here 
		cout << "The mean average of the first " << value
			 << " positive integers is " << mean << endl;
	}

	else
		cout << "Invalid input - integer must be positive" << endl;

	return 0;
}
```

A) Why is the typecast operator needed to compute the mean in the statement `mean = static_cast<float>(total)/value;`? What do you think
will happen if it is removed? Modify the code and try it. Record what happens. Make sure that you try both even and odd cases. Now put `static_cast<float>total` back in the program.

B) What happens if you enter a float such as 2.99 instead of an integer for value? Try it and record the results.

C) Modify the code so that it computes the mean of the consecutive positive integers n, n+1, n+2, . . . , m, where the user chooses n and m. For example, if the user picks 3 and 9, then the program should find the mean of 3, 4, 5, 6, 7, 8, and 9, which is 6.

# Homework 
Q18. 

``` cpp

// This program finds the average time spent programming by a student
// each day over a three day period.

// PLACE YOUR NAME HERE

#include <iostream>
using namespace std;

int main()
{
	int numStudents;
	float numHours, total, average;
	int student, day = 0;	// these are the counters for the loops

	cout << "This program will find the average number of hours a day"
		 << " that a student spent programming over a long weekend\n\n";
	cout << "How many students are there ?" << endl << endl;
	cin >> numStudents;

	for (student = 1; student <= numStudents; student++)
	{
		total = 0;

		for (day = 1; day <= 3; day++)
		{
			cout << "Please enter the number of hours worked by student "
				 << student << " on day " << day << "." << endl;
			cin >> numHours;

			total = total + numHours;
		}

		average = total / 3;

		cout << endl;
		cout << "The average number of hours per day spent programming by "
			 << "student " << student << " is " << average
			 << endl << endl << endl;
	}

	return 0;
}
```
 Note that the inner loop of this program is always executed exactly three times—once for each day of the long weekend. Modify the code so that the inner loop iterates n times, where n is a positive integer input by the user. In other words, let the user decide how many days to consider just as they choose how many students to consider.

Sample Run:
```
This program will find the average number of hours a day that a student spent programming over a long weekend

How many students are there?
2
Enter the number of days in the long weekend
2

Please enter the number of hours worked by student 1 on day 1
4

Please enter the number of hours worked by student 1 on day 2
6

The average number of hours per day spent programming by student 1 is 5


Please enter the number of hours worked by student 2 on day 1
9

Please enter the number of hours worked by student 2 on day 2
13

The average number of hours per day spent programming by student 2 is 11
```

Q19. Modify the program from Q18 so that it also finds the average number of hours per day that a given student studies biology as well as programming. For each given student include two prompts, one for each subject. Have the program print out which subject the student, on average, spent the most time on.

Q20. Using C++ style string to write a program that reads a sentence as input and converts each word of the sentence following the rule below:

- For every word in the sentence, the first letter is relocated the end of the word.
- Then append the string “KPU” to the word. 

More requirements:
- All letters in the output should be uppercase. 

More assumptions:
- The input sentence contains no non-alphabetic letters

Sample Run:

```
Please enter the original sentence: i LOVE to program
Translated: IKPU OVELKPU OTKPU ROGRAMPKPU
```

