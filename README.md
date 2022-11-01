# Water-Treatment-ML-model-in-R

Report ReadMe

Executive Summary
The aim of this study was to find out the role of different variables that affect the water treatment process at different stages. We found out several insights from our research methods. The variables are the observed values of different attributes of water passing through its treatment after four stages namely, input stage, primary settler, secondary settler and final output stage. Corrplot showed several preliminary insights on how the processes adapted by the water treatment is actually changing its various attributes through each of the four phases. By looking at the self dependence of different variables like pH, Conductivity and Sedimentation, we see that the processes adapted by the water treatment plant to reduce the turbidity due to the precipitation of anionic and cationic salts worked as expected. In Stepwise regression a group of 12 components which comprise of  was found to be the most important components that could determine the pH of the water going through the water treatment plant. This pH of the outflowing water will in turn help determine the acidity or basicness of the water which can later be used to see if the water is potable to drink or for any other end-use like irrigation, industrial water supply and so on. Likewise, running CCA analysis allows us to find out 2 major correlations between primary settler and the final output. In the PCA analysis, we found which variables are related to each other and they were grouped under respective components. 
Summing it up, we found out several results and insights that play a significant role in determining the water quality in the treatment process. All the research methods showed different significant results that can be used for further analysis by experts.



Abstract
Water treatment plants mainly improve the quality of water to make it more suitable for a particular end-use like drinking, industrial water supply, irrigation, river flow maintenance, water recreation or many other uses. The objective of this study is to identify the components that influence the quality of water coming out of such water treatment plants. The pH of water will be majorly used to assess the quality of water. This pH of the water coming out of the plant will help in identifying whether the water is more acidic or basic and in turn will provide insights to determine if the water is suitable for end-use like drinking, irrigation and so on. The water treatment plant dataset with 38 variables that is being used in this study was made available by the UCI (University of California Irvine) Machine Learning Repository. The first step after cleaning the dataset was to identify the correlations between the variables. In the next step, a stepwise multiple regression model was created to come up with the list of influential variables in determining the pH of the water going through the water treatment plant. Later, Canonical Correspondence Analysis (CCA) on the dataset indicated that the most representative variables in the primary phase are suspended solids and volatile suspended solids. Biological demand of oxygen  also indicates the biodegradable waste might be  the majority of the primary phase. At the last step, Principal Component Analysis (PCA) is being used to identify and group similar variables together with the help of components predicted by the PCA model. The model predicted by stepwise regression did have certain outliers and also issues with few variables not getting categorized as well as we expected, with the PCA model. Overall, the presented techniques and statistical methods provide knowledgeable insights on the components responsible for determining the quality of the water going through the water treatment plant.   


Introduction
In civil engineering, water treatment plants played a crucial part as a one of the basic infrastructures alongside with power to sustain the neighboring cities. However, almost 2 decades ago when water treatment plants were not fully automated in Spain, the water purification level could be unstable depending on the water condition, turbidity as well as the configuration of the water treatment plant. Aside from the predetermined factors, human error was a possible variable to take into consideration for the final output water quality. To ensure the water plant can make transition to fully-automated system to detect and predict possible problems in each water purification states, the water treatment plant dataset aimed to achieve the goal by introducing domain experts to manually pick up the predictor variables to help the water treatment plant to reach full self-monitoring functionality. All second hand data used in this project was obtained via UCI machine learning repository. This data was collected in one of the water treatment plants located in Spain. The water treatment process can be simply broken down into 4 major procedures: input of contaminated water, primary settler, secondary settler, and eventually the output of the purified water. In the research project we desire to find out more from the given dataset using multivariate statistical methods to know more from the dataset in terms of water treatment.

