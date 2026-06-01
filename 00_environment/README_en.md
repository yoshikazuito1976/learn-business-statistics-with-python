# 00_environment

## English

In this chapter, you check the learning environment required for this course.

The goal is not difficult setup work.
The goal is to make sure you are ready to work with data using Python and spreadsheet tools.

---

## Objectives

In this chapter, you confirm that:

- You can run Python
- You can use a spreadsheet tool
- You can display simple calculation results
- You can generate random numbers
- You can display graphs

---

## Tools

This course mainly uses:

- Python
- Google Colab or Jupyter Notebook
- Excel or Google Sheets
- matplotlib (as needed)
- pandas (as needed)

You do not need to master everything at the beginning.
First, confirm that your environment works.

---

## Minimum checks

### 1. Run Python

```python
print("Hello, Business Statistics")
```

```text
Hello, Business Statistics
```

### 2. Simple calculation

```python
price = 1000
tax_rate = 0.1

total = price + price * tax_rate

print(total)
```

### 3. Random number generation

```python
import random

number = random.random()
print(number)
```

`random.random()` returns a value in [0, 1).

### 4. Graph display

```python
import matplotlib.pyplot as plt

values = [1, 2, 3, 4, 5]
counts = [2, 4, 6, 8, 10]

plt.bar(values, counts)
plt.show()
```

---

## Spreadsheet check

In Excel or Google Sheets, confirm basic operations:

- Create a table
- Count records
- Create a chart

Both Python and spreadsheets are tools for observing data.

---

## Environment check on AlmaLinux

If you use AlmaLinux, run:

```bash
python3 -V
sudo dnf install python3-pip
python3 -m pip --version
python3 -m pip install --user ipykernel
python3 -m ipykernel install --user --name python3 --display-name "Python 3"
```

- `python3 -V`: check Python version
- `python3 -m pip --version`: confirm pip is available
- Install `ipykernel` so Jupyter can use the `Python 3` kernel

---

## Summary

In this chapter, you confirmed the environment for learning business statistics.

From the next chapter, you start probability and trials.
