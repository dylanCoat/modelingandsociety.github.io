## Introduction
  Across the globe, weather of record highs and lows have been experienced. Out of
control fires in Toronto, Manitoba, and Saskatchewan Canada in June 2025 (Public Safety
Canada, 2025). Texas, USA experienced a power grid shutdown because of a large snowstorm in
February of 2021 (Marfin et al., 2021). Coral reefs all around have been dying faster than they
can heal since the 1980s (Igini, 2025). Long-lasting wildfires raged in South Korea from late
March 2025 until mid May 2025 (Dieckman, 2025). All of these events showcase extreme
weather conditions which could be detrimental to the health of the people and environment that
have experienced these events.

  It is already well-known how adverse the impacts of climate change already are and will
continue to be. It is arguably the most pressing threat facing the world, one that needs a united
front to prevent its worsening. The median individual can only do so much, especially when the
brunt of climate change is caused by select entities. Our governments are supposed to represent
and protect us. Every single one committed to the UN’s Sustainable Development Goals. We
need them to act in our interest and fight—and if even a single one isn’t, it holds the entire world
back.

  We live in this world and under these governments, both the natural and the political
aspects of where we live should be understood as well as their effects on each other. We want to
see if national political corruption and transparency levels predict the change in ecological
health. By doing this, we would be able to predict how the world in which we live looks and
performs on the basis of political corruption. In order to achieve these goals, we created a
machine learning model that determined which aspects of political corruption affected
environmental performance the most.

## Model Creation

In creating this model, we collected our numbers from Transparency International,
specifically their world Corruption Perception Index (CPI). This index is a collection of indices
which are used to determine a country’s corruption perception score. We got out numbers for
environmental health from the Environmental Performance Index (EPI) (Block, et. al., 2024). In
this index, countries are ranked on their environmental performance biannually. In our model, we
are using the CPI, and all of its deciding factors, to determine and predict a country's EPI.

There are deciding factors, not including the Corruption Perception Index, that
determines what affects the Environmental Performance index. One of them is the Bertelsmann
Foundation Transformation Index which compares international effectiveness towards both
democracy and market economies. The second is the Economic Intelligence Unit that looks at
the Financial services, corporations, government, academic institutions and healthcare in a
country and ranks them based on how well that country performs in all the aforementioned
categories. The third factor is the Global Insights Country Risk Ratings which manages financial
risk that is based upon a country’s or location’s criminal, economic, and political factors. The
fourth is the PRS International Country Risk Guide uses different risk assessments like internal
conflict, government instability, corruption, etc. To predict the risk that countries and their
investments have. The fifth feature is the Varieties of Democracy Project which distinguishes
between five types of democracy and measures the complexity of the different principles of
democracy. The sixth one is the World Economic Forum, a platform made for cooperation
between the public and private sectors inside geopolitics. The final feature is the World Justice
Project Rule of Law which is an organization that works to protect people from injustices that
they may face by their governments. The WJP focuses mostly on the systemic corruption that
appears in the government.

Once we gathered our datasets, we combined the Corruption Perception Index and the
Environmental Performance Index into one for cohesive analysis and feature equivalence. This
allows us to make sure that no country is counted more than once, as well as making sure that
each dataset has the same countries. Now that the indices have been converted into one index, we
are able to experiment with the data.

## Experiments
The first experiment that we ran was a Random Forest Regression algorithm which
randomly picks multiple data points from our combined datasets and breaks those data points
down into which of the eight deciding variables, now including CPI as a variable, was the most
important determining feature. Once the algorithm has broken down all the elements that it
chooses, it counts up all the determining features and whichever feature has the most is the
overall most important deciding factor in that specific algorithm. If we were to run this algorithm
multiple times, there could be a difference in the deciding factor.

In Figure 1, we can see one of these Random Forest Regression algorithms. This
algorithm shows us that the World Justice Project: Rule of Law Index was the most important
feature in most of the datapoints experimented on. Practically, this means that systemic
corruption and injustice is the most important factor in determining a country’s economic
performance.

_Figure 1_

Although this algorithm gives us a lot of information about feature importance, it’s not as
reliable as other algorithms or experiments. The Random Forest Regression algorithm has a
problem with overfitting; which means it punishes some features for what it rewards other
features. This is why there is such a big gap between just the top two important features. Because
of this, the second experiment we ran was with an XGBoost algorithm.

XGBoost builds its trees sequentially, unlike Random Forest which builds them parallel.
This means that XGBoost looks at anything that went wrong in a previous step, and then tries to
correct those mistakes, which builds much more accuracy than in a Random Forest algorithm. In
Figure 2, the outcome is drastically different than in Figure 1. This is because of the correction
that XGBoost did throughout its algorithm. In this figure, we can see that the Economist
Intelligence Unit Country Ratings was slightly higher than the World Justice Project, creating a
new most important feature. However, there is one major aspect that was not included in either
the Random Forest or the XGBoost algorithm: categorical data.

_Figure 2_

Categorical data, or data that are not countable numbers, is littered throughout our entire
model. Because of this, the Random Forest and XGBoost algorithms outcomes are slightly
miscalculated. In order to fix this, we ran an experiment called CatBoost which takes into
account the categorical data that was missing in the two previous experiments. Of the three
experiments that we ran, CatBoost is the most accurate because of its inclusion of categorical
data.

