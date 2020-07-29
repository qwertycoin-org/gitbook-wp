---
description: Last Updated 2020-07-23
---

# Difficulty Algorithm - CIMA \(Confidence Interval Moving Average\)

CIMA stands for Confidence Interval Moving Average. This difficulty algorithm\('DA', hereinafter\) takes the basic form of moving average techniques in statistics. Normally 95%-98% confidence interval is chosen for statistical analysis. 

The percentage figure used in CI stands for the range of distributions of the values, which are normally within the confidence interval range from a mean value of the sample population. The percentage value does not necessarily represent that the future samples are likely to be within that specific interval range.

![A bell-shaped distribution curve diagram with confidence interval from Wikipedia](../../../.gitbook/assets/normal_distribution_and_scales.gif)

QWC's CIMA DA currently uses a 68% confidence interval and this selection of 68% CI to allow DA to adjust more quickly from valid sample data.

Within a range of 30 block time, equivalent to 1 hour, a sample mean\(1\), and the standard deviation is calculated.

We filter out those samples with a value that lies outside of mean +/- the standard deviation range. We treat those values outside of the 68% CI as outliers.

We then re-calculate the mean\(2\) of the filtered samples. We consider this mean\(2\) a true mean value. If the values of the samples are within a range we consider 'consistent'\(remember we used the notion of consistency in our reward algorithm\), the difficulty for the next block will stay the same.

In other cases, by comparing mean\(1\) and mean\(2\), the algorithm decides whether to increase or decrease the difficulty for the next block.

With CIMA and Consistency, QWC blockchain is bulletproof against the majority attacks and protects the network from any malicious intents. 

 

