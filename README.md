# Secretary-Problem
The secretary problem demonstrates a scenario involving optimal stopping theory[1][2] that is studied extensively in the fields of applied probability, statistics, and decision theory. It is also known as the marriage problem, the sultan's dowry problem, the fussy suitor problem, the googol game, and the best choice problem.

This problem can be stated in the following form: Imagine an administrator who wants to hire the best secretary out of n rankable applicants for a position. The applicants are interviewed one by one in random order. A decision about each particular applicant is to be made immediately after the interview. Once rejected, an applicant cannot be recalled. During the interview, the administrator can rank the applicant among all applicants interviewed so far but is unaware of the quality of yet unseen applicants. The question is about the optimal strategy (stopping rule) to maximize the probability of selecting the best applicant. The difficult part of this problem is that the decision must be made immediately after interviewing a candidate.

### 1/e law of Optimal Strategy
According to this strategy, the optimal win probability is always at least 1/e. The optimal stopping rule prescribes always rejecting the first n/e applicants that are interviewed (where e is the base of the natural logarithm and has the value 2.71828) and then stopping at the first applicant who is better than every applicant interviewed so far (or continuing to the last applicant if this never occurs). This strategy is called the 1/e stopping rule because the probability to select the best candidate is 1/e, in other words, this strategy selects the best candidate about 37% of time. If you think carefully, it might seem obvious that one cannot select the first candidate because the first candidate has no one to compare with. A better strategy is to choose a few candidates as a sample to set the benchmark for remaining candidates. So the sample will be rejected and will only be used for setting benchmark. So, we have two different states:

* If a sample is too small, we don’t get information enough for setting the benchmark for remaining candidates.

![image](https://user-images.githubusercontent.com/125180530/218307037-e05dd8ef-8823-4ef6-8404-fc19337d09b5.png)

* If a sample is too large, though we get plenty of information but we have also burned too many of the potential candidates. This leaves us with very few candidates to choose from, and hence making the strategy a poor one.

![image](https://user-images.githubusercontent.com/125180530/218307055-0469b060-b647-4842-a117-435ccc70591e.png)

The best strategy is to choose the perfect or optimal sample size which can be done using 1/e law that is rejecting n/e candidates (this n/e is the sample size).

![image](https://user-images.githubusercontent.com/125180530/218307093-f88b1cf2-c643-4658-abaa-52d9a7827f55.png)

### Formulation of the Secretary Problem

![image](https://user-images.githubusercontent.com/125180530/218307677-00291834-972e-4eb6-9a56-a849e0e3e855.png)
![image](https://user-images.githubusercontent.com/125180530/218307695-1767c1b4-f988-4dd0-bed0-27f6bca6ee33.png)

If i is the best candidate, he is selected if and only if the best candidate among the first i-1 candidates, is the best candidate among the first k-1 eliminated candidates. Now if we converge n to infinity we have:

![image](https://user-images.githubusercontent.com/125180530/218307730-51c6aa20-b9f1-4117-8af8-a6e7790cce5a.png)

Now we want to find x in which we have the maximum probability P(x):

![image](https://user-images.githubusercontent.com/125180530/218307741-be069f03-451d-4c54-8bfa-5a8af6a83ad9.png)

### Implementations
First, for n = 100 and k = range(5, 101, 5), and for 10000 experiments we do the implementation. (Calculating the probability of choosing the best candidate after eliminating k first candidates). 

The next step is to repeat the implementation considering k = n/e while n changes from 3 to 100. 

Now, consider we have a function that generates a population for us. (This function is given in the Dist file). We choose a random population among the primary population for n = 100 and calculate the mean of the population for different repeats of this process and then plot the calculated means and see that it has a normal distribution. 

Now, we use the wine dataset and do the previous process by choosing n random columns of this dataset and plotting the graphs. We can then compare the calculated mean and standard deviations with the values calculated by the Central limit theorem. 
