# 04 Histogram and Distribution

## अध्यायको उद्देश्य

यस अध्यायमा data को distribution कसरी हेर्ने भन्ने सिकिन्छ।

Average र standard deviation उपयोगी भए पनि average मात्रले data कति फैलिएको छ भन्ने देखाउँदैन।
एउटै average हुँदा पनि data को shape धेरै फरक हुन सक्छ।

- धेरै मान average नजिक जम्मा हुन्छन्
- उच्च र कम मान छुट्टाछुट्टै समूहमा हुन सक्छन्
- केही extreme मानले average माथि तान्न सक्छ

यस अध्यायको अवलोकन प्रवाह:

```text
Raw data
->
Frequency table
->
Histogram
->
Distribution reading
```

## Frequency distribution table के हो?

Data लाई range मा बाँडेर प्रत्येक range मा कति data छ भन्ने तालिका frequency table हो।

```python
scores = [45, 52, 58, 61, 63, 67, 70, 72, 75, 78, 80, 82, 85, 88, 92]
```

## Frequency, class, class width

- Frequency: उक्त range भित्रको data संख्या
- Class: data group गर्ने range
- Class width: class को चौडाइ

Class width धेरै ठूलो भए detail हराउँछ।
धेरै सानो भए overall trend पढ्न गाह्रो हुन सक्छ।

## Python मा frequency table

```python
import pandas as pd

scores = [45, 52, 58, 61, 63, 67, 70, 72, 75, 78, 80, 82, 85, 88, 92]

bins = [40, 50, 60, 70, 80, 90, 100]
labels = [
    "40-<50",
    "50-<60",
    "60-<70",
    "70-<80",
    "80-<90",
    "90-100"
]

groups = pd.cut(scores, bins=bins, labels=labels, right=False)
frequency_table = groups.value_counts().sort_index()
print(frequency_table)
```

## Histogram के हो?

Histogram भनेको frequency table को graph रूप हो।

- Table: exact count हेर्न सजिलो
- Histogram: shape बुझ्न सजिलो

## Python मा histogram

```python
import matplotlib.pyplot as plt

scores = [45, 52, 58, 61, 63, 67, 70, 72, 75, 78, 80, 82, 85, 88, 92]

plt.hist(scores, bins=[40, 50, 60, 70, 80, 90, 100], edgecolor="black")
plt.title("Histogram of Test Scores")
plt.xlabel("Score")
plt.ylabel("Frequency")
plt.show()
```

## Histogram बाट के पढ्ने?

1. Data कहाँ धेरै छ
2. Data कति फैलिएको छ
3. Extreme value छ कि छैन
4. Peak एक हो कि धेरै

## व्यवसायिक प्रयोग

- खरिद रकमको वितरण
- inquiry handle time को वितरण
- test score को वितरण

## Average मात्रले नदेखिने कुरा

एउटै average भएका दुई समूहको distribution फरक हुन सक्छ।
त्यसैले average मात्र होइन, distribution पनि हेर्नुपर्छ।

## सारांश

- Frequency table ले range अनुसार data गन्छ
- Histogram ले उक्त तालिकालाई दृश्य बनाउँछ
- Class width ले detail र readability दुवैमा असर गर्छ
- Histogram ले concentration र spread देखाउँछ
- व्यवसायमा बिक्री, ग्राहक व्यवहार, प्रतिक्रिया समय विश्लेषणमा उपयोगी छ

अर्को अध्याय: scatter plot र correlation.