Literature Review
Two related papers found on the dataset description page of UCI Machine Learning Repository is the starting point of our literature review. Both Belanche et al. (1992) and Javier et al. (1993) should be reviewed together as complementary researches.  Before the introduction of an expert-based system, running water treatment plants were based mostly on manager’s past experiences Javier et al. (1993). But the variables involved during the water treatment process are numerous and complex. The goal for Belanche et al. (1992) was to create an expert-based system for water treatment plants to reduce cost and improve the quality of water.
The water purification domain was described as 'ill-structured’ in Belanche et al. (1992). This was further explained by Javier et al. (1993) by specifying the state that research communities have not reached consensus on topics or having disparate results. This directly caused Belanche et al. (1992) to use LINNEO+ to construct the expert-based system. Since LINNEO+ allows nominal and numeric data input for classification with reasonable processing cost, which is a flexibility not provided by other softwares. Javier et al. (1993) took the research result and used other methods including KOBWEB and K-means expecting to have different results. Eventually, both classification methods generate similar results with minor differences on chosen variables. This indirectly supports the research consistency of Javier et al. (1993) and implying that building an expert knowledge based water treatment plants system is possible via machine learning other than LINNEO+.
The complexity of water treatment plants mentioned by Belanche et al. (1992) is further elaborated by Avella et al. (2011). The research team was dealing with individual variance of each water treatment plant as well as the group-wise variances including water plants structure and datasets collected. In terms of analytic approach, Avella et al. (2011) uses XLSTAT software to run statistical models. But the theoretical bases are essentially the same since both Belanche et al.(1992) and  Avella et al. (2011) use fuzzy classification. In variable selection, Belanche et al.(1992) depends on experts’ empirical experience while Avella et al. (2011) utilized Principal Components Analysis (PCA) to select variables by correlation. Furthermore, PCA is generating promising results from multiple articles reviewed in Avella et al. (2011). Therefore a commonly used method analysing huge datasets of variables and observations.
According to the results from Avella et al. (2011), we learned what to expect from our dataset. The volume of sludge combined with the calcium and magnesium ions will result in steady sludge settling. Though we do not have the measuring data for cations, we have ph value and Zinc ions to serve as substitute indicators. Another result mentioned by Avella et al. (2011) is the sludge settling results in this case will reach an optimal level within a certain range.
Some of the research questions decided for this dataset are as follows:
Hypothesis testing to check for relationship between a few variables including input zinc to the water plant (ZN-E) and output ph(PH-S), input sediments to the water plant (SED-E) and output conductivity (COND-S). Presented by Chungkuang Lin.
Identifying the correlationships between the independent variables and PH-S(output ph).
Presented by Akshat Gupta.
Check for the optimal outcome variables that can be used to predict the PH-S(output ph) using Stepwise multiple linear regression. Presented by Sandeep Pala Sreeramulu.
Creating linear regression to explain the output PH (output ph) possibly using Lasso regression to find the optimal outcome variables. Presented by Brijesh Taunk.
We plan to learn how to effectively run hypothesis testing and regression methods to determine the optimal parameters to determine the water quality based on the ph level of the water. The hypothesis could be like how different levels of residuals will affect the PH-S will in turn indicate the water quality. 



Methods
The first research question is to identify the correlationships between the independent variables. It is done by observing how the  pH value of output water gets affected by each of all the attributes available for the supplied water(input) to the plant, pH value greater than 7 will be taken as the strength of cations in the sedimentation process, as a substitute for other unknown cations in the input water. Correlation plots will be used to identify any significant correlation between different predictor variables. The assumption for this research question is that the dataset is normally distributed and numerical in nature. This method will be implemented using R (version 4.0.3). The packages and ‘corrplot’ will be used during this process. Next we will see how each input variable affects the output variable upto what extent and will see how the predictions offered by each individual variable differs from the predictions offered by others. We will find which ones are the significant contributors that affect PH-S in this process. (Conducted by Akshat Gupta)
In order to find the optimal outcome variables that can be used to predict the PH-S(output ph). Stepwise multiple regression will be applied on the dataset to explain the optimal outcome variables to explain output ph of the water. This method will identify which components of the water treatment plant contribute the most in determining the water’s output ph which in turn explains the quality of water (i.e, acidic or alkaline) after going through the water treatment plant. The assumptions made for linear regression are that the dependent variable is normally distributed, there is a linear relationship between the variables, no multicollinearity and have equal variances (homoscedasticity). This method will be implemented using R (version 4.0.3). The packages ‘readr’ and ‘plyr’ will be used during this process. (Conducted by Sandeep Pala Sreeramulu)

