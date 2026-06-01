# 00_environment

## नेपाली

यस अध्यायमा, यो सामग्री पढ्न आवश्यक हुने अध्ययन वातावरण जाँचिन्छ।

लक्ष्य कठिन सेटअप गर्नु होइन।
Python र spreadsheet प्रयोग गरेर data सम्हाल्न तयार भएको अवस्था बनाउनु हो।

---

## यस अध्यायका उद्देश्य

यस अध्यायमा, यी कुरा जाँचिन्छन्:

- Python चलाउन सकिने
- Spreadsheet tool प्रयोग गर्न सकिने
- सरल गणनाको नतिजा देखाउन सकिने
- Random number बनाउन सकिने
- Graph देखाउन सकिने

---

## प्रयोग हुने उपकरण

यो सामग्रीमा मुख्य रूपमा:

- Python
- Google Colab वा Jupyter Notebook
- Excel वा Google Sheets
- आवश्यक परे matplotlib
- आवश्यक परे pandas

सुरुमै सबै कुरा पूर्ण रूपमा जान्न आवश्यक छैन।
पहिले चल्छ कि चल्दैन भन्ने जाँच गर्नु नै लक्ष्य हो।

---

## न्यूनतम जाँच

### 1. Python चल्ने जाँच

```python
print("Hello, Business Statistics")
```

```text
Hello, Business Statistics
```

### 2. सरल गणना जाँच

```python
price = 1000
tax_rate = 0.1

total = price + price * tax_rate

print(total)
```

### 3. Random number जाँच

```python
import random

number = random.random()
print(number)
```

`random.random()` ले 0 भन्दा ठूलो वा बराबर र 1 भन्दा सानो मान फिर्ता गर्छ।

### 4. Graph जाँच

```python
import matplotlib.pyplot as plt

values = [1, 2, 3, 4, 5]
counts = [2, 4, 6, 8, 10]

plt.bar(values, counts)
plt.show()
```

---

## Spreadsheet जाँच

Excel वा Google Sheets मा यी आधारभूत काम गर्न सकिन्छ कि जाँच्नुहोस्:

- तालिका बनाउने
- गणना गर्ने
- ग्राफ बनाउने

Python र spreadsheet दुवै data अवलोकनका उपकरण हुन्।

---

## AlmaLinux मा वातावरण जाँच

AlmaLinux प्रयोग गर्दा यी कमाण्ड चलाउनुहोस्:

```bash
python3 -V
sudo dnf install python3-pip
python3 -m pip --version
python3 -m pip install --user ipykernel
python3 -m ipykernel install --user --name python3 --display-name "Python 3"
```

- `python3 -V`: Python version जाँच
- `python3 -m pip --version`: pip उपलब्ध छ कि जाँच
- `ipykernel` इन्स्टल गरेर Jupyter मा `Python 3` kernel प्रयोगयोग्य बनाउने

---

## सारांश

यस अध्यायमा business statistics सिक्न आवश्यक वातावरण जाँच गरियो।

अर्को अध्यायबाट probability र trials सुरु हुन्छ।
