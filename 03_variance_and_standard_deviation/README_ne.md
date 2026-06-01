# 03 Variance and Standard Deviation

## नेपाली

यस अध्यायमा average मात्रले नदेखिने data को spread (variability) सिकिन्छ।

उदाहरण:

```text
A: 48, 49, 50, 51, 52
B: 10, 30, 50, 70, 90
```

दुवैको average 50 हो, तर spread फरक छ।

## Average मात्र किन पर्याप्त हुँदैन

व्यवसायमा center मात्र होइन stability पनि महत्त्वपूर्ण छ:
- दैनिक बिक्री स्थिर छ कि छैन
- आगन्तुक संख्या धेरै उतारचढावमा छ कि छैन
- कामको समय consistent छ कि छैन

## Deviation

Deviation भनेको data value र mean बीचको फरक हो।

```text
deviation = value - mean
```

Deviation सिधै जोड्दा plus/minus cancel भएर 0 नजिक आउँछ।

## Variance

त्यसैले deviation लाई square गरेर average लिइन्छ।
त्यसलाई variance भनिन्छ।

## Standard deviation

Variance square unit मा हुन्छ, त्यसैले कम intuitive हुन्छ।
Variance को square root नै standard deviation हो।

## Python उदाहरण

```python
data = [40, 50, 60]

mean = sum(data) / len(data)
deviations = [x - mean for x in data]
squared = [d ** 2 for d in deviations]
variance = sum(squared) / len(data)
std = variance ** 0.5

print(mean, deviations, variance, std)
```

## NumPy उदाहरण

```python
import numpy as np

data = [40, 50, 60]
print(np.mean(data))
print(np.var(data))
print(np.std(data))
```

## व्यवसायिक अर्थ

एउटै average भएको दुई पसलको जोखिम स्तर फरक हुन सक्छ।
Standard deviation ले stability र risk बुझ्न मद्दत गर्छ।

## सारांश

- Average ले center देखाउँछ
- Variance/standard deviation ले spread देखाउँछ
- एउटै average भए पनि data को अवस्था एउटै हुँदैन
- व्यवसायिक निर्णयमा center र variability दुवै हेर्नुपर्छ
