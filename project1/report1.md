# Heroin and Alcohol: Could there be a relationship?

On October 26, 2017, Donald Trump and his administration declared the opiod epidemic a national *Public Health Emergency.* This declaration allows both federal and state health agencies to apply and use fund to prevent the spread of the opiod epidemic. With an increased in prescription and access to opiod medications, there has been a widespread misuse of opiods, making opiods drugs some of the most abused substances in the US. The *US Department of Health and Human Services* reported that **"opiod overdoses accounted for more than 42,000 deats in 2016."** Among the non-medically prescribed abused form of opiod in the US is heroin. The *National Institute on Drug Abuse Prescription* describe medically prescribed opiods like **Oxycodin** and **Vicodin** to have similar effects to heroin, making them just as likely to be abused especially with the increase access through prescriptions. Another substance that's highly abused in the US is alcohol. The *CDC* reports that **88,000 deaths from 2006-2010 has been related to excessive alcohol consumption.** Given the prevalence of alcohol an heroin abuse in the US, this project investigates whether there exists a relationship between alcohol consumption and heroin consumption. 

## National Survey of Drug Use and Health 2017
In order to proceed with the investigation, data was collected from the National *Survery of Drug Use and Health* (NSDUH)for the year 2017. The purpose of NSDUH is to measure the prevalence and correlates of drug use in the united states. The Survey targets repondents who were at least 12 years of age at the time of the survey. NSDUH draws from a representative sample of all the 50 states in the US. Since 2014, youths of age 12-17 and young adults 18-25 were oversampled and more samples were also targeted for the 26-older age group. For further details on the methodologies and details of the survey, please see the [codebook](http://samhda.s3-us-gov-west-1.amazonaws.com/s3fs-public/field-uploads-protected/studies/NSDUH-2017/NSDUH-2017-datasets/NSDUH-2017-DS0001/NSDUH-2017-DS0001-info/NSDUH-2017-DS0001-info-codebook.pdf).


## Demographics of the 2017 Respondents
### Age
![Screen Shot 2019-03-09 at 20.52.03.png](quiver-image-url/3B2381941CEE4871B47373AFDBA60DFB.png =446x289)

### Race
![Screen Shot 2019-03-09 at 20.56.27.png](quiver-image-url/FF65F6E561592E2719578BFAE249E506.png =459x371)

### Education
![Screen Shot 2019-03-09 at 20.57.25.png](quiver-image-url/5D7406C804EAFD071B2629AD9C1AB1A6.png =437x380)

Out of the 56,276 respondents that provided data to the survey, majority of the respondents were youths and young adults of the age 12-26, making 60% of the respondents. Given the age-education level correspondence, it was unsurprising to see that the majority of the respondents were in K-12 education or has had some college level education. The sample was racially diversed with racial makeup similar to that of the US, with majority of the respondents idenfying as Caucasian, 18.1% Hispanic, 12.5% Black or African American. The other racial groups were minorities in the survey.

## Methodologies
In order to determine if there exists a relationship between heroin and alcohol consumption the following two variables were selected for correlation analysis: **alcyrtot** - which refers to alcohol use for the past 12 months and **heryrtot** - which refers to usage of heroin in the past 12 months. Preliminary exploratory analysis of these variables were performed. The distributions of the data were plotted and described using summary statistics that describe the shape, center, and spread and was examined to see if any of the analytic distribution can be used to model the dataset. Lastly, the two variables were plotted to determine if there exists a linear relationship and regression analysis followed to determined the strength of the correlation.

## Results
### Alcohol Consumption
#### Histogram
![Screen Shot 2019-03-09 at 21.16.57.png](quiver-image-url/F198A9F045A257B7A6C2BC53242D9CC2.png =467x280)
For the year 2017, 33,532 of the 56,276 (59.6%) of respondents reported to have consume alcohol from the previous 12 months. As can be observed in the histogram, the distribution of alcohol consumption for the year 2017 is multi-modal, asymmetric and right skewed with median of 48.0 days out of the 365 days of the year. The observations are widely spread. The standard deviation is 91.3 days, with a maximum report of consuming alcohol daily over the course of the year.
#### Cumulative Distribution Function
![Screen Shot 2019-03-09 at 21.19.13.png](quiver-image-url/FFD975AE2F9ADE8031A5E8D814E79E55.png =431x274)

### Heroin Consumption
#### Histogram
![Screen Shot 2019-03-10 at 12.11.38.png](quiver-image-url/9D19F0D9B7D7A77A771277F5683620DD.png =427x278)
As for Heroin, we have 212 respondents who reported to have consume heroin from the previous 12 months. While this is a small percentage of consumers as compared to consumers of alcohol, we observed a high usage of heroin among this group. The median of consumption of heroin over 365 days was 87.5 days. This is 1.8 times more than the median of alcohol consumption. The observations were high in variation with standard deviation amounting to 128.5 days. The maximum numbers of days reported to have consumed heroin from the previous year was 365 days, which is every day for the past year.
#### Cumulative Distribution Function
![Screen Shot 2019-03-10 at 12.12.53.png](quiver-image-url/06E9B0FA4CC9F643A6994300BD59530B.png =447x275)

By looking at the Cumulative Distribution Function (CDF) of both variables, we observe similar pattern/shape. The CDF function measures the percentile rank of each day of consumption. Using different plotting scale, we were able to determine that the two variables could be modeled mathematically using an exponential/weibull distribution function. Understanding this feature of the two variables is beneficial when extrapolating for values that were not found in our observations. Exponential distributions, a special kind of weibull distribution, is typically used to measure the interarrival time between events of a random variable. In this case, we are measuring the number of days (time) of alcohol/heroin consumption which is also a random variable that can take values between 0 - 365 days, making the exponential model a good fit for our two variables.

#### Correlation Analysis

![Screen Shot 2019-03-10 at 12.24.15.png](quiver-image-url/CD2B75D036458F98EF065C3FF268087D.png =437x282)

Now that we have a better understanding of the two variables, a linear regression was performed to measure whether there was a correlation or association between the two variables. The two variables were plotted against each other using a scatter plot. There's a weak, negative linear correlation between the two variables with correlation coeffient r = -0.22. Although the observations do not take the typical shape of the rugby/football ball that usually signals a linear relation, we know that it's statistically significant to highlight the linear relation between the two variables with a p-value of 0.0039. As opposed to the rugby shape, the plot above depicts that the majority of the points cluster around the axes, highlighting that most people do not typically use both substances.