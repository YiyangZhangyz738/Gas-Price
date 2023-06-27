# NFT Transaction Fee：Analysis of the Impact of the London Upgrade on the stability of Gas Fee
## Project information
- **Author**: Yiyang Zhang, Computation and Design with tracks in Digital Media, Class of 2025, Duke Kunshan University
- **Instructor**: Prof. Luyao Zhang, Duke Kunshan University
- **Disclaimer**: SRS program instructed by Prof. Luyao Zhang at Duke Kunshan University.
- **Acknowledgments**: Thanks to Professor Luyao Zhang for guiding my project. Thanks to the SciEcon editorial team including Xintong Wu, Wanlin Deng, Xinyu Tian, Zesen Zhuang, Prof. Luyao Zhang. Thanks to Yu Wang for giving me emotional support and encouragement.
- **Project Summary**: 
  - [Summarize the Background/Motivation]The Non-Fungible Token (NFT) market has experienced tremendous growth and popularity in recent years, attracting artists, collectors, and investors alike. However, one of the challenges facing this market is the volatility of transaction fees, which can fluctuate greatly depending on network congestion and gas price dynamics. Such price fluctuations pose a barrier to the development of a more stable and predictable NFT market. Previous research in the field has predominantly focused on predicting gas price changes using various modeling techniques. While these studies have provided valuable insights into understanding gas price, there is a gap in the literature regarding the examination of gas price stability specifically in the context of the London Upgrade and its impact on the NFT market.
By studying the gas price data before and after the implementation of the London Upgrade, we aim to analyze the changes in gas price standard deviation as a measure of gas price stability. This analysis will provide insights into the impact of the London Upgrade on the stability of gas fee. Furthermore, we will explore the potential implications of gas price stability on the NFT market’s transaction fees. A more stable gas price environment could contribute to reducing the price volatility associated with NFT transactions, making it more attractive for market participants and facilitating smoother operations within the NFT ecosystem.

  - [Research Questions] How does the London Upgrade affect the stability of gas fees?
  - [Application Scenario (Data Source)] https://etherscan.io/chart/gasprice
  - [Methodology]
  - Standard deviation
   - For the collected data of the daily average gas price used of the Ethereum network, I calculated the standard deviation of its data from seven days ago to the current day at a daily frequency. The value of standard deviation reflects the degree of dispersion of the data. The smaller the fluctuation of the data and the smaller the degree of dispersion, the higher the stability. So I use the standard deviation of the daily average gas price used of the Ethereum network to measure the stability of the gas price.

   - Linear regression analysis
For the standard deviation of the daily average gas price used of the Ethereum data set, this exploratory research conducts linear regression analysis. The first half of the data is used to train the linear regression model, and the first half of the data is used to verify the degree of fitting between the predicted data generated by the model and the real data. If the degree of fitting between the predicted data and the real data is low, it indicates that the London Upgrade has a significant impact on the standard deviation of the daily average gas price used of the Ethereum. On the contrary, the effect is not significant.

   - Causal inference research design
In this exploratory research, the standard deviation of the daily average gas price used of the Ethereum was analyzed by regression discontinuity design network data from July 30, 2015 to June 23, 2023, including data before and after the London Upgrade. If you don't consider the London Upgrade, the standard deviation of the daily average gas price used of the Ethereum network. It should steadily increase according to the original trend, that is, the stability of the gas price will decrease. But given the  London Upgrade in August 5, 2021 the standard deviation of the daily average gas price used of the Ethereum network was expected to turn around and gradually decline because of this event. But it won't go to zero. This means that the London Upgrade is expected to contribute to increasing the stability of the gas price in this exploratory research.

  - [Results] We accept the predictions in the study design that the London Upgrade to the standard deviation of the daily average gas price used of the Ethereum There are negative effects, that is, the London Upgrade contributes to increasing the stability of the gas price in this exploratory research.

  - [Intellectual Merits and Practical impacts of your project.] The research explores the impact of the London Upgrade on the stability of gas fees in the Ethereum network and its potential implications for the NFT market. By analyzing the standard deviation of the daily average gas price before and after the upgrade, the study finds that the London Upgrade contributes to increasing the stability of gas fees. The innovation of this research lies in its specific focus on examining the impact of the London Upgrade on the stability of gas fees in the context of the NFT market.


