# 04 Histogram and Distribution

## Chapter Objective

In this chapter, you learn how to inspect data distributions.

Average and standard deviation are useful summary metrics, but average alone cannot show how data is spread.
Even with the same mean, data shapes can be very different.

- Most values are concentrated near the mean
- Values are split into high and low groups
- A few extreme values pull the mean up

Observation flow in this chapter:

```text
Raw data
->
Frequency table
->
Histogram
->
Interpret distribution
```

## What is a Frequency Distribution Table?

A frequency table groups data into ranges and counts how many values fall into each range.

```python
scores = [45, 52, 58, 61, 63, 67, 70, 72, 75, 78, 80, 82, 85, 88, 92]
```

| Score range | Count |
| --- | ---: |
| 40 to under 50 | 1 |
| 50 to under 60 | 2 |
| 60 to under 70 | 3 |
| 70 to under 80 | 4 |
| 80 to under 90 | 4 |
| 90 to 100 | 1 |

## Frequency, Class, and Class Width

- Frequency: number of values in a class
- Class: each range used to group data
- Class width: size of the class interval

Example class width:

```text
40 to under 50
```

Width is $50 - 40 = 10$.

Wider class width makes global trend easier to see, but hides details.
Narrower class width shows detail, but can make global trend harder to read.

## Create a Frequency Table in Python

```python
import pandas as pd

scores = [45, 52, 58, 61, 63, 67, 70, 72, 75, 78, 80, 82, 85, 88, 92]

bins = [40, 50, 60, 70, 80, 90, 100]
labels = [
    "40 to under 50",
    "50 to under 60",
    "60 to under 70",
    "70 to under 80",
    "80 to under 90",
    "90 to 100"
]

groups = pd.cut(scores, bins=bins, labels=labels, right=False)
frequency_table = groups.value_counts().sort_index()
print(frequency_table)
```

## What is a Histogram?

A histogram is a graph version of a frequency table.

```text
Frequency table: check counts by range as a table
Histogram: check counts by range as a graph
```

The table is precise for numbers.
The histogram is intuitive for shape.

## Draw a Histogram in Python

```python
import matplotlib.pyplot as plt

scores = [45, 52, 58, 61, 63, 67, 70, 72, 75, 78, 80, 82, 85, 88, 92]

plt.hist(scores, bins=[40, 50, 60, 70, 80, 90, 100], edgecolor="black")
plt.title("Histogram of Test Scores")
plt.xlabel("Score")
plt.ylabel("Frequency")
plt.show()
```

## How to Read a Histogram

### 1. Where data is concentrated

Higher bars indicate ranges with many observations.

### 2. How wide data is spread

A wider shape means larger variability.
A narrow concentration means smaller variability.

### 3. Whether extreme values exist

Small bars far from the main group may indicate outliers.

### 4. Whether there is one peak or multiple peaks

One peak suggests one main group.
Two peaks may suggest mixed subgroups.

## Business Use Cases

### Purchase amount distribution

- Are most customers low spenders?
- Are high spenders a small segment?
- Is the mean inflated by a few large customers?

### Inquiry handling time distribution

- Are most inquiries solved quickly?
- Are only a few inquiries taking very long?
- How unstable is handling time?

### Test score distribution

- Is understanding generally good?
- Is there polarization?
- How large is the group needing support?

## What Mean Alone Cannot Show

Two classes can have similar means but very different learning states.

```text
Class A: most students around the mean
Class B: split into high and low groups
```

So data analysis should include distribution shape, not only mean.

## Summary

- Frequency table counts values by ranges
- Histogram visualizes the frequency table
- Frequency is the count in each class
- Class is a grouping interval
- Class width affects readability and detail
- Histogram reveals concentration and spread
- Mean alone cannot represent distribution shape
- In business, this applies to sales, behavior, response time, and more

Next chapter: scatter plot and correlation.
