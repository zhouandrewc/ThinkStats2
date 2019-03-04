<head>
<h3>Daphka Alius</h3>
<h3>March 4, 2019</h3>
<br>

<h1>Analyzing the relationship between yearly alcohol consumption to yearly heroin consumption in the US in 2017</h1>
</head>

<h2>Introduction</h2>

This project examines the relationships between alcohol use and and heroin use in the US. This analysis was accomplished using public data from the National Survey of Drug Use and Health (NSDUH). The purpose of NSDUH is to “measure the prevalence and correlates of drug use in the united states. Since 1991, the target population of the survey has been civilians (including those living on military bases) who were at least 12 years of age at the time of the survey. The sample is representative of all the 50 states and has been designed to collect larger sample size for the larger states while maintaining sufficient sample size of the smaller states. Since 2014, the survey has oversampled youths aged 12-17 and young adults age 18-26 while also placing more samples in the 26 and older age groups. For further details on the methodologies of the survey, please see [link].

<h2>History of Heroin/Alcohol Abuse in the US</h2>

[INSERT History of Alcohol Abuse in the US]

Heroin is a powerful non-medically prescribed opiate narcotic in the US but has been granted pharmaceutical grade outside of the US. Opiums have been known for their pain relieving properties since [insert date]. 
[Snippet to provide context to the comparison]

<https://drugabuse.com/heroin/history-statistics/>


<h2>Methods</h2>

Since the focus of this reseach was for the year 2017, survey results from the NSDUH was collected, cleaned and validated. To provide background on the participants of the survey, demographics analysis along the line of race, age group, and education was completed. [highlight highest participants of these groups]. To pursue further, two variables were selected for correlation analysis: alcyrtot - which refers to alcohol use for the past 12 months and heryrtot - which refers to usage of heroin in the past 12 months [needs to confirm if it’s prescribed or not]. Prior to correlation analysis, preliminary exploratory analysis of these variables were performed. The distributions of the data were plotted and described using their summary statistics that describes the shape, center, and spread. Furthermore, we examined whether the two variables can be modeled using an analytic distribution such as normal, lognormal, exponential, and weibull. In addition, a kernel density estimation analysis was performed to smoothen the data to determine whether the data fits an analytical model’s pdf. For the correlation analysis, the two variables were plotted to determine if there exists a linear relationship and regression analysis followed to determined the strength of the correlation.

<h2>Results<h2>
<h3>Demographics</h3>
Out of the 56276 people who provided useful response to the survey regarding their age at the time of the survey, 35.4% were between the age of 12-17, 24.5% between the age of 18-25, 24.3% between the age of 26-34, and 15.6% were 35 and above.
With regards to race, 58.8% of the respondents were Caucasian, 18.1% identified as Hispanic, 12.5% as Black or African American, 4.6% Asian,1.5% native american/AK natives, 0.46% HI/Pacific Islanders, and 3.8% more than one race. 
[insert about education]


[make sure to highlight number of participants that responded to heroin us]
<h3>ALCYRTOT: Past 12 Months Alcohol Use</h3>

The Distribution of Alcohol used can be described as multimodal and assymetric in shape. The median is 48 days, which means that about 50% of the respondents consumed alcohol 13.1% of the year with a min consumption of once during the year and a max of all 365 days of the year. The spread as measured by standard deviation is ~91 days.
[needs to measure skewness]
<br>


Using these three visualizations, the distribution of alcohol use appears to fit the Weibull analytic distribution. The graphing of the complementary CDF on log-log y scale and log x scale shows a linear relationship, which is the expected form of a weibull on these scales. Alternatively, a kernel density estimation was used to smoothen out the data to see whether it fits an analytic model's pdf and the result shows the curvature of a weibull under some unknown parameter. Similar observations were made in the distribution of heroin use.

<h3>HERYRTOT: Past 12 Months Alcohol Use</h3>

The distribution of heroin use is multimodal asymmetric in shape, just like the distribution of alcohol use. The median is 87.5% -  a huge difference of ~40 days from alcohol use. Similar to alcohol, the two extremes show that some respondents only resorted to heroin once a year while others were using it daily. The interquartile range shows the spread of the middle 50% of the observations to be 206 days.

[needs to measure skewness]


<h3>Correlation Analysis</h3>
<ul>
<li>correlation coefficient: -0.22</li>
<li>intercept: 140 days of heroin use/year</li>
<li>slope: for every increment of alcohol consumed, we see 0.27 days less of heroin consumption</li>
<li>standard error: 0.095</li>
<li>pvalue: pvalue=0.00390 </li>
</ul>

<h2>Conclusion</h2>
Although alcohol abuse is common in the US and the opiod crisis has become a national epidemic, there's a stark difference in yearly consumptions of alcohol and the yearly consumption of heroin.
<br><br>


<h2>Comments/Questions: </h2>
<body>
This is a very rough draft of the summary of the analysis of these two variables. It does not read like a blog as of this moment. Here are some of my concerns. 
<ul>
<li>Am I comparing apple to oranges even if they're in the same units? Should I standardize to show a clear comparison of the two variables</li>
<li>Should I consider binning by age groups since alcohol abused is usually known for being more common among 
young people but who consumes heroin the most? I think that can add more to the story.</li>
<li>Also, I'm having a tough time interpreting my results - needs to find a way to make the results as clear to any reader</li>
<li>Needs to frame a story - (working on that part): Is it possible to talk about how maybe the people who consume alcohol the most do/do not also abuse alcohol </li>
<li>how to relabel the categorical variables (age groups, race, etc) to be clear to readers</li>
<li>how to deal with discrepancy from results in code book versus results from dataset analys in the case of demographics?</li>
</ul>
</body>