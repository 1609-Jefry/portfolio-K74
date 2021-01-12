# Datasets

---

[FeatureAddition-MachineLearning.pdf](Datasets%20e581ab49c64e4a8886f347acd0ecb45c/FeatureAddition-MachineLearning.pdf)

For the testing we used a standardized testing method. Which also required a standardized dataset so every model could be compared easier.

In this notebook there's happing a ton of feature extraction since the only features that are going in are the datetime-index, the irradiance, and the production or consumption.

Added features are:

- Hours [One-Hot]
- Weekday [One-Hot]
- Shifting of the consumption of production for 24-168 hours before.
- The mean of the past day
- The mean of the past week

These were then saved as a pickle and read into the testing notebook.

### Skills:

- One hot encoding of a variable
- Using pandas
    - Reading files
    - Merging dataframes
- Shifting variables in time
- Calculating the average of a time-frame and adding that to the corresponding rows