The third research question is to take a closer look at the correlation between the primary and secondary water purifying process. The dataset to answer the question is to use second hand water treatment data from UCI machine learning repository. The statistical method of choice will be the canonical correlation analysis (CCA). The required R studio library packages are: yacca, readr, fmsb, REdaS, psych to conduct the stated statistical method. An initial data cleaning resulted in 380 valid observations without missing values and 38 variables within the dataset. (Conducted by Chung Kuang Lin)
Last, creating Principal Component Analysis (PCA) to see which variables come under the same category or are related to each other. PCA will be used on the dataset to find the results. PCA will allow us to summarize the information content in large data tables by means of a smaller set of “summary indices” that can be more easily visualized and analyzed. The assumptions made by PCA is that :
There needs to be a linear relationship between all variables.
You should have sampling adequacy, which simply means that for PCA to produce a reliable result, large enough sample sizes are required.
There should be no significant outliers.
This method will be implemented using R (version 4.0.3). The packages ‘Psych’ and ‘Factoextra’ will be used during this process. Two sided tests will be used with significance being p < 0.05. (Conducted by Brijesh Taunk)










Discussion and Results
Research question 1 result (Akshat):
Identifying the relationships between independent variables. Corrplot is made for identification of the pairs showing significant correlation between each other. 

