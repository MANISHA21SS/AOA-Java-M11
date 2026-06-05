
# EX 1A Print All Numbers 
## DATE: 16/04/26
## AIM:
To Write a Java program that takes an integer input N from the user and prints all the numbers from 1 to N, separated by spaces, on a single line..

## Algorithm
1.Start the program.

2.Input an integer N from the user.

3.Check condition: If N <= 0, display "Invalid input. N must be greater than 0." and stop.

4.Initialize a variable i = 1.

5.Use a loop to print numbers from 1 to N:

While i <= N, print i followed by a space.

Increment i by 1.

End loop and stop the program.  

## Program:
```
/*

Developed by: Manisha selvakumari.S.S.
Register Number: 212223220055
*/
import java.util.Scanner;
public class PrintNumbers{
    public static void main(String[] args){
        Scanner scanner = new Scanner(System.in);
        int n = scanner.nextInt();
        if(n<=0){
            System.out.println("Invalid");
        }else{
            for(int i=1;i<=n;i++){
                System.out.print(i+" ");
            }
        }
    }
}
```

## Output:

<img width="1236" height="158" alt="image" src="https://github.com/user-attachments/assets/28684235-9371-49bb-a7d9-d7a2e53a96c6" />



## Result:
The program successfully print all the numbers from 1 to N. 
