# Heroin and Alcohol: Could there be a relationship?
#### by Daphka Alius

On october 26, 2017, President Donald Trump's administration declared the opioid epidemic a national *Public Health Emergency.* A statement of this magnitude from federal level implies that the abuse of and the number of death related to opiood drugs have become a problem in our society. Given the increase in prescription and access to opioid medications, there has been a widespread misuse of opioid drugs, making them some of the most abused substances in the United States (US). The *US Department of Health and Human Services* reports that **"opioid overdoses accounted for more than 42,000 deaths in 2016."** Heroin, a form of opioid, remains one of the most abused non-medically prescribed drugs, signaling that medically prescribed opioids of similar effect like **Oxycodin** and **Vicodin** are just as likely to be addictive especially with the increase access through prescriptions. While the opioid epidemic continues to garner media attention, there are other substances that are overused in the US - one of which is alcohol. The *CDC* reports that **"88,000 deaths from 2006-2010 has been related to excessive alcohol consumption."** Given the prevalence of both alcohol and heroin abuse in the US, it leaves one wondering whether there exists a relationship between alcohol consumption and heroin consumption. More specifically, the question under investigation is whether people who heavily consume one substance also consume the other at similar rates.

## National Survey of Drug Use and Health 2017
In order to proceed with the investigation, I collected data from the *National Survery of Drug Use and Health* (NSDUH) for the year 2017. The purpose of NSDUH is to measure the prevalence and correlates of drug use in the US. The Survey targets repondents who were at least 12 years of age at the time of the survey and selects a representative sample of all the 50 states in the US. Since 2014, youths of age 12-17 and young adults age 18-25 were oversampled and more samples were also targeted for the 26-older age group. For further details on the methodologies and details of the survey, please see the [ codebook (2017)](http://samhda.s3-us-gov-west-1.amazonaws.com/s3fs-public/field-uploads-protected/studies/NSDUH-2017/NSDUH-2017-datasets/NSDUH-2017-DS0001/NSDUH-2017-DS0001-info/NSDUH-2017-DS0001-info-codebook.pdf).


## Demographics of the 2017 Respondents
### Age
![age](/project1/images/Screen%20Shot%202019-03-09%20at%2020.52.03.png)
      

To gain a better understanding of the background of the respondents, I looked at the distribution of age, race, and education at the time they were participating in the survey. When looking at the distribution of age, as is shown above, the graph confirms the oversample of youths and young adults between the age of 12-25 as they make up approximately 60% of the respondents with a large portion being minors under the age of 18.

### Race

The racial makeup of the respondents was remarkably representative of the racial makeup of the US. A representative group of respondents serves as an attempt to provide a clear picture of who is being affected by substance abuse.

### Education

Given that 56,276 people participated in the survey and majority of the respondents were youths and young adults, it is unsurprising to see that the majority of the respondents were either in K-12 or had some college level education by the time they were surveyed.

Now that we have a better understanding of the respondents, let's dive into the methodologies and results.


## Methods and Results
In order to determine if there exists a relationship between heroin and alcohol consumption, I selected the following two variables from the dataset: **alcyrtot** - which refers to alcohol use of the previous 12 months from the time the respondents provided answers to the questions  and **heryrtot** - which refers to heroin use of the same time length. In the following order, I performed preliminary exploratory analysis of the two variables, examined whether an analytic distribution can be used to model the variables, and lastly, **heryrtot** was grouped (by reported number of days over the year) and plotted against **alcyrtot** to determine if there's any association between the two.

### Exploratory Analysis of the Two Variables
#### Distribution of Alcohol Consumption

For the year 2017, 33,532 of the 56,276 (59.6%) of the respondents reported to have consume alcohol from the previous 12 months. The distribution of alcohol consumption is multi-modal, asymmetric, and right skewed with median of 48.0 days out of the 365 days of the year. The observations are widely spread. The standard deviation is 91.3 days, with a maximum report of daily alcohol consumption over the course of the year. Using a sort of grouping system that categorizes responses into infrequently, almost daily, at least weekly, and at least monthly, most respondents (approximately 90%) fall either into the infrequently group, reporting less than 30 days of consumption over 12 months, or into the weekly group which reports between 52-300 days of consumption over the previous 12 months.

#### Distribution of Heroin Consumption
As for Heroin, we have 212 respondents who reported to have consume heroin from the previous 12 months. While this is a small percentage of responses as compared to consumers of alcohol, the days of consumption was relatively high. The median of consumption of heroin over 365 days was 87.5 days. This is 1.8 times more than the median of alcohol consumption. The observations were high in variation with standard deviation amounting to 128.5 days. The maximum number of days reported to have consumed heroin from the previous year was 365 days, which is daily. Similar to alcohol, heroin users fall either in the infrequent group or at least weekly with approximately 37% of respondents reporting using heroin between 52-300 days a year.

#### Cumulative Distribution Function

By looking at the Cumulative Distribution Function (CDF) of both variables, the CDFs have similar shape. The CDF function measures the percentile rank of the number of days of consumption. Using different plotting scale, I determined that the two variables could be modeled mathematically using an exponential/Weibull distribution function. Understanding this feature of the two variables is beneficial when extrapolating for values that were not found in our observations. Exponential distributions, a special kind of Weibull distribution, is typically used to measure the inter-arrival time between events of a random variable. In this case,  alcohol/heroin consumption, a random variable measures the number of days (time) a person reported to have used/drank heroin or alcohol, making the exponential model a good fit for our two variables.

#### Relationship


Lastly, to observe if there is an association between the two variables, I binned alcohol by days reported and looked at the mean of days of heroin use that were reported for each bin. Once again, I categorized the dependent variable alcohol into infrequently, almost daily, at least weekly, at least monthly and observed the mean of those groups. As can be seen in the graph, the group who is catagorized as infrequent alcohol consumers reported the highest mean of heroin use as compared to the other groups. In this case, it is clear that people who are using heroin for the most number of days are not the same people who are also drinking alcohol more frequently. The pearson correlation of the two variables is -0.22, which means that there's a weak association between the two variables. Therefore, we don't expect knowing someone's heroin consumption patterns to be a strong determinant factor in predicting their alcohol consumption but we now know that people who use heroin infreqently are more likely to have consume alcohol for the most number of days as compared to frequent heroin users. 
