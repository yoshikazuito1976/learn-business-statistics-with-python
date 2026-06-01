# 02 Average and Expected Value

## English

In this chapter, you learn average and expected value.

In the previous chapter, you compared one result and repeated-trial trends using a 10% lottery.
Now you go one step further: if you draw 10 times, how many wins are expected on average?

## Objectives

- Understand average
- Understand expected value
- Understand that expected value is not a guaranteed result
- Use probability times count to estimate average outcomes
- Verify with Python simulation
- Connect average/expected value to business decisions

## What is average?

Average is a representative value obtained by smoothing multiple values.

```text
2, 4, 6, 8, 10
(2 + 4 + 6 + 8 + 10) / 5 = 6
```

Average is useful, but average alone does not fully explain data.

## Python example for average

```python
values = [2, 4, 6, 8, 10]
average = sum(values) / len(values)
print(average)
```

## What is expected value?

Expected value is the average outcome if a probabilistic event is repeated many times.

For a 10% lottery drawn 10 times:

```text
10 x 0.1 = 1
```

So the expected number of wins is 1.

Important: expected value is not a guaranteed one-run outcome.
One set of 10 draws can be 0, 1, 2, or more wins.

## Expected value vs actual result

A single set can vary, but the average across many sets tends toward the expected value.

```text
0, 1, 2, 1, 0, 3, 1, 2, ...
```

## Concrete examples of expected value

### Example 1: Ad clicks

Click rate is 5%, ad shown to 100 users:

```text
100 x 0.05 = 5
```

Expected about 5 clicks on average, but actual could be 3 or 8.

### Example 2: Sales conversions

Conversion rate is 10%, 30 sales calls:

```text
30 x 0.1 = 3
```

Expected around 3 deals on average, but actual can be 0 or 5+.

### Example 3: Inquiry handling time

Average handling time is 12 minutes, 20 inquiries:

```text
20 x 12 = 240
```

Estimated total is 240 minutes (about 4 hours), but each inquiry differs.

### Example 4: Revenue forecast

Average purchase is 3000 yen, 100 buyers:

```text
100 x 3000 = 300000
```

Expected revenue is around 300,000 yen, though individuals vary.

### Example 5: Gacha / lottery

Win rate 2%, 100 draws:

```text
100 x 0.02 = 2
```

Expected around 2 wins on average, but actual can be 0, 1, or 3+.

### Example 6: Absence forecast

Absence probability per student is 5%, class size 40:

```text
40 x 0.05 = 2
```

Expected around 2 absences on average, but day-to-day results vary.

### Example 7: Defective products

Defect rate 1%, production 1000 units:

```text
1000 x 0.01 = 10
```

Expected around 10 defects on average, but actual can differ.

## Python simulation for expected value

```python
import random

p = 0.1
trials_per_set = 10
set_count = 1000
results = []

for _ in range(set_count):
    win_count = 0
    for i in range(trials_per_set):
        if random.random() < p:
            win_count += 1
    results.append(win_count)

average_wins = sum(results) / len(results)
print("average wins:", average_wins)
```

The result tends to be close to 1 but not exactly 1 every run.

## Why average needs caution

Two datasets can have the same average but very different spread:

```text
A: 4, 5, 6
B: 0, 5, 10
```

So combine average with variance/standard deviation (next chapter).

## Summary

- Average is a representative value
- Expected value is an average forecast under repeated probabilistic events
- Expected value is not guaranteed in one run
- Same average does not mean same data behavior
- In business, use average/expected value together with variability and risk
