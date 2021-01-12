# Paper parts

# PDF-files

[K74_Introduction.pdf](Paper%20parts%20f6103c42afff4e6cbb44f0e474144bf4/K74_Introduction.pdf)

[K74_Results.pdf](Paper%20parts%20f6103c42afff4e6cbb44f0e474144bf4/K74_Results.pdf)

# Introduction

In recent years, the European Commission has set the ambitious goal of reducingthe impact of global warming with the Paris agreement. In the agreementall participating nations are expected to release their Nationally Determined Contributions (NDCs) by 2020 [2]. The Netherlands has released their NDC in November 2019 in which the plans for the coming 30 years are presented. The Netherlands has set a goal of reducing the CO2 emission, relative to 1990, with49% by 2030 and with 80-95% by 2050 [3]. Electricity makes up around 26%of the energy-wise CO2 emissions. In 2015 the portion of renewable energy of the electricity consumption was circa 12%. As a result of the reduction of CO2emissions this percentage will increase to circa 41% by 2023. This is achieved by increasing the production of energy with sources that are low in CO2 emissions. One of the ways to achieve that is to create more Nearly Zero-Energy Buildings (nZEBs). These buildings are isolated better and use a low in CO2 energy source as their main power source. They are still connected to the main grid to sell and buy energy in case the supply is more or less than required. At the this point in time nZEBs sell their surplus of energy to the net ata profit. In the near future this will not be as straightforward. As the energy demand is increasing, the load of the grid is as well. Meaning that the energy providers will deal out fines for overloading the net by selling energy at points of high energy traffic[1].To be able to keep nZEBs profitable they need to automate their buying and selling moments. To achieve this, the prediction of energy consumption and energy production is essential. Earlier research has been conducted to predict the energy consumption of commercial buildings[1]; however individual housing has not gotten the same amount of research put into it yet. This could be caused by the complications resulting from the privacy sensitivity of gaining data from residential houses[4]. Recently more research is being conducted on the prediction of residential housing energy consumption and production [5] [6]. They do this because...

> What is a suitable model to predict energy consumption and production of an nZEB, one day in advance with hourly resolution?

Multiple machine learning models (SVR, MVLR, MLP & LSTM) have been tested to evaluate their performance in forecasting the energy production and consumption of nZEBs. These models have been using data from 120 nZEB row-houses located in South-Holland. Data will be explained in a new chapter called Data.

References

[1]  Source to be determined.

[2]  Paris agreement.1

[3]  Rijksoverheid.  Energieagenda:  Naar een co-arme energievoorziening.

[4]  Constance Douris. BALANCING SMART GRID DATA AND CONSUMERPRIVACY.  page 24.

[5]  Mohammad Azhar Mat Daut, Mohammad Yusri Hassan, Hayati Abdullah,Hasimah Abdul Rahman, Md Pauzi Abdullah, and Faridah Hussin. Buildingelectrical  energy  consumption  forecasting  analysis  using  conventional  andartificial intelligence methods:  A review.  70:1108–1118.

[6]  etc.

# 3 Results

The results were determined by running the 4 models on 12 randomly chosen houses from a list of houses that have the lowest number of one-hour gaps. After each model was run on these houses the average of the metrics MAE, MSE, MAPE and $R^2$ was calculated and shown the corresponding table.

## Consumption

The results in Table 3 show that the LSTM overall outperforms the other models at predicting consumption. The same table concludes that SVR performs the worst overall.

Table 3 Consumption Model Results

[Untitled](Paper%20parts%20f6103c42afff4e6cbb44f0e474144bf4/Untitled%20Database%20c7c579b1821e4077b5fa8cb248db7635.csv)

In  Figure 1 the four models for consumption are shown in combination with the ground truth. The LSTM again is closest to predicting the timing and height of the peaks, as well as the mean of the data.

![Paper%20parts%20f6103c42afff4e6cbb44f0e474144bf4/Untitled.png](Paper%20parts%20f6103c42afff4e6cbb44f0e474144bf4/Untitled.png)

The MLP seems to perform the worst out of these models when it was the second worst according to Table 3.

## Production

The results in Table 4 show that the SVR is performing the best overall at predicting the production. The MLP performs the worst overall.

Table 4 Production Model Results

[Untitled](Paper%20parts%20f6103c42afff4e6cbb44f0e474144bf4/Untitled%20Database%20f7d021614c574e6bb15f778927c1da12.csv)

In Figure 2 the four models for production are shown in combination with the ground truth. The SVR shows the lowest percentage of negative production predictions which results in the SVR having better predictions at night than the other models. The LSTM seems to perform better at predicting the shape of the production during the day, however the LSTM predicts negative production during the night.

![Paper%20parts%20f6103c42afff4e6cbb44f0e474144bf4/Untitled%201.png](Paper%20parts%20f6103c42afff4e6cbb44f0e474144bf4/Untitled%201.png)

The MLP seems to perform the worst out of these models which corresponds to the results of Table 4.