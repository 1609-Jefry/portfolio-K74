# Preprocessing&Exploration

[W14_DataPreprocessing-Copy7.pdf](Preprocessing&Exploration%20f1ddb0f73ad449f0a3cacdbee3021e83/W14_DataPreprocessing-Copy7.pdf)

When trying to collect every single preprocessing step in one notebook we found some problems with the consumption data, which I tried to find the cause of (I was unsuccessful). The steps I took are found in that notebook and some will be highlighted below!

![Preprocessing&Exploration%20f1ddb0f73ad449f0a3cacdbee3021e83/Untitled.png](Preprocessing&Exploration%20f1ddb0f73ad449f0a3cacdbee3021e83/Untitled.png)

The consumption (smartmeter) shouldn't be able to reach a value that's lower than exactly 0.

The formula to calculate the consumption is:

$Energy_{consumption}= smart_{in} + [solar_{out}-smart_{out}]$

That would mean that the energy being sold to the net (smart_out) would be higher than the energy being produced by the solar panels (solar_out), which should be the only power source.

### Time gaps:

![Preprocessing&Exploration%20f1ddb0f73ad449f0a3cacdbee3021e83/Untitled%201.png](Preprocessing&Exploration%20f1ddb0f73ad449f0a3cacdbee3021e83/Untitled%201.png)

![Preprocessing&Exploration%20f1ddb0f73ad449f0a3cacdbee3021e83/Untitled%202.png](Preprocessing&Exploration%20f1ddb0f73ad449f0a3cacdbee3021e83/Untitled%202.png)

A small summary of the time gap exploration

```python
solar
Mean of timestamps in solar: 300.1599912432659
Standard Deviation timestamps of solar: 17.276597542275262

The amount of timestamp gaps significantly (2*std) above 5 minutes: 	34
Solar peaks:
solar peaks above 600: 15
```

### Peaks of timegaps (indicating missing data)

Showcasing two of the peaks in the two datasets (solar and smartMeter) that fell almost on the same moment, to see if there's a correlation.

![Preprocessing&Exploration%20f1ddb0f73ad449f0a3cacdbee3021e83/Untitled%203.png](Preprocessing&Exploration%20f1ddb0f73ad449f0a3cacdbee3021e83/Untitled%203.png)

### Cleaning

```python
204 values were set to 0
Which is 0.19% of the dataset
The area under consumption = 5089.9 kWh 
The area under production = 7464.21 kWh
```

Since a small amount of the data is actually negative, the team decided to just change them to 0.