In Figure 3, we can see the ultimate feature importance for our model which is the World
Justice Project: Rule of Law Index followed by the Economist Intelligence Unit Country Ratings
and the Bertelsmann Foundation Transformation Index. Practically, this shows that systemic
corruption, economic and societal institutional reliability, and the comparison of democracy and
market economies are the most important features that impact a country’s environmental
performance score.

_Figure 3_

## Overall Results

When looking at the Corruption Perception Index and all of its components and its
correlation with the Environmental Performance Index, we can see that the CPI has a negative
relationship with the EPI. In Figure 4 we can see that when the global average CPI score is low,
then the global EPI score is high; opposingly, when the global average CPI score is high, the
global average EPI score is low.

In 2016, we can see that the gap between the CPI and the EPI is the highest between the
years 2014 and 2022. This can largely be attributed to the Paris Agreement in 2016 which was an
international treaty where countries agreed to try to get the global warming temperatures below 2
degrees celsius. The impacts of this agreement started to show in 2016-17.

_Figure 4_

## Model Impact
We have tasked ourselves with finding a correlation, and possibly causation, between
ecological health issues and political corruption. Because of these topics, and the data that we are
using, there are a couple ethical concerns that should be addressed.

One important aspect to keep in mind throughout this project is that we are not measuring
actual corruption of countries, but rather their residents’ perceptions of corruption. Because this
part of our data is based on human perceptions, it makes the data less reliable; especially when
we consider that the corruption dataset takes into account most countries in the world. Although
our political corruption dataset claims to take measures to squash the variability in human
perceptions (like cross comparing countries' corruption scores) it’s important to note the
possibility of unreliable data.

Another thing to take into consideration is the differences in climate around the world.
For example, Brazil and Canada have two vastly different ecological systems, which means that
even if those two countries had the same political corruption score, that corruption could have
massively different effects on the ecological system of that country.

On top of taking climate into consideration, a country's population and ecology
desirability should also be taken into account. A country that has a desirable environment will
lead to more tourism and higher populations. Both of these can contribute to a score increase in
the Economist Intelligence Unit and the Bertelsmann Foundation Transformation Index. Both
desirability and population could also cause an increase in the World Justice Project Index as
well as the Corruption Perception Index.

## References
Bertelsmann foundation. (n.d.). The transformation index. BTI Transformation Index.
https://bti-project.org/en/?&cb=00000

Block, S., Emerson, J. W., Esty, D. C., de Sherbinin, A., Wendling, Z. A., et al. (2024). 2024
Environmental Performance Index. Yale Center for Environmental Law & Policy.
epi.yale.edu

Dieckman, E. (2025, April 30). Climate Change Heightened Conditions of South Korean Fires.
Eos. https://eos.org/articles/climate-change-heightened-conditions-of-south-korean-fires

Economist Enterprise EUI. (n.d.). Who we help: Industry research, insights & solutions.
Economist Enterprise. https://www.eiu.com/n/who-we-help/

Igini, M. (2025, October 14). Global Coral Reefs Face ‘Widespread Death’ As Warming Planet
Pushes System Beyond What It Can Cope With. Earth.Org.
https://earth.org/global-coral-reefs-face-widespread-death-as-warming-planet-pushes-syst
em-beyond-what-it-can-cope-with/

LSEG. (n.d.). Country risk ranking. LSEG: Risk Ranking.
https://www.lseg.com/en/risk-intelligence/screening-solutions/world-check-kyc-screening
/country-risk-ranking?utm_content=Brand%20Product%20Risk-US-B-EN-ALL&utm_so
urce=bing&utm_medium=cpc&utm_campaign=3008936_WorldCheckBrandProductBing
PaidSearch2025&elqCampaignId=29286&utm_term=thomson%20reuters%20country%2
0risk%20ranking&gclid=161b1a4c956e1f7bac9073be93f2a44a&gclsrc=3p.ds&msclkid=
161b1a4c956e1f7bac9073be93f2a44a

Marfin, C., Jimenez, J., & Steele, T. (2021, February 16). Hundreds of thousands remain without
power as more snow is headed to Dallas-Fort Worth on heels of record cold. The Dallas
Morning News.
https://www.dallasnews.com/news/weather/2021/02/16/thousands-still-without-power-as-
north-texas-reaches-record-low-temperature/

Public Safety Canada. (2025, October 30). Government of Canada provides update on 2025
wildfires as support continues. Government of Canada.
https://www.canada.ca/en/public-safety-canada/news/2025/10/government-of-canada-pro
vides-update-on-2025-wildfires-as-support-continues.html

Transparency International. (2025, February). Corruption Perceptions Index.
https://www.transparency.org/en/cpi/2025

The PRS Group. (n.d.). Our projects: The international country risk guide (ICRG). The PRS
Group. https://www.prsgroup.com/explore-our-products/icrg/

V-Dem. (n.d.). Varieties of democracy (V-Dem). V-Dem: Varieties of Democracy.
https://v-dem.net/

World Economic Forum. (n.d.). Who we are. World Economic Forum.
https://www.weforum.org/about/world-economic-forum/

World Justice Project. (n.d.). About us. World Justice Project.
https://worldjusticeproject.org/about-us

### AI Transparency

After finishing pieces of code, we used Claude to check that there were no errors made and all of
our results were accurate.