![Picture1](https://user-images.githubusercontent.com/89531599/199129045-713af60e-843e-4ca0-8715-b9d1c62bcdfc.jpg)

Figure 1: Correlation plot between pH.S and other variables across the dataset.
To answer question one, we observed significant correlation between pH-E (Input pH of water to the plant), pH-P (Input pH to the primary settler) and pH-D (Input pH to the secondary settler), and similar correlations between COND-E (Input conductivity to the plant) , COND-D (Input conductivity to the secondary settler) , COND-P (Input conductivity to the primary settler)  and COND-S ( Final conductivity of output water)  was also seen. A negative correlation between SSV-P( input volatile suspended solids to primary settler) and RDSS-p (performance input suspended solids to primary settler),SS-S (output suspended solids) and RD.SS.G  (global performance input suspended solids),  SED-D  (input sediments to secondary settler) and RD SED.P (performance input sediments to primary settler) and a significant negative correlation between SED.S (output sediments) and RD SED.G (global performance input sediments) was observed. Looking at the corrplot, it was seen that the input water for primary and secondary settlers was showing similar attributes, while a significant negative correlation between output sediments and global input sediments shows that the processes deployed on input water is actually working successfully to decrease the sedimentation in water.  

Research question 2 results (Sandeep)
Find the optimal outcome variables that can be used to predict the PH-S(output ph). Stepwise multiple regression is applied on the cleaned data and the variable ‘null’ is initialized for the forward regression and variable ‘full’ is initialized for the backward regression. The results of this are shown below.


![Picture2](https://user-images.githubusercontent.com/89531599/199130644-c6913440-5302-4b97-a582-4fc9c7d9e9d8.jpg)


Figure 2: Stepwise linear regression summary.

With the above results, the adjusted R-squared is close to the multiple R-squared value. This means that there is no multicollinearity. The variable SS-E has the highest p-value. Since each variable affects each other’s p value in the model, removing the variable SS-E will make other variables possibly significant. Therefore, the difference the variable SS-E had accounted for, will get redistributed into other variables in the matrix. 
The variables SSV-S and SED-P are significantly different from 0.05 level. So, SS-E and SED-P are the significant variables from stepwise multiple regression.
The outcome variables are PH-D, DQO-D, SSV-S, ZN-E, RD-SS-P, SS-D, PH-E, COND-P, SED-P, COND-P, Q-E and SS-E i.e, these are the optimal variables that play a significant role in determining the output ph (PH-S) of the water through the water treatment plant
Research question 3 Results (Chung Kuang Lin)
The lack of water treatment related background leads us to conduct a canonical correlation analysis (CCA) on the water treatment dataset to find out if certain variables are highly correlated with each other. The two groups of data chosen are primary treatment (primary) and output performance (output). We find out the conductivity (COND.P) to be highly correlated (0.9) between primary treatment and output performance. The primary group can explain 75% of output performance while the output performance can explain the 80% of the input water.


![Picture3](https://user-images.githubusercontent.com/89531599/199131075-279b221b-0e7c-4726-9777-80f34f249211.jpg)

![Picture4](https://user-images.githubusercontent.com/89531599/199131090-9da9402f-d56f-44e8-bf27-591bc78c30d3.jpg)


Figure 3: CCA Helio plot (Left: 1st loading, Right: 2nd loading)

According to the previous literature review, we expect to see variables including ph. value and metal ions related variables to be correlated in different parts of the water treating process. Yet the results we received from CCA showed a different explanation. The ph. value and conductivity variables for primary and eventual output of water are highly correlated only when either one of the variables is significantly correlated. In the first loading of CCA, conductivity is the variable to be highly correlated for both primary and output data. In this case the ph. value was not well correlated. While in the second loading the ph. value became highly correlated but with conductivity change from highly correlated to be negatively correlated with almost to none. 
The conclusion for finding out the critical variable that highly correlated with the water treatment plant data set. We discovered 2 major variables ph. value and conductivity to be mostly correlated with output water through previous CCA results. This allows us to focus on how conductivity of initial input to the water plants is related to the performance. This was implicitly mentioned by Al Saad et al. (2020) stating the metal ions in the water to be more conductive. High conductivity correlation here can have multiple interpretations. One being the salinity of the water is not being taken off during the water treatment process. Another aspect of the salinity is the composition of the metal ions which we cannot know from the given dataset. The greater the salinity the more unsuitable for the water to be used for irrigation or drinking. The influence of how salinity changes the durability of the water treatment plants facilities is yet another problem to be solved by having more data on the composition of the water. A significant negative correlation between input water sedimentation and global output water sedimentation tells us that the ions suspended in water that could result in sedimentation were significantly reduced after primary and secondary settler.



Research question 4  Results (Brijesh):
Create a PCA Analysis to represent the dataset as a smaller set of variables (summary indices) in order to observe trends, jumps, clusters and outliers. This overview will uncover the relationships between observations and variables, and among the variables.

![Picture5](https://user-images.githubusercontent.com/89531599/199131107-99047267-16fa-476

Figure 4: Scree plot for model building.


![Picture6](https://user-images.githubusercontent.com/89531599/199131123-5ad6a68a-fe83-4593-9bc6-973e0d6c8971.jpg)
0-9a5c-4fed55ce5aba.jpg)

Figure 5: Structural loading of PCA.

Initially a scree plot of the dataset was made, it showed a knee bend between 3rd and 4th variables, so 3 factors were applied on the PCA analysis. Above we can see the final PCA on the dataset. From the initial 2 PCAs, all the variables which showed null values were removed from the dataset. After every PCA the cumulative variance increased. This showed us that the insignificant variables were lowering the accuracy of the dataset. As soon as they were removed, the cumulative variance increased.
The PCA analysis showed that variables DBO.E,  DQO.E, COND.E, DBO.P, COND.P,  DBO.D, DQO.D, COND.D and COND.S form a cluster and are similar in some way. The variables DBO.S, DQO.S, SS.S, SED.S , RD.DBO.S, RD.DQO.S, RD.DBO.G, RD.DQO.G, RD.SS.G  and RD.SED.G are related and fall under RC 1. Lastly, the variables SS.E, SSV.E, SED.E, SS.P, SSV.P, SED.P, SSV.D  and RD.SS.P were grouped together under RC3.

Limitations
The water treatment plant dataset is not without limitations. First, the missing values for certain variables are influential to our valid sample count. The original dataset consists of 38 variables and 527 observations. After cleaning the missing value, only 380 observations left for further analysis. The statistical part of the research must be conducted under a scaled dataset. Second, during the statistical part we noticed a great number of overlapping variables were measured in different parts of the water treating plant. This will directly impact our regression model by the tendency to create inflated models. Furthermore, all members in the groups are not familiar with water treatment projects. The disadvantage of lacking domain knowledge is another challenge presented in the research process. If similar research is conducted in the future using second hand data. Our suggestion is to focus on data which provides the most about the chemical or biological composition of the water to generate a result with better clarity on related topics.
Conclusion
Upon running Corrplot we found that Conductivity, pH and sedimentation are self correlated in all 4 phases of water treatment, but no intercorrelation was seen between them. It was observed that the input water for primary and secondary settlers showed similar attributes, while a significant negative correlation between output sediments and global input sediments showed that the processes deployed on input water is actually working successfully to decrease the sedimentation in water.
After applying the stepwise multiple regression, the variables input PH to plant and secondary settler, input chemical demand of oxygen to secondary settler, volatile suspended solids, suspended solids (input and secondary settler) input zinc, conductivity and sediments to primary settler were found to be the most significant in determining the output ph (PH-S) of water going through the water treatment plant, which in turn affects the quality of water (as ph determines the acidity of the water, water being more basic and more acidic is harmful). This will also allow us to draw a conclusion whether the water going through the water treatment is potable to drink, irrigation and many other day to day use.
The results from the CCA have some insights to be revealed from the model we constructed. Since the pH value of the initial water treatment phase could imply the salinity of the water, a pre-treatment phase can be implemented into the system to lower the wear of the water pipeline. On the other hand, the metal ions and the minerals in the water treatment system might join together to clog the pipeline. The installation of the osmosis film before transmitting the water in different phases of the purification process can extend the longevity of the water treatment plant facility which shares a similar structure as the dataset.
Principal Component Analysis showed us the variables that are similar and grouped them together. Cumulative variance after removing the null variables increased significantly from 49% in the first PCA to approximately 63% in the final. All the variables which were significant were grouped under the respective components.



References:
Alonso, J., Garcia, C., & Poch, M. (1993). LINNEO+: a classification methodology for ill-structured domains. LSI-93-22-R. https://upcommons.upc.edu/handle/2117/97083

Avella, A. C., Görner, T., Yvon, J., de Donato, P., Chappe, P., & Guinot-Thomas, P.. (2011). A combined approach for a better understanding of wastewater treatment plants operation: Statistical analysis of monitoring database and sludge physico-chemical characterization. Water Research, 45(3), 981–992.
https://doi-org.proxy2.library.illinois.edu/10.1016/j.watres.2010.09.028
Al Saad, Zainb A.A., and Hamdan, Ahmed N.A. “Evaluation of Water Treatment Plants Quality in Basrah Province, by Factor and Cluster Analysis.” Journal of Water and Land Development no. 46, no. (2020): 10–19. https://yadda.icm.edu.pl/baztech/element/bwmeta1.element.baztech-bf565518-2a4d-49ad-aa82-4be4a5619fbb
Belanche, L., Sànchez, M., Cortés, U., & Serra, P.. (1992). A knowledge-based system for the diagnosis of waste-water treatment plants: Vol. 604 LNAI. Springer Verlag. https://doi-org.proxy2.library.illinois.edu/10.1007/bfb0024984

Dua, D. and Graff, C. (2019). UCI Machine Learning Repository  Irvine, CA: University of California, School of Information and Computer Science. https://archive.ics.uci.edu/ml/datasets/Water+Treatment+Plant

Ebrahimi, M., Rockaway, T. D., & Gerber, E. L.. (2017). Temporal performance assessment of wastewater treatment plants by using multivariate statistical analysis. Journal of Environmental Management, 193, 234–246. https://doi-org.proxy2.library.illinois.edu/10.1016/j.jenvman.2017.02.027






