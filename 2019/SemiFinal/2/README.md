# Code Gladiators Semi Final 2019 Problem #2's Solution

## The Problem

~~Sadly, the original problem has been lost in the annals of time. Or to put it less dramatically, I didn't have enough sense at the time to save it somewhere.  But fear not, we have the next best thing - my own description of the same.~~ Keyur provided the original problem statement.

Two national parties BJP and Congress are head to head in the election and are blaming each other as always. The Election has become interesting because of the importance of Regional parties. BJP is boasting on the work done during their tenure by the Government and how much they thought for the nation and people. On the other hand, Congress and other parties are calling it a hoax and urging people to vote for them. BJP star campaigners are just launching the missiles and making place amongst the people again. Congress is worried because of their track record and are breaking the boundaries to get to the people. The other Regional parties are also pulling out every trick in their book. The Election is taking ups and downs frequently.

 <img width="800" alt="image" src="https://user-images.githubusercontent.com/11571484/171372372-5b5bd22b-d8b2-4138-bb67-5b51359f7e3c.png">

The voting is done in various phases and News channels are on the edge of their seats covering the areas where elections are to be held. Opinion polls are being conducted in the areas and public opinion is taken to predict the winner of the elections. People are also talking whether the Modi led Government will continue to rule or the Congress and other parties would be able to pull out some magic.

There are many political pandits and experts in the news industry which are covering the elections for a long time now. With their experience in the political field, they have come out with a theory which they claim can predict if the BJP government will come to power again or not.

The experts have formed a matrix in the form of **Phases** and **States**.

 <img width="800" alt="image" src="https://user-images.githubusercontent.com/11571484/171372407-c0e1fe25-6a73-403f-9c0a-392971d9f704.png">

The experts have provided the number of wins required by BJP in different phases and states to form the government. According to theory, if it is possible to arrange the wins required by BJP in the form of experts matrix, then they will definitely form the government otherwise there will be a new government.

If BJP can form the government as per the theory, then the output would be "**YES**" indicating that people are happy with the government otherwise the output would be "**NO**" indicating that people are unhappy with the government.

**Note:** There are different seats in States which are to be voted in different phases. The number of phases and states is not restricted to the actual number of states and phases in the Indian Election.


## Input Format
 - The first line consists of **T**, number of test cases. 
 - The first line of each test case consists of **r** and **c**, number of phases and states respectively.
 - The second line of each test case consists of the number of wins ri required by BJP in the phases to win elections.
 - The third line of each test case consists of the number of wins ci required by BJP in the States to win the elections.



## Constraints
 - 1<=T<5
 - 1<= r, c <=100000
 - 0<= ri <=c
 - 0<=ci <=r

## Output Format
Print "**YES**" (without quotes) if BJP can form the government as per the experts theory otherwise print "**NO**" (without quotes).


## Sample TestCase 1
### Input
> 2\
> 3 2\
> 2 1 0\
> 1 2\
> 3 3\
> 3 2 1\
> 1 2 2

### Output
> YES\
> NO

### Explanation
#### Test Case 1
As per the theory, to form the government, BJP should win 2 seats in the first phase, 1 seat in second phase and 0 in last phase.

BJP also needs to follow the number of wins in states column wise. There should be a single win in the seats of first state and 2 wins in the seats of second state.

<img width="400" alt="image" src="https://user-images.githubusercontent.com/11571484/171372472-d3a7b727-784d-47a8-b0fa-0aa0231a4b20.png">
 
It is possible for BJP to win the seats in this format and form the matrix as per the theory. The matrix can be successfully made thus BJP can form the government. Thus, the answer is **YES**.

#### Test Case 2 
It is not possible to create the matrix with respective wins by BJP in phases and states. Thus, the answer is **NO**.

## Simple explanation of the problem
Consider a matrix with 'n' rows and 'm' columns. Each cell in this matrix is occupied with either the value of 0 or 1. Now, if we add up the values in the cells of a column, we obtain what I hereafter refer to as a **column-summation**. And similarly, if we add up the values in the cells of a row, we obtain the **row-summation**. The problem is to figure out if it is possible to create a matrix with the following constraints:
* Given value of 'n' rows and 'm' columns
* Cell arrangements that lead to a specific list of column-summations and row-summations 

Eg: So if I request you to create a matrix with 3 rows and 4 columns such that each cell has either 0 or 1 in it AND the row-summations are 4, 2 and 1 AND the column-summations are 3, 2, 1 and 1; would you be able to create it? YES or NO? (Note: For these values, the answer is YES, as shown below.)

Alternatively, the problem could be succinctly described as checking the feasibility of creation of a [binary matrix](https://en.wikipedia.org/wiki/Logical_matrix) when the summation values for each row and column in the matrix are provided. 

Consider the following binary matrix (with added column and row summations in bold)

Counts | 3 | 2 | 1 | 1
------ | ---| ---| ---| ---
**4**| 1 | 1 | 1 | 1
**2**| 1 | 1 | 0 | 0
**1**| 1 | 0 | 0 | 0

### Nitty Gritties
The problem statement further states that:
* the code should be able to process multiple test cases
* all input should be read from standard input
* the first line should indicate the number of test cases
* for each test case the first line would indicate the number of rows followed by the number of columns, followed by the space-delimited row-summations and column-summations on the second and third line of each test case.
* For each test case, the code should simply output (on a new-line) YES or NO according to the feasibility

### Sample Execution

Input

```
2 <-- Number of test cases
3 4 <-- Test case 1: count of rows followed by count of columns
4 2 1 <-- Test case 1: Row summation values
3 2 1 1 <-- Test case 1: Column summation values
3 4 <-- Test case 2: count of rows followed by count of columns
3 3 0 <-- Test case 2: Row summation values
3 1 1 1 <-- Test case 2: Column summation values
```

Corresponding Output
```
YES <-- According to first test case's constraints, a binary matrix can be created
NO <-- According to second test case's constraints, a binary matrix CANNOT be created
```

### Explanation
The first test case i.e. 
```
3 4
4 2 1
3 2 1 1
```
asks us to check if it is possible to create a binary matrix with 3 rows and 4 columns. Also the summation of values (i.e. total occurances of 1) in the rows should be 4, 2 and 1. And subsequently the summation of values in the columns should be 3, 2, 1 and 1.

The expected answer for this test case is YES as it is trivial to create such a matrix, as demonstrated above.

Conversely, the expected answer for the second test case is NO as it is not possible to create a matrix with the given set of conditions.

Armed with this understanding let's dive into the solution - or rather I should say let's relive my tiresome search for the optimum solution.

## Evolution of the Solution
So right off the bat, I figured that an easy way to figure out at least some of the NOs would be to add up all the column-summation values and compare that value with the sum of the row-summation values. If these 2 values differ then it's a straightforward NO. Reason being, that the total count of 1's in a matrix is going to remain the same, whether you add up the columns first or the rows. That was simple. Moving on.

Please note that all of the different versions described below are part of this repo as [different versions of the same file](../../../../../commits/master/2019/SemiFinal/2/CandidateCode.java).

### Version 1
I created a function **preliminaryValidation** to take care of the above mentioned validation along with few other trivial ones like:
* ensuring that an individual row-summation value is > 0 and < column_count AND
* ensuring that an individual column-summation value is > 0 and < row_count

I'm unsure now why I took it upon myself to handle these validations as these were sanity constraints already imposed by the Problem creators. Hmmm.

I created a function **minimize** which was meant to reduce the complexity of the overall problem. This function checked for any full-capacity rows i.e. if a matrix had 4 columns and 1 of the row-summation values was 4, we could infer from this that all of the columns had 1 present in them for that 1 row. So this minimize function would check for such full-capacity rows and remove them from the equation.

So effectively it would look for an input like this:
```
3 4
4 2 1
3 2 1 1
```

which has a solution as 

Counts | 3 | 2 | 1 | 1
------ | ---| ---| ---| ---
**4**| 1 | 1 | 1 | 1
**2**| 1 | 1 | 0 | 0
**1**| 1 | 0 | 0 | 0

and convert it to a smaller problem like:

```
2 4
2 1
2 1 0 0
```

which has a solution as

Counts | 2 | 1 | 0 | 0
------ | ---| ---| ---| ---
**2**| 1 | 1 | 0 | 0
**1**| 1 | 0 | 0 | 0

Then I would traspose the matrix and continue to exploit this for any "full-capacity columns". Finally after exhausting the utility of minimize, I am not ashamed to admit that I resorted to using brute-force to check if it was possible to create the binary matrix. 

Submission Outcome: 10 points out of 100. I'm guessing most of the test cases which failed for this version were due to TLE (aka Time Limit Exceeded) i.e. my code was too slow. Ouch!

### Version 2
I assumed (incorrectly) that probably I could save some time (for extremely long values of row-count and column-count) by avoiding an iteration. I did this by replacing my earlier **stringToList** function with an inline processing which did 2 things in the same loop:
* parse the String values (received from standard input) into integers AND
* calculate the sum of row-summations/column-summations.

Submission Outcome: (probably still) 10 points out of 100

### Version 3
What happened to Version3? Ummm... I will let you know as soon as I find out. 

### Version 4
I did some minor changes which were not really related to the logic (so in other words illogical changes, eh?) like:
* Swapped a LinkedList with an ArrayList
* Used a slightly optimum way to sort the lists in the reverse-order 
```
Collections.sort(rows, Collections.reverseOrder()); //Ooooh
```
* Used a ListIterator

I did modify some portion of the logic. For the life of me, I am not sure what made me make [these changes](../../../../../commit/4e8ab8aceddddf857a3c89d254ca40f18ac6779d). But it increased my score by 30 points. Woohoo!

Submission Outcome: 40 points out of 100

### Version 5
Ignore this

### Version 6
I started focusing on short-circuit evaluations for NO scenarios in this version. I checked if the ordered row-summations list is an exact copy of the ordered column-summations list. Also I reduced the maximum possible values for row-summations. Earlier the max allowed value for a row-summation was the column-count i.e. if a matrix has 5 columns then it's not possible for an individual row-summation to be greater than 5. In this version I reduced that further by the total count of columns with summations as zero. That is if a matrix has 5 columns but 2 of those columns have just zeroes in them (i.e. 2 of the column-summations are 0), then the max possible value for any row-summation value for this matrix would be 5 -2 = 3. I did some other mumbo-jumbo changes in the code as well. I was really hoping this would get me the elusive 100/100 score. Alas, it went to the other extreme.

Submission Outcome: 0 points

### Version 7
I cleaned up my code in this version. Instead of transposing and re-processing the matrix conditions inside my **preliminaryValidation** function, I cleaned it up to just process from a rows-perspective. Then I transposed the matrix and invoked the same function again. This fixed whatever glitches were unintentionally introduced in version 6. By now, I was at my wit's end and was more that willing to throw in the towel if this didn't work.

Submission Outcome: 40 points (Arghh! but at least 40 > 0) The only failures were due to TLEs. 

### Version 8
At this point I had no idea how to further refine my logic. So I felt that I was missing something very basic and probably the overall logic itself was flawed (or at least unnecessarily complex). I was actually considering writing a program to churn out various combinations of random inputs (as test-cases). My "plan" was to solve these on paper manually and then let my code solve the same. I would then try to figure out if my logic was flawed or alternatively I might discover some other pattern that I could exploit to find a faster solution.

Thankfully, I had a kid visiting me at home at that time and I asked her to come up with a few different random test-cases manually for me. I had to explain to this college kid what a matrix was. Let's observe 1 minute of silence for our education system. Moving on.

In some of the test-cases that she came up with, she used a lot of zeroes for the row/column-summations. This led me to the discovery of the very simple yet elegant solution that is Version 8. Following are the constraints that I checked for:

* max_possible_row = column_count - empty_columns (Version 6 deja-vous)
i.e. the maximum possible row-summation value = total number of columns - count(column-summations which are zero)
* min_possible_row = full_columns
i.e. the minimum possible row-summation value = count(column-summations which are equal to count of rows)

Also, I optimized the above comparison by first sorting the row/column summations list and then picking the max and min values from just the ends (as opposed to applying the above 2 comparisons for each element). Additionally I did the sum(row-summations) == sum(column-summations).

Submission Outcome: 100 points (finally)

## Moral of the story
There is a reason why I went through all of my failed versions before getting to the final solution. I wanted to highlight that more often than not failures accompany us on the road to victory. I don't think that I am smarter or more talented than my peers who couldn't solve this problem. But I will tell you this, the only reason why I did finally solve it, is because I refused to give up. I like how we usually say "find a solution" as opposed to "create a solution". Because the former phrase assumes that a solution indeed exists; all we have to do is go and find it! And one of the reasons why I kept striving was because in the statistics tab on the results page I could see that there were several others who had obtained a score of 100. I said to myself, "Hmm, if so many others can do it, then maybe I can to."

Some other misc learning points for us (including me):
* Do not be afraid to throw away your code. I kept refining and tweaking the code (from Version 1 to Version 7). But finally what worked was a complete rewrite.
* Sometimes a problem has a very simple yet elegant solution. Everything does not need to be brute-forced.

Finally for next time, Be Persistent and Don't give up! :)
