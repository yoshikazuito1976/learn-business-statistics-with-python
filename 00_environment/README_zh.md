# 00_environment

## 中文

本章用于确认学习本教材所需的环境。

目标不是进行复杂的环境搭建，
而是确保你已经可以用 Python 和电子表格工具处理数据。

---

## 本章目标

本章确认以下事项：

- 可以运行 Python
- 可以使用电子表格工具
- 可以输出简单计算结果
- 可以生成随机数
- 可以显示图表

---

## 使用工具

本教材主要使用：

- Python
- Google Colab 或 Jupyter Notebook
- Excel 或 Google Sheets
- 需要时使用 matplotlib
- 需要时使用 pandas

不需要一开始就全部精通。
先确认能够正常运行即可。

---

## 最低运行确认

### 1. Python 运行确认

```python
print("Hello, Business Statistics")
```

```text
Hello, Business Statistics
```

### 2. 简单计算确认

```python
price = 1000
tax_rate = 0.1

total = price + price * tax_rate

print(total)
```

### 3. 随机数确认

```python
import random

number = random.random()
print(number)
```

`random.random()` 返回大于等于 0 且小于 1 的值。

### 4. 图表显示确认

```python
import matplotlib.pyplot as plt

values = [1, 2, 3, 4, 5]
counts = [2, 4, 6, 8, 10]

plt.bar(values, counts)
plt.show()
```

---

## 电子表格工具确认

在 Excel 或 Google Sheets 中，确认可以完成以下基本操作：

- 制作表格
- 统计数量
- 绘制图表

Python 与电子表格都是观察数据的工具。

---

## AlmaLinux 环境确认

如果使用 AlmaLinux，请按顺序执行：

```bash
python3 -V
sudo dnf install python3-pip
python3 -m pip --version
python3 -m pip install --user ipykernel
python3 -m ipykernel install --user --name python3 --display-name "Python 3"
```

- `python3 -V`：确认 Python 版本
- `python3 -m pip --version`：确认可使用 pip
- 安装 `ipykernel`，使 Jupyter 可使用 `Python 3` 内核

---

## 小结

本章完成了学习商业统计所需环境的确认。

下一章开始进入概率与试验。
