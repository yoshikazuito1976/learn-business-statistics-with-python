# 03 Variance and Standard Deviation

## English

This chapter covers variability in data, which cannot be understood by average alone.

Even when two datasets have the same average, their spread can be very different.

```text
A: 48, 49, 50, 51, 52
B: 10, 30, 50, 70, 90
```

Both averages are 50, but B is much more spread out.

## Why average is not enough

In business, stability matters:
- Are daily sales stable?
- Is customer traffic fluctuating too much?
- Are processing times consistent?

Average shows center, but not spread.

## First step: deviation

Deviation means distance from average.

```text
deviation = value - mean
```

Example for 40, 50, 60 (mean 50):

```text
-10, 0, 10
```

If you sum deviations, positives and negatives cancel to 0.
So you cannot measure spread that way.

## Square then average: variance

Square each deviation:

```text
(-10)^2 = 100
0^2 = 0
10^2 = 100
```

Variance is the average of squared deviations.

```text
variance = average of squared deviations
```

## Standard deviation

Variance is in squared units, so it is less intuitive.
Take square root of variance to return to original unit.
That value is standard deviation.

```text
standard deviation = sqrt(variance)
```

## Python check

```python
data = [40, 50, 60]

mean = sum(data) / len(data)
deviations = [x - mean for x in data]
squared = [d ** 2 for d in deviations]
variance = sum(squared) / len(data)
std = variance ** 0.5

print("mean:", mean)
print("deviation:", deviations)
print("squared deviations:", squared)
print("variance:", variance)
print("std:", std)
```

## Compare two datasets

```python
data_a = [48, 49, 50, 51, 52]
data_b = [10, 30, 50, 70, 90]
```

Same average, different variance/std.
This is why average-only judgment can miss important risk.

## NumPy version

```python
import numpy as np

data = [40, 50, 60]
print(np.mean(data))
print(np.var(data))
print(np.std(data))
```

## Business meaning

Two stores can have same average sales, but one can be unstable.
Standard deviation helps evaluate stability and risk.

## Summary

- Average shows center
- Variance/standard deviation show spread
- Same average does not mean same behavior
- In business, look at both level and stability
