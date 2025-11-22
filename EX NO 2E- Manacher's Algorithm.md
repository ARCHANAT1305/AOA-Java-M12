
# EX 2E Pattern Matching using KMP Algorithm.
## AIM:
To write a Java program for the following constraints.
Longest Palindromic Substring
Given a string s, return the longest palindromic substring in s.
using Manacher's Algorithm

## Algorithm
1. Start and read the number of test cases T, then input the text and pattern for each case
2. For every possible starting index i in text, compare each character of pattern with the corresponding substring in text.
3. If all characters match, store the index i in a result list.
4. If no match is found after checking all positions, add -1 to the result list. 
5. Finally, print all stored indices (or -1 if not found) for each test case and stop.  

## Program:
#### Developed by:ARCHANA T 
#### Register Number: 212223240013
```
import java.util.*;

public class PatternMatching {

    public static List<Integer> findPatternIndices(String text, String pattern) {
       //Type code here...
       List<Integer> result =new ArrayList<>();
       int n=text.length();
       int m =pattern.length();
       for(int i=0;i<=n-m;i++){
           int j;
           for(j=0;j<m;j++){
               if(text.charAt(i+j)!=pattern.charAt(j)){
                   break;
               }
           }
           if(j==m){
               result.add(i);
               
           }
       }
       if(result.isEmpty()){
           result.add(-1);
           
       }
       return result;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int T = Integer.parseInt(scanner.nextLine()); // number of test cases

        for (int t = 0; t < T; t++) {
            String text = scanner.nextLine();
            String pattern = scanner.nextLine();

            List<Integer> indices = findPatternIndices(text, pattern);
            for (int idx : indices) {
                System.out.print(idx + " ");
            }
            System.out.println();
        }

        scanner.close();
    }
}

```

## Output:
<img width="489" height="214" alt="image" src="https://github.com/user-attachments/assets/b45aa5ee-c16f-42dc-88fb-d438a698e03f" />



## Result:
The program successfully implemented and the expected output is verified.
