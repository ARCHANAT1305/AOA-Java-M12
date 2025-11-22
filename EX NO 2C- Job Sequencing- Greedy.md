# EX 2C Job Sequencing using Greedy Approach
## AIM:
To write a Java program to for given constraints.
Given an integer array nums and an integer k, return the number of pairs (i, j) where i < j such that |nums[i] - nums[j]| == k.

The value of |x| is defined as:

x if x >= 0.
-x if x < 0.You're given N jobs, each with:

A unique jobId

A deadline (by which it must be completed)

A profit (earned only if completed on or before the deadline)

Each job:

Takes exactly 1 unit of time

Only one job can be done at a time

Your goal is to maximize total profit while completing the maximum number of jobs possible within their deadlines.

## Algorithm
1. Start and read the number of jobs n, along with each job’s id, deadline, and profit.
2. Sort all jobs in descending order of profit to prioritize the most profitable ones.
3. Find the maximum deadline to determine the number of available time slots.
4. For each job, starting from its deadline and moving backward, assign it to the latest free slot available and update total profit and job count.
5. After scheduling all possible jobs, print the number of jobs done and the total profit earned, then stop.

## Program:
#### Developed by: 
#### Register Number: 
```
import java.util.*;
public class JobScheduling {
    static class Job {
        int id, deadline, profit;
        Job(int id, int deadline, int profit) {
            this.id = id;
            this.deadline = deadline;
            this.profit = profit;
        }
    }
    public static int[] jobScheduling(Job[] jobs, int n) {
        Arrays.sort(jobs, (a, b) -> b.profit - a.profit);
        int maxDeadline = 0;
        for (Job job : jobs) {
            maxDeadline = Math.max(maxDeadline, job.deadline);
        }
        int[] slot = new int[maxDeadline + 1]; // 1-based indexing
        Arrays.fill(slot, -1);
        int countJobs = 0, totalProfit = 0;
        for (Job job : jobs) {
            for (int j = job.deadline; j > 0; j--) {
                if (slot[j] == -1) {
                    slot[j] = job.id;
                    countJobs++;
                    totalProfit += job.profit;
                    break;
                }
            }
        }
        return new int[]{countJobs, totalProfit};
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        Job[] jobs = new Job[n];

        for (int i = 0; i < n; i++) {
            int id = sc.nextInt();
            int deadline = sc.nextInt();
            int profit = sc.nextInt();
            jobs[i] = new Job(id, deadline, profit);
        }
        int[] result = jobScheduling(jobs, n);
        System.out.println(result[0] + " " + result[1]);
    }
}
```

## Output:

<img width="326" height="292" alt="image" src="https://github.com/user-attachments/assets/c467c04f-baf5-4a50-a7db-ef878df68037" />


## Result:
The program successfully implemented and the expected output is verified.
