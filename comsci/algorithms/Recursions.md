# Recursions

An algorithmic concept in which a problem is split into two parts (a **base** case and a **recursive** case). The problem divides itself into smaller sub-problems each time until we finally hit a base case. That's when all the solutions so far are combined together to produce a result.

Here's a classic real-world example:

Let's say you go to the movie theater and you want to know the total number of row that have been filled in for tonight's show. Instead of standing up and walking up and down the path to count the number of rows by yourself, you simply ask the person sitting in front of you what row he is in. The person in front of you doesn't know either, so he asks the person sitting in front of him as well. As everyone does so, eventually we'll find the guy who sits in the front row. He'll yell "1" since he's sitting in the first row. And then everyone else sitting behind the first person will begin increasing the counter until you finally get the answer.

That's recursion!