## Table of Contents
- [Data](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/README.md#data)
- [Code](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/README.md#code)
- [Spotlight](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/README.md#spotlight)
- [More about the author](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/README.md#more-about-the-author)
- [References](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/README.md#references)
- [GitHub Page](https://github.com/YiyangZhangyz738/Gas-Price/tree/main)



## Data
- Data Source: https://etherscan.io/chart/gasprice
- Meta Data Infomation:

| Data Files | Data Type | Data Content |
| ----- | ----- | ----- | 
|  [GasPrice.csv](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/data/Queried_Data/GasPrice.csv) | Queried | the daily average gas price used of the Ethereum network | 
| [GP.csv](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/data/Queried_Data/GP.csv) |  Processed | arranged average gas price used of the Ethereum network |
| [GPR.csv](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/data/Processed_Data/GPR.csv) | Processed |the standard deviation of the daily average gas price used of the Ethereum network |
| [Regression_Train.csv](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/data/Processed_Data/Regression_Train.csv) | Processed | Training data for regression | 
| [Regression_Test.csv](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/data/Processed_Data/Regression_Test.csv) | Processed | Testing data for regression | 

- Data Dictionary
- 
| File Name | Variable Name | Description | Frecuency | Unit | Type |
| ----- | ----- | ----- | ----- | ----- | ----- |
| [GasPrice.csv](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/data/Queried_Data/GasPrice.csv)  | Date(UTC) | date of data collected | daily | day | datetime |
|  | UnixTimeStamp | UnixTimeStamp of data collected | daily | None | Timestamp |
|  | Value (Wei) | the daily average gas price used of the Ethereum network | daily | Wei | int |
| [GP.csv](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/data/Queried_Data/GP.csv) | Date(UTC) | date of data collected | daily | day | datetime |
|  | UnixTimeStamp | UnixTimeStamp of data collected | daily | None | Timestamp |
|  | Value (Wei) | the daily average gas price used of the Ethereum network | daily | Wei | int |
| [GPR.csv](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/data/Processed_Data/GPR.csv)  |  Date | date of data collected | daily | day | datetime |
|  | Rate | the standard deviation of the daily average gas price used of the Ethereum network | daily | None | float |
| [Regression_Train.csv](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/data/Processed_Data/Regression_Train.csv) | theta | the daily average gas price used of the Ethereum network | daily | None | float |
|  | theta_past_ma10 | average standard deviation of past 10 days | daily | None | float |
| [Regression_Test.csv](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/data/Processed_Data/Regression_Test.csv) | theta | the daily average gas price used of the Ethereum network | daily | None | float |
|  | theta_past_ma10 | average standard deviation of past 10 days | daily | None | float |

## Code
- Prediction Code Source: https://github.com/Rising-Stars-by-Sunshine/stats201-tutorial-prediction

- Causal Event Certification Code Source: https://numpy.org/doc/stable/reference/generated/numpy.polyfit.html

| Prediction | Causal Inference |
| ----- | ----- | 
|  [Process_Data_Prepare_X_and_Y_for_Classification_and_Regressions.ipynb](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/code/Process_Data_Prepare_X_and_Y_for_Classification_and_Regressions.ipynb)  | [Query_Data.ipynb](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/code/Query_Data.ipynb) |
| [Analyze_Data_Machine_Learning_for_Predicting_Market_Congestion_ipynb.ipynb](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/code/Analyze_Data_Machine_Learning_for_Predicting_Market_Congestion_ipynb.ipynb) | [Process_Data.ipynb](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/code/Process_Data.ipynb) |
|  | [Analyze_Data.ipynb](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/code/Analyze_Data.ipynb) | 

## Spotlight
- Prediction
  
![image](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/spotlight/figures/Linear%20Regression.png)
### Figure No.1. Linear regression prediction histogram of the stability of Gas Fee
The figure above uses the linear regression prediction method in machine learning and is obtained by collecting the standard deviation of the daily average gas price used of the Ethereum data. The blue section represents the real data and the green section represents the data predicted by linear regression. It can be noted that the predicted data in the first half of the horizontal coordinate is larger than the actual data. In other words, the predicted value is greater than the actual predicted value, and the actual standard deviation of the daily average gas price is significantly reduced due to the impact of the event.

- Causal Inference Research Design

![image](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/spotlight/figures/Causal%20Inference%20Research%20Design.png)
### Figure No.2. Causal Inference Research Design
In this exploratory research, the standard deviation of the daily average gas price used of the Ethereum was analyzed by regression discontinuity design network data from July 30, 2015 to June 23, 2023, including data before and after the London Upgrade. If you don't consider the London Upgrade, the standard deviation of the daily average gas price used of the Ethereum network. It should steadily increase according to the original trend, that is, the stability of the gas price will decrease. But given the  London Upgrade in August 5, 2021 the standard deviation of the daily average gas price used of the Ethereum network was expected to turn around and gradually decline because of this event. But it won't go to zero. This means that the London Upgrade is expected to contribute to increasing the stability of the gas price in this exploratory research.

- Causal Inference

![image](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/spotlight/figures/Casual%20Inference.png)
### Figure No.3. Result
The blue broken line in the figure above represents the actual change in the standard deviation of the daily average gas price used of the Ethereum. The solid red line is the linear regression fitting line of the standard deviation of the daily average gas price before the London Upgrade, while the dotted line in red is an extension of this line after the London Upgrade. The dark blue straight line is a linear regression fit for the standard deviation of the daily average gas price after the London Upgrade. The grey vertical dotted line represents the London Upgrade on August 5, 2021.
By observing the two linear regression fitting lines, it can be judged that after the London Upgrade event, the standard deviation of the daily average gas price used of the Ethereum The trend has changed from upward to downward. This is consistent with the predictions in the study design. So we accept the predictions in the study design that the London Upgrade to the standard deviation of the daily average gas price used of the Ethereum There are negative effects, that is, the London Upgrade contributes to increasing the stability of the gas price in this exploratory research.

## More about the Author

![image](https://github.com/YiyangZhangyz738/Gas-Price/blob/main/headshot.jpeg)
- Yiyang Zhang is from the class of 2025, majoring in Computation and Design with tracks in Digital Media at Duke Kunshan University. She is designated a Summer Research Scholar for the summer of 2023 and awarded by the SRS program. Her research interest is NFT transaction, digital design, and media interaction. 

## References

### Data Source
- https://etherscan.io/chart/gasprice
### Code Source
- https://github.com/Rising-Stars-by-Sunshine/stats201-portfolio
- https://github.com/sunshineluyao/design-principle-blockchain

### Literature
“Gas and Fees.” 2023. Ethereum.org. May 31, 2023. https://ethereum.org/en/developers/docs/gas/.
‌Kasireddy, Preethi. 2019. “How Does Ethereum Work, Anyway?” Medium. October 29, 2019. https://preethikasireddy.medium.com/how-does-ethereum-work-anyway-22d1df506369.
‌Parham, Arsalan, and Corinna Breitinger. 2022. “Non-Fungible Tokens: Promise or Peril?,” February. https://doi.org/10.48550/arxiv.2202.06354.
‌Pierro, Giuseppe Antonio, and Henrique Rocha. 2019. “The Influence Factors on Ethereum Transaction Fees.” 2019 IEEE/ACM 2nd International Workshop on Emerging Trends in Software Engineering for Blockchain (WETSEB), May, 24–31. https://doi.org/10.1109/wetseb.2019.00010.

- Zhang, Luyao (Sunshine). 2022. “Machine Learning for Causal Inference.” Machine Learning for Social Science, November. https://ms.pubpub.org/pub/causal-inference/release/8.
- Zhang, Luyao (Sunshine), Zesen Zhuang, and Xinyu (Michelle) Tian. 2022. “Machine Learning for Predictions.” Machine Learning for Social Science, November. https://ms.pubpub.org/pub/ml-prediction/release/4.
