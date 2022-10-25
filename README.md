# Project-1
# Introduction
I plan to analyze how the population density and GINI index of each county of Pennsylvania influences reported covid death rates. I want to determine the effect of the disparty between death rates in densely populated cities and in less densly populated rural areas and see if there is a correlation in death rate. I also want to determine the effects that income inequality has on the death rate through looking at the gini index of each county. The inability for a large percent of people the afford proper health care in a county with a high gini index could correspond to an increase in death rate. Covid data was gathered from https://github.com/nytimes/covid-19-data and the GINI index and population density was gathered from census.gov.

# Population Density vs Death Rates in PA
![image](https://user-images.githubusercontent.com/112734081/197607823-711deb80-2464-4f65-9932-26d91bee673e.png)

From the plot, it can be observed that there is a pretty clear increase in death rate as the population density increases. Below I have plotted the data excluding Philidelphia and Delaware (the two highest population counties) to get a better view at the lower population density data.

![image](https://user-images.githubusercontent.com/112734081/197607883-422911e5-6999-4fc3-b76f-d457a4d028b2.png)

It can be seen that the majority of the data can be observed to follow a linear trend with increasing population density.

# Gini Index vs Death Rates in PA
![image](https://user-images.githubusercontent.com/112734081/197309584-8008816d-745b-4060-b1b1-5e168fad9f60.png)

From this plot, there seems to be a slight correlation between increasing gini index and an increase in the number of deaths. Although, the data is not nearly as clear is that of the population density.

# Population Density 2 sample t-test analysis
Hypothesis: Are people in counties with higher population densities in PA more likely to have experienced fatal outcomes?
Null hypothesis: do people in higher and lower population densities have the same number of fatal outcomes?

A two-sample t-test was used to analyze the null hypothesis by splitting the data at the average population density into two section – higher population density (above average) and low population density (below average) and taking the corresponding covid deaths from each of those sections. Plotted is the null distribution obtained from a random population with the same mean and standard deviation as the high and low density populations with n = 5.

![image](https://user-images.githubusercontent.com/112734081/197684219-6f94aae1-1b13-4d9a-8199-8180f60a0e2a.png)

![image](https://user-images.githubusercontent.com/112734081/197684239-473db255-8ab9-4e71-838d-45072d9e6b71.png)

The value of t from a two sided t-test comparing death numbers corresponding to high and low populations is -4.78 and the DOF is 11.34. So taking an alpha of 0.05 we have a critical t-value of region of -2.201 to 2.201, since our value of -4.78 falls outside the critical region, we can reject the null hypothesis. This proves our origional hypothesis that people in higher population density counties in PA are more likely to have experienced a fatal outcome.

# Population Density 2 sample t-test analysis
Hypothesis: Are people in counties with higher income inequality (gini index) in PA more likely to have experienced fatal outcomes?

A two-sample t-test was used to analyze the null hypothesis by splitting the data at the average gini index into two section – higher gini index (above average) and low gini index (below average) and taking the corresponding covid deaths from each of those sections. Plotted is the null distribution obtained from a random population with the same mean and standard deviation as the high and low gini index with n = 5.

![image](https://user-images.githubusercontent.com/112734081/197685072-2c04f02c-3329-4054-9501-f590094a8a48.png)

![image](https://user-images.githubusercontent.com/112734081/197685114-ef8befa5-e496-4645-be0a-f095d1859946.png)

The value of t from a two sided t-test comparing death numbers corresponding to high and low populations is -3.18 and the DOF is 33.26. So taking an alpha of 0.05 we have a critical t-value of region of -2.04 to 2.04, since our value of -3.18 falls outside the critical region, we can reject the null hypothesis. This proves our origional hypothesis that people in higher gini index counties in PA are more likely to have experienced a fatal outcome.

# Gini Index vs Population Density
![image](https://user-images.githubusercontent.com/112734081/197607960-14f928ad-6e7f-4e7d-982d-c5a7b0fc4a62.png)

When looking at the two variables studied, gini index and population density, it can be observed that the data seems slighly dependent.

# Linear Regression Analysis
Hypothesis: Were people in less densely populated counties with lower income inequality (Gini Index) in PA less likely to have experienced fatal outcomes?

To analyze this dependence effect further, I have performed two linear regression analyses between population density and gini index, one with no interaction effects, and another with interaction effects between the two. The resulting R^2 value for linear regression with no interactions is 0.682, while the R^2 value for linear regression with interactions is 0.840. Including interactions in the analysis gives a much better fit, which confirms that there is a dependency between gini index and population density.
