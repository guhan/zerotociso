# Exploit Prediction Scoring System (EPSS)

The Exploit Prediction Scoring System (EPSS) is a community-driven effort to combine descriptive information about vulnerabilities (CVEs) with evidence of actual exploitation in-the-wild. By collecting and analyzing these data, EPSS seeks to improve vulnerability prioritization by estimating the likelihood that a vulnerability will be exploited. 

- The EPSS model produces a probability score between 0 and 1 (0% and 100%).
- The higher the score, the greater the probability that a vulnerability will be exploited (in the next 30 days).

![EPSS](/images/EPSS.png)

- **True positives (TP)** are the good decisions – the prioritized vulnerabilities that were exploited in the wild. This is where the blue circle of remediated vulnerabilities overlaps with the exploited vulnerabilities in red.
- **False positives (FP)** are vulnerabilities that were prioritized, but not exploited. These decisions represent potentially wasted resources and are in the blue circle of remediated vulnerabilities that did not overlap with the red circle of exploited vulnerabilities.
- **False negatives (FN)** are vulnerabilities that were not prioritized (and not remediated) but were observed to be exploited in the wild. These are the vulnerabilities in the red circle not being overlapped by the remediated vulnerabilities in the blue circle.
- **True Negatives (TN)** are vulnerabilities not prioritized and not exploited, these are the vulnerabilities in the outer gray circle that were neither remediated nor exploited in the wild.

## Efficiency 
Considers how efficiently resources were spent by measuring the percent of remediated vulnerabilities that were exploited. In the above diagram, efficiency is the amount of the blue circle covered by the red circle. Remediating mostly exploited vulnerabilities would be a high efficiency rating (resources were allocated efficiently), while remediating perhaps random or mostly non-exploited vulnerabilities would result in a low efficiency rating. Efficiency is calculated as the number of exploited vulnerabilities prioritized (TP) divided by the total number of prioritized vulnerabilities (TP+FP).

## Coverage 
The percent of exploited vulnerabilities that were remediated, and is calculated as the number of exploited vulnerabilities prioritized (TP) divided by the total number of exploited vulnerabilities (TP + FN). In the above diagram, coverage is the amount of the red circle covered by the blue circle. Having low coverage indicates that not many of the exploited vulnerabilities were remediated with the given strategy.
