---
layout: project
type: project
image: images/micromouse.jpg
title: Novel Implementation of Chlorophytes and Rhodophytes
permalink: projects/algae
# All dates must be YYYY-MM-DD format!
date: 2020-09-03
labels:
  - Environmental Science
  - Biochemistry
summary: My team developed a robotic mouse that won first place in the 2015 UH Micromouse competition.
---

Algae!

```js
byte ADCRead(byte ch)
{
    word value;
    ADC1SC1 = ch;
    while (ADC1SC1_COCO != 1)
    {   // wait until ADC conversion is completed   
    }
    return ADC1RL;  // lower 8-bit value out of 10-bit data from the ADC
}
```

You can learn more at the [UH Micromouse Website](http://www-ee.eng.hawaii.edu/~mmouse/about.html).



