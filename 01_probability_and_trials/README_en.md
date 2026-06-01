# 01 Probability and Trials

## English

In this chapter, you learn probability and trials.

Probability does not predict one single result exactly.
It is a tool to think about trends that appear when the same condition is repeated many times.

## Objectives

- Understand probability
- Understand trials
- Understand the difference between one trial and repeated trials
- Understand that probability and actual outcomes do not always match
- Observe that larger trial counts reveal trends more clearly
- Simulate probabilistic phenomena with Python

## What is probability?

Probability is a number that represents how likely an event is.

For a lottery with a 10% win chance, 10% does not mean "you win 0.1 times in one draw."
One draw is either win or lose.

10% means: over many repeated draws under the same condition, the win ratio tends to be around 10%.

## What is a trial?

A trial is one experiment/action under the same condition.

Examples:
- Draw one lottery ticket
- Roll a die once
- One user visits a product page
- Send one email
- Show one ad impression

In business statistics, we focus on trends from multiple trials, not one outcome only.

## Example: a 10% lottery

In one draw:
- Win
- Lose

From one draw, it is hard to "feel" 10%.
When repeated 100, 1000, 10000 times, the win ratio tends to approach 10%.

Important distinction:
- One result
- Trend from repetition

## Probability of at least one win in 10 draws

Two different statements:
- Win probability of one draw is 10%
- Probability of at least one win in 10 draws is not 10%

Use the complement event:

```text
P(at least one win) = 1 - P(no wins in 10 draws)
P(no wins in 10 draws) = 0.9^10 = 0.3486784401
P(at least one win) = 1 - 0.9^10 = 0.6513215599
```

So, for intuition, about 65% is enough to remember.
10% is "per-draw likelihood," not the whole 10-draw event probability.

## Expressing the lottery in Python

```python
import random

if random.random() < 0.1:
    print("win")
else:
    print("lose")
```

## Repeat 100 draws

```python
import random

win_count = 0
trial_count = 100

for i in range(trial_count):
    if random.random() < 0.1:
        win_count += 1

print("trials:", trial_count)
print("wins:", win_count)
print("win rate:", win_count / trial_count)
```

The result changes each run.
Probability does not guarantee exact matching in one run.

## Increase trial count

```python
import random

trial_counts = [10, 100, 1000, 10000]

for trial_count in trial_counts:
    win_count = 0

    for i in range(trial_count):
        if random.random() < 0.1:
            win_count += 1

    win_rate = win_count / trial_count
    print(trial_count, win_count, win_rate)
```

Small trial counts fluctuate more.
Larger trial counts tend to approach 10%.

## Check by graph

```python
import random
import matplotlib.pyplot as plt

trial_counts = [10, 100, 1000, 10000]
win_rates = []

for trial_count in trial_counts:
    win_count = 0
    for i in range(trial_count):
        if random.random() < 0.1:
            win_count += 1
    win_rates.append(win_count / trial_count)

plt.bar([str(x) for x in trial_counts], win_rates)
plt.axhline(0.1, linestyle="--")
plt.xlabel("Number of Trials")
plt.ylabel("Win Rate")
plt.title("Win Rate by Number of Trials")
plt.show()
```

## Connection to business

Single outcomes can be misleading:
- One ad did not sell
- One email got no reply
- One user did not purchase
- One respondent gave a bad score

Business statistics requires multiple trials and overall trends.

## Summary

- Probability indicates likelihood
- One outcome and repeated-trial trend are different
- Small trial counts fluctuate
- Larger trial counts reveal trend
- Python helps simulate probabilistic phenomena

Next chapter: average and expected value.
