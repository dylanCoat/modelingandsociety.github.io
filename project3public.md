## Introduction

It is already well-known how adverse the impacts of climate change already are and will continue to be. It is arguably the most pressing threat facing the world, one that needs a united front to prevent its worsening. The median individual can only do so much, especially when the brunt of climate change is caused by select entities. Our governments are supposed to represent and protect us. Every single one committed to the UN's Sustainable Development Goals. We need them to act in our interest and fight-and if even a single one isn't, it holds the entire world back.

We live in this world and under these governments, both the natural and the political aspects of where we live should be understood as well as their effects on each other. We want to see if national political corruption can predict the change in ecological health. By doing this, we would be able to predict how the world in which we live looks and performs on the basis of political corruption and explain what forms of corruption are most impactful on our environment.

## Dataset and Problem Framing

We will use a dataset provided by the Corruption Perceptions Index (CPI) from [Corruption Perception Index](https://www.transparency.org/en/cpi/2024) (Transparency International, 2025) which has been validated by the European Commission Joint Research Centre in 2017. The numbers from these datasets come from surveys that were conducted that asked people about corrupt behaviors like bribery, diversion of public funds, use of public office for private gain, state capture, and nepotism in the civil service. In this dataset, the lower the score resembles the more corrupt countries; however, the higher ranks resemble the less corrupt countries. It is important to know that the CPI is an index of indexes, meaning that we can look further into what kinds of corruption.

We will measure ecological health through the [environmental performance index](https://epi.yale.edu/) (Block et al., 2024) created by Yale. Yale has created an EPI score for each country by looking at 58 indicators across environmental health, ecosystem vitality, and climate change. This data is usually published on a biannual basis.

There are seven indices used in the construction of the Corruption Perception Index. One of them is the Bertelsmann Foundation Transformation Index which compares international effectiveness towards both democracy and market economies (Bertelsmann Stiftung, 2026). The second is the Economic Intelligence Unit that looks at the Financial services, corporations, government, academic institutions and healthcare in a country and ranks them based on how well that country performs in all the aforementioned categories (Economist Enterprise EIU, 2025). The third factor is the Global Insights Country Risk Ratings which manages financial risk that is based upon a country's or location's criminal, economic, and political factors (S&P Global, 2024). The fourth is the PRS International Country Risk Guide uses different risk assessments like internal conflict, government instability, corruption, etc. to predict the risk that countries and their investments have (The PRS Group, 2025). The fifth feature is the Varieties of Democracy Project which distinguishes between five types of democracy and measures the complexity of the different principles of democracy (Varieties of Democracy, 2025). The sixth one is the World Economic Forum (2025), a platform made for cooperation between the public and private sectors inside geopolitics. The final feature is the World Justice Project Rule of Law which evaluates the judicial regulation and constraints on government power, making it focused on systemic corruption.

## Initial Assumptions

To start, we focused on establishing the relationship between CPI and EPI, as it would strengthen our assumptions on how the specific indexes would impact the environment. We made two visualizations that we could draft assumptions from, the first being a comparison between the average CPI and EPI score over the time period of the study.

![comparison of epi vs. cpi over time](./docs/assets/proj3/epi_vs_cpi.png)

The graph shows how CPI and EPI move together over time, and at first glance the pattern isn't perfectly straightforward. In some years, they even seem to move in opposite directions. For example, in 2016, CPI hit its lowest point while EPI was at its highest. Then in the years that follow, EPI drops in 2018 and 2020, before climbing again by 2024 as CPI rises. What this suggests is that environmental outcomes don't always react instantly to changes in corruption levels. Instead, the relationship seems to unfold more gradually over time, with effects showing up a few years later rather than immediately. This is a concept known as ecological lag.

To get a clearer picture of the overall trend, we also plotted the data on a scatter graph with a trend line.

![another comparison of epi vs. cpi over time](./docs/assets/proj3/epi_vs_cpi2.png)

The plot establishes a linear relationship, showing that as CPI score increases, EPI also increases. Combining the insights taken from these two visualizations, we can conclude that as CPI increases, EPI is also expected to increase.

## Model Experiments / Evaluations

For this part of our project, we tested a few different machine learning models to see how well they could predict environmental performance based on corruption and governance related data. We decided to use Random Forest, XGBoost, and CatBoost. These are all built upon decision trees. A decision tree is basically a model that makes predictions by asking a series of simple questions, kind of like a flowchart. It starts with all the data and then splits it into smaller groups based on the most important factors. For example, it might first ask, "Is this country's rule of law high or low?" Then, depending on the answer, it moves down a different path and asks another question, like "Is the economy stable?" or "Is corruption perception high?" This process keeps repeating until it reaches a final prediction at the end. However, each of these models do this in their own way.

Random Forest works by building lots of decision trees in parallel and averaging their results. XGBoost builds trees one at a time, improving the model step-by-step by learning from its mistakes. CatBoost is especially good at working with mixed types of data and picking up more subtle patterns across countries and regions. We chose these models not just for accuracy, but because they also let us look at feature importance, which stands for which factors matter most in making predictions. Since the CPI is made up of multiple different governance and corruption-related indicators, this helps us understand which parts of the system are most strongly linked to environmental outcomes. Out of the three models, CatBoost performed the best. It explained about 57% of the variation in global environmental performance scores and also had the lowest prediction error. In simple terms, it was the most accurate at capturing the overall pattern in the data. Despite CatBoost being our highest performing model, we made a visualization to include each model's feature importance, as we felt like valuable insights could be gained from the comparisons.

![graph showing the importance of the various cpi indices](./docs/assets/proj3/cpi_indices.png)

From the feature importance comparison, we can deduce that the World Justice Project Rule of Law Index and Economist Intelligence Unit Country Ratings are the most reliable predictors of environmental health. The World Justice Project being of consistently high feature importance suggests that things like government regulation, structural integrity, and judicial strength are important to environmental health. Likewise, the Economist Intelligence Unit suggests that along with structural protections, countries with strong and stable economies are more likely to have higher performing environments. This is likely due to having more resources to be able to enforce regulations to protect the environment. The results are pointing to a broader idea that it might not be corruption alone that dictates environmental health, but rather the effectiveness of the regulations designed to protect it.

View the more comprehensive technical report [here](project3technical.md).

## Limitations, Ethics, and Reflection

We have tasked ourselves with finding a correlation, and possibly causation, between ecological health issues and political corruption. Because of these topics, and the data that we are using, there are a couple ethical concerns that should be addressed.

One technical limitation was the exclusion of Year and Region from our feature importance analysis. Year was the most important feature for our decision trees, but no insight could be taken away from that, as including Year would have overshadowed the other variables. However, excluding these features from the analysis could overstate the importance of the other features. We decided to prioritize interpretability in order to get actionable insights, but the takeaways should be understood within this limitation.

When it comes to the features that we used to deem importance, we had to use personal research to determine what those features were, what they did, and how they affected the Environmental Performance Index.

One important part to keep in mind throughout this project is that we are not measuring _actual_ corruption of countries, but rather their residents' and political experts' perceptions of corruption. Because this part of our data is based on human perceptions, it makes the data less reliable; especially when we consider that the corruption dataset takes into account most countries in the world. Although our political corruption dataset claims to take measures to squash the variability in human perceptions (like cross comparing countries' corruption scores) it's important to note the possibility of unreliable data.

Another thing to take into consideration is the differences in climate around the world. For example, Brazil and Canada have two vastly different ecological systems, which means that even if those two countries had the same political corruption score, that corruption could have massively different effects on the ecological system of that country.

It is unlikely for this project to have any adverse impact on the various stakeholders. On one hand, even if little to no correlation is found it would not change the fact that lack of transparency as well as environmental decline are both still negative phenomenons in need of reform. On the other hand, insightful results could illuminate potential areas of focus for environmental groups to target.

This experiment has given insight into the relationship between government corruption and environmental health. Overall, government corruption and environmental health have shown to have a consistent relationship and thus, it's important to every living organism on the planet that we understand it. Government regulations and having the resources to enforce those regulations are seemingly simple concepts, but many developed countries are still struggling with judicial effectiveness and accountability.

### References

Bertelsmann Stiftung. (2026). The Transformation Index. BTI Transformation Index. https://bti-project.org/en/

Block, S., Emerson, J. W., Esty, D. C., de Sherbinin, A., Wendling, Z. A., et al. (2024). 2024 Environmental Performance Index. Yale Center for Environmental Law & Policy. epi.yale.edu

Dieckman, E. (2025, April 30). Climate Change Heightened Conditions of South Korean Fires. Eos. https://eos.org/articles/climate-change-heightened-conditions-of-south-korean-fires

Economist Enterprise EIU. (2025). Who we help: Industry research, insights & solutions. https://www.eiu.com/n/who-we-help/

Igini, M. (2025, October 14). Global Coral Reefs Face ‘Widespread Death’ As Warming Planet Pushes System Beyond What It Can Cope With. Earth.Org. https://earth.org/global-coral-reefs-face-widespread-death-as-warming-planet-pushes-system-beyond-what-it-can-cope-with/

Marfin, C., Jimenez, J., & Steele, T. (2021, February 16). Hundreds of thousands remain without power as more snow is headed to Dallas-Fort Worth on heels of record cold. The Dallas Morning News. https://www.dallasnews.com/news/weather/2021/02/16/thousands-still-without-power-as-north-texas-reaches-record-low-temperature/

Public Safety Canada. (2025, October 30). Government of Canada provides update on 2025 wildfires as support continues. Government of Canada. https://www.canada.ca/en/public-safety-canada/news/2025/10/government-of-canada-provides-update-on-2025-wildfires-as-support-continues.html

S&P Global. (2024). Global Risk & Economics Solutions. https://www.spglobal.com/market-intelligence/en/solutions/global-risk-and-economics

The PRS Group. (2025). Our Products: The International Country Risk Guide (ICRG). https://www.prsgroup.com/explore-our-products/icrg/

Transparency International. (2025, February). Corruption Perceptions Index. https://www.transparency.org/en/cpi/2025

Varieties of Democracy. (2025). Varieties of Democracy (V-Dem). V-Dem: Varieties of Democracy. https://v-dem.net/

World Economic Forum. (2025). Who we are. https://www.weforum.org/about/world-economic-forum/

World Justice Project. (2025). About us. https://worldjusticeproject.org/about-us

### Resources

GeeksforGeeks. “CatBoost in Machine Learning.” GeeksforGeeks, 20 Jan. 2021, 
www.geeksforgeeks.org/machine-learning/catboost-ml/.  

GeeksforGeeks. “Random Forest Algorithm in Machine Learning.” GeeksforGeeks, 22 Feb. 2024, www.geeksforgeeks.org/machine-learning/random-forest-algorithm-in-machine-learning/ 

GeeksforGeeks. “XGBoost.” GeeksforGeeks, 18 Sept. 2021, 
www.geeksforgeeks.org/machine-learning/xgboost/.


### Code Repo

[Code here](https://github.com/p-hall1904/Final-Project/blob/f6d5f786e406efb00337544412fc47afc6ad97fd/Final%20project%20code.ipynb)

### AI Transparency

Claude Sonnet 4.6 was used to help debug and build visualizations. All interpretations were done by us as a group.
