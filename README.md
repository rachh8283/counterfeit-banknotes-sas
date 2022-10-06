# counterfeit-banknotes-sas
This project uses the banknotes.csv file in SAS to build an appropriate model to predict forgery successfully.

The dataset was uploaded into SAS for mining and analysis. Summary statistics and a graphical summary of histograms are provided, along with a discussion of key aspects of that data. The Winsorization approach, commonly referred to as percentile capping, is used for anomaly detection, and associations are identified using correlation analysis. The hierarchical clustering technique is used in this project to analyze the variables, and the results are explained. A classification model to predict forgeries and reasoning for its use are provided. Finally, the model (isolation forest) is evaluated, and impressions on model fit are reviewed. 

## Key Aspects of Statistical Data
There are two classes identified in the dataset, with 1 meaning the observation is genuine and 2 that it is forged. Basic statistics are performed on these two variables to look more closely at legitimate and counterfeit items. The data shows there are 762 genuine entries and 610 forgery entries. The Wavelet Transform tool extracts features from the images, which are demonstrated in integers for four variables, including: 
1.	V1 = variance of Wavelet Transformed image, which measures the spread between these numbers in the dataset (Sturdivant et al., 2016).
2.	V2 = skewness of Wavelet Transformed image detects the symmetry of the curve in terms of the image data features.
3.	V3 = kurtosis of Wavelet Transformed image describes the degree of the tails and at the peak of the curve in a frequency distribution (Sturdivant et al., 2016) 
4.	V4 = entropy of image measures the degree of randomness in the image features (Thum, 1984). 
Summary statistics and histograms demonstrate a left skewness in genuine entries (class = 1) for variance, skewness, and entropy. Kurtosis has a right skew that looks to be multimodal. Forgeries (class = 2) show a rightward skewness in variance and kurtosis, with a left skewness in entropy. This suggests higher variance, skewness, and entropy in the images. When classes are not separated, variance is multimodal but relatively normally distributed. Skewness is left-skewed and multimodal, kurtosis is right-skewed and bimodal, and entropy is left-skewed. Items with larger entropy values and kurtosis tend to be a class = 2, forgery. Higher variance and skewness values tend to be class =1, genuine. 

## Model Evaluation
Summary statistics and histograms help with visualizing the data in the banknotes dataset. After reviewing the documentation and analyzing these summaries, I determined an isolation forest model was the best fit for predicting forgery by asking specific questions about the banknote images' Variance, Skewness, Kurtosis, and Entropy. Anomaly detection, clustering, and correlation coefficient analysis helped detect outliers, group similar items, and identify correlations between observations. Overall, this was a good fit model, and I did not see any reason or way to improve it, as it successfully identified forgery items.

### Interptration can be found on my website at https://rachaelherman.com/counterfeiting-banknotes-data-mining/ 

