## Lab Report 5
Below is a simulated conversation with a student and TA.
## Issue with AverageCalculator.java
# _posted by Anonymous_
I wrote a function to calculate the average of any integer array of numbers. The function is located inside of my file called ``AverageCalculator.java``. Here is a screenshot of the code and the code for the class below: 
![Image](AverageCalculator.png)
```
public class AverageCalculator {

    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};
        double result = calculateAverage(numbers);
        System.out.println("Average: " + result);
    }

    public static double calculateAverage(int[] numbers) {
        int sum = 0;
        for (int i = 0; i <= numbers.length; i++) {  
            sum += numbers[i];
        }
        return (double) sum / numbers.length;
    }
}
```
  Every time I run the file using my bash script, it tells me the compilation was successful, but there's an 
  ArrayOutOfBounds error that I get when I run it. I tried running it with several different arrays, but it keeps 
  giving me the same exception. I noticed that each time I try a different array, it gives me the same out of 
  bounds error with the length of the array as out of bounds. 

![Image](error.png)
```
nidaf@TABLET-0ECIG2SB MINGW64 ~/lab5
$ bash test.sh
Compilation successful. Running AverageCalculator...
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 5 out of bounds for length 5
        at AverageCalculator.calculateAverage(AverageCalculator.java:12)
        at AverageCalculator.main(AverageCalculator.java:5)
```
I tried checking line 5, but I'm not sure where to look to fix the bug. Could you help me out? 

## Reply to: Anonymous 
# _posted by: TA Ben Programmer_
    Hello! I see you're having an issue with your ```AverageCalculator.java``` class. The failure inducing input 
    here seems to be the array you pass into your ```main``` method in the ```.java``` file. I can't see what's 
    happening in your bash script, could you explain what you need the bash script to do and what code iscurrently 
    present there? 

## Reply to: Ben Programmer
# _posted by Anonymous_

My bash script is supposed to compile and run the ```AverageCalculator.java``` file. It currently looks like this:
```

javac AverageCalculator.java
![Image](bash.png)
if [ $? -eq 0 ]; then
    echo "Compilation successful. Running AverageCalculator..."
    java AverageCalculator
else
    echo "Compilation failed. 
fi
```
The script successfully compiles the file, but it prints out the error message right afterward. I think that means my program is correct? 

## Reply to: TA Ben Programmer 
# _posted by: Anonymous_

Okay! Looking at the picture, can see that your bash script is meant to compile the file, then run it if compilation is successful. If compilation is 
successful, it means that the compiler successfully found the file and was able to understand the code. The ```ArrayIndexOutOfBoundsException```
below  ```'Compilation successful``` shows that there is a bug within your program itself, given that it took in input from your main method. 
I am going to make the following suggestions: 

- Try creating a separate file to run your tests as JUnit. This will allow you to 


