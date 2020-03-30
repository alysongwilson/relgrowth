---
author: Alyson Wilson
date: "2020-03-23"
description: Basics of DoD Test and Evaluation
image: images/dataev.jpg
image_webp: images/dataev.webp
title: Repairable Systems
---

It is important to distinguish two cases for reliability models and data. The first is for systems or components that are *nonrepairable*, where the system is discarded after failure. In this case, we are interested in the time of failure for each system. An example of a nonrepairable system is a ``one-shot'' device, like a light bulb, which is completely replaced upon failure. These data are often modeled as arising from a single failure-time distribution, or from a distribution that depends on explanatory variables, like the manufacturer, environment, and operating conditions. 

The second case is for *repairable* systems, which can be restored to an operating condition by some process other than replacement of the entire system after failure. Examples of repairable systems include cars and airplanes, where failures are followed by repairs. The data consist of a sequence of failure times for one or more systems. The distribution of time to the next failure depends on the state of the system and on the nature of the repairs. 

Reliability growth models are based on models for repairable systems. The two most common types of reliability growth models used by the DoD for continuous data are (1) system-level models using nonhomogeneous Poisson processes and (2) competing risk models where multiple failure modes are operating in series.

For nonrepairable systems, we observe a single failure time for each system; for repairable systems, however, we observe a number of failures for each system.  

```{r  out.width = "50%"}
include_graphics(images/data.jpg)
```

The figure illustrates the three types of data commonly encountered for repairable systems. The first data are the failure times, $T_{1} < T_{2} < \cdots$ of the system. While these observations frequently have units of time, they may also be measured with other units, including the number of cycles to failure or the number of miles to failure. We can transform these failure times into data on the times between failures, $X_{i} = T_{i} - T_{i-1}$. The failure time data can also be expressed in form of count data: $N([0, t)) = N(t)$, the number of failures within some time interval $[0, t)$. No matter how the failure data are collected, once we have one form of the data, we can easily move among them and derive equivalent statistical models. For example, we can re-express global time data, $t_{1} < t_{2} < \cdots < t_n$, as $N(t_{1}) = 1, N(t_{2}) = 2, \ldots, N(t_n) = n$.

Many repairable systems have an intensity function described as a ``bathtub curve'' like that in the figure. 

```{r  out.width = "50%"}
include_graphics(images/bathtub.jpg)
```

When the system is young, failures are frequent; as problems are found and corrected, the failure intensity is smaller; as the system ages, failures become more and more common as the system wears out. The bathtub curve is identical to the curve that describes the hazard function ($h(t) = \frac{f(t)}{1 - F(t)}$) for many nonrepairable systems. However, the interpretations are different. The hazard function for a nonrepairable system is the limit of the probability that a system fails (for the only time) in a small interval given that it survived to the beginning of the interval.

