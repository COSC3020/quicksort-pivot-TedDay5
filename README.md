# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

Within the lecture 01 sorting slides, slide 52 explains how 1/2 of the array is a good pivot as long as it's not within the first 1/4 or last 1/4 of the array.
If we always pick the left most element as the pivot it has a 50% chance of being a good pivot since it could be the middle 1/2 or the first and last 1/2 (1/4 + 1/4 = 1/2).

Using the median-of-three method to pick a pivot, there's 3 possiblities of left, middle, and right sections of the array. 
It's the same probability as before where the bad pivots would be L = 1/4, and R = 1/4 while the good pivots would be M = 1/2.
Worse case would be three L L L.
The other cases would be L L R, L R L, L R R, R R R, R R L, R L R, and R L L.
Out of the 8 possible, each with a 1/64 chance of appearing, median-of-three pivots there's only a 1/8 chance of the pivot being strictly bad.
Total of (2/16) chance.
The other bad case would be either L or R are chosen twice while M is chosen once.
L L M, L M L, M L L, R R M, R M R, M R R.
Out of 6 possible, there would be 1/32 * 6 chance of the pivot being strictly bad.
Total of (3/16) chance.

Combining all the bad cases results with a probability of 5/16 chance of a bad pivot, meaning we have a 11/16 chance to have a good pivot.
Chosing the leftmost element as the pivot results in a good pivot 50% of the time while using the median-of-three method results in a good pivot 68.75% of the time.
50% < 68.75% so median-of-three method is superior.

“I certify that I have listed all sources used to complete this exercise, including the use
of any Large Language Models. All of the work is my own, except where stated
otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is
suspected, charges may be filed against me without prior notice.”
