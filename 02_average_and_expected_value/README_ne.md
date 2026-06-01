# 02 Average and Expected Value

## नेपाली

यस अध्यायमा average र expected value सिकिन्छ।

## उद्देश्य

- Average के हो बुझ्ने
- Expected value के हो बुझ्ने
- Expected value भनेको निश्चित परिणाम होइन भन्ने बुझ्ने
- Probability x प्रयास संख्या प्रयोग गरेर औसत नतिजा अनुमान गर्ने
- Python simulation मार्फत पुष्टि गर्ने
- व्यवसायिक निर्णयसँग जोड्ने

## Average

Average ले धेरै संख्याको प्रतिनिधि मान दिन्छ।

```text
2, 4, 6, 8, 10
(2 + 4 + 6 + 8 + 10) / 5 = 6
```

Average उपयोगी भए पनि, एक्लै पर्याप्त नहुन सक्छ।

## Expected value

Expected value भनेको अनिश्चित घटनालाई धेरै पटक दोहोर्याउँदा देखिने औसत परिणाम हो।

10% जित सम्भावना भएको चिठ्ठा 10 पटक तानेमा:

```text
10 x 0.1 = 1
```

औसत जित 1 हुन सक्छ, तर एक पटकको सेटमा यो अनिवार्य होइन।

## ठोस उदाहरणहरू

1. विज्ञापन क्लिक: 100 x 0.05 = 5
2. बिक्री रूपान्तरण: 30 x 0.1 = 3
3. सोधपुछ समय: 20 x 12 = 240 मिनेट
4. बिक्री अनुमान: 100 x 3000 = 300000
5. गाचा/चिठ्ठा: 100 x 0.02 = 2
6. अनुपस्थिति अनुमान: 40 x 0.05 = 2
7. खराब उत्पादन: 1000 x 0.01 = 10

यी सबै औसत अनुमान हुन्, निश्चित नतिजा होइनन्।

## Python simulation

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

print(sum(results) / len(results))
```

## व्यवसायिक अर्थ

Average र expected value ले योजना बनाउन मद्दत गर्छ:
- क्लिक अनुमान
- रूपान्तरण अनुमान
- समय अनुमान
- बिक्री अनुमान

तर average मात्र हेरेर निर्णय गर्न मिल्दैन।
डेटाको variability पनि हेर्नुपर्छ।

## सारांश

- Average प्रतिनिधि मान हो
- Expected value अनिश्चित घटनाको औसत अनुमान हो
- Expected value एक पटकको नतिजाको ग्यारेन्टी होइन
- एउटै average भए पनि data pattern फरक हुन सक्छ
