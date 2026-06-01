# 01 Probability and Trials

## नेपाली

यस अध्यायमा probability र trial सिकिन्छ।

Probability ले एक पटकको नतिजा ठ्याक्कै भविष्यवाणी गर्दैन।
यो एउटै अवस्था धेरै पटक दोहोर्याउँदा देखिने प्रवृत्ति बुझ्ने उपकरण हो।

## उद्देश्य

- Probability के हो बुझ्ने
- Trial के हो बुझ्ने
- एक पटकको नतिजा र दोहोरिएको प्रवृत्ति फरक हो भन्ने बुझ्ने
- Probability र वास्तविक नतिजा सधैं उस्तै हुँदैन भन्ने बुझ्ने
- Trial बढ्दा प्रवृत्ति स्पष्ट देखिने कुरा बुझ्ने
- Python बाट simulation गर्ने

## Probability के हो?

Probability भनेको कुनै घटना हुने सम्भावना कति छ भन्ने संख्या हो।

10% probability भएको चिठ्ठामा, 1 पटक तानेर 0.1 पटक जित्ने भन्ने अर्थ हुँदैन।
१ पटकको नतिजा जित वा हार मात्र हुन्छ।

10% भन्नाले धेरै पटक दोहोर्याउँदा समग्र जित अनुपात 10% नजिक जाने प्रवृत्ति हो।

## Trial के हो?

एउटै सर्तमा गरिएको 1 प्रयोगलाई trial भनिन्छ।

उदाहरण:
- 1 पटक चिठ्ठा तान्नु
- 1 पटक पासा फाल्नु
- 1 प्रयोगकर्ताले page हेर्नु
- 1 email पठाउनु
- 1 पटक विज्ञापन देखाउनु

## 10% चिठ्ठा उदाहरण

१ पटक तानेपछि परिणाम:
- जित
- हार

तर धेरै पटक तान्दा (100, 1000, 10000) जितको अनुपात 10% नजिक जान्छ।

## 10 पटकमा कम्तीमा 1 पटक जित्ने सम्भावना

यी दुई कुरा फरक हुन्:
- 1 पटक जित्ने सम्भावना 10%
- 10 पटकमा कम्तीमा 1 पटक जित्ने सम्भावना 10% होइन

पूरक घटना प्रयोग गर्दा सजिलो हुन्छ:

```text
P(कम्तीमा 1 जित) = 1 - P(10 पटक सबै हार)
P(10 पटक सबै हार) = 0.9^10 = 0.3486784401
P(कम्तीमा 1 जित) = 1 - 0.9^10 = 0.6513215599
```

यसलाई करिब 65% भनेर बुझ्न पर्याप्त हुन्छ।

## Python उदाहरण

```python
import random

if random.random() < 0.1:
    print("win")
else:
    print("lose")
```

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
plt.show()
```

## व्यवसायसँग सम्बन्ध

एउटा नतिजाबाट मात्र निर्णय गर्नु जोखिमपूर्ण हुन्छ।
धेरै trial र data जम्मा गरेर समग्र प्रवृत्ति हेर्नुपर्छ।

## सारांश

- Probability ले सम्भावना देखाउँछ
- एक पटकको नतिजा र दीर्घ प्रवृत्ति फरक हुन्छ
- Trial कम हुँदा fluctuation धेरै हुन्छ
- Trial बढ्दा प्रवृत्ति स्पष्ट हुन्छ
- Python ले probabilistic घटना simulation गर्न सहयोग गर्छ
