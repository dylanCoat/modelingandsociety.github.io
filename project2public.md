# Project Intro
Building off of my last project, I wanted to examine potential causes behind why some states are worse than others with regards to transgender rights. To do this I compiled basic political information about every state, like their governor's party, legislature's dominant party, 2024 president vote, and more. And while transgender rights exist on a continuum, I needed a binary measure. I once again used Erin Reed's (2026) Adult Anti Trans Legal Risk Assessment Map, seen here:

![Risk assessment map, sorry don't have time for alt text](./docs/assets/anti_trans_risk_assessment_map.png)

I separated it into two categories. Every state deemed high-risk or worse is categorized as high-risk in my data, while all else is not high-risk.

# Findings
To try to weigh the importance of each variable, I used a decision tree. A decision tree decides the most important variable and splits the data according to it, then repeats the process with different variables until each path all belongs to the same category. You can see the results of my most accurate tree here:

![](./docs/assets/tree_2.png)

Keep in mind that this is true for 40 states; the final 10 are reserved to test the model's accuracy. Essentially what this is saying is that of my variables, the most important one is which party controls the state's government. States with Republican control (and Nebraska, which is ostensibly non-partisan) all are high-risk states. The only state to be high-risk but not controlled by conservatives is that which has a Republican legislature and a population below 3,792,042 (an arbitrary threshold). But before I talk more about the results here, we need to first be aware of how accurate this model actually is. With the final 10 states, all but 1 were correctly categorized by the tree. That's pretty good, but then again there being only 50 states mean that it's pretty easy for a model to do well. Disappointingly, this model tells me no insightful information. Of course total control of the government is important. The only interesting thing here is the final step, where it separates what makes a Republican legislature pass these laws, but even there it could just be coincidence that the least-populous state of the 5 happens to be the only one high-risk.

I decided that perhaps state control was too obvious of a varaible and wanted to see how a tree would look without it. I tried another tree removing that variable, while also increasing the amount of states reserved for testing the model. Here is the tree that formed:



Works cited
https://ballotpedia.org/State_supreme_courts#sscinfo-listofcourts-1
https://www.ncsl.org/about-state-legislatures/state-partisan-composition
https://williamsinstitute.law.ucla.edu/wp-content/uploads/Trans-Adults-US-Aug-2016.pdf
https://www.erininthemorning.com/p/anti-trans-national-legal-risk-assessment-a5d
