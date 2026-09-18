
# EX 4E Longest Increasing Subsequence - Dynamic Programming.
## DATE: 17-08-2026
## AIM:
To write a Java program to for given constraints.
Given an integer array nums, return the length of the longest strictly increasing subsequence.
Example 1:
Input: nums = [10,9,2,5,3,7,101,18]
Output: 4
Explanation: The longest increasing subsequence is [2,3,7,101], therefore the length is 4.
## Algorithm
```
1.Initialize a DP array dp[] where each element starts as 1 (each number is an LIS of length 1 by itself).
2.For each index i from 1 to n-1, compare nums[i] with all previous nums[j].
3.If nums[i] > nums[j], update dp[i] = max(dp[i], dp[j] + 1).
4.Maintain a variable ans to store the maximum LIS length found.
5.Return ans as the final answer.
```
## Program:
```
/*
Program to implement Reverse a String
Developed by: SANDHIYA SREE B
Register Number:  212223220093
*/
```
```
import java.util.*;

public class LongestIncreasingSubsequence {

    public static int lengthOfLIS(int[] nums) {
        int n=nums.length;
        int[] dp=new int[n];
        Arrays.fill(dp,1);
        int ans=0;
        for(int i=1;i<n;i++){
            for(int j=0;j<i;j++){
                if(nums[i]>nums[j]){
                    dp[i]=Math.max(dp[i],dp[j]+1);
                    ans=Math.max(ans,dp[i]);
                }
            }
        }
        return ans;
    }

public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt user input
        int n = scanner.nextInt();
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = scanner.nextInt();
        }

        // Calculate and display the length of LIS
        int result = lengthOfLIS(nums);
        System.out.println("Length of Longest Increasing Subsequence: " + result);

        scanner.close();
    }
}

```

## Output:

<img width="1120" height="253" alt="image" src="https://github.com/user-attachments/assets/ffae43d0-6f07-49a4-9642-7d1accb494d6" />


## Result:
The program successfully implemented and the expected output is verified.
