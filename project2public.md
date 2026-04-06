# Project Intro
Building off of my last project, I wanted to examine potential causes behind why some states are worse than others with regards to transgender rights. To do this I compiled basic political information about every state, like their governor's party, legislature's dominant party, 2024 president vote, and more. And while transgender rights exist on a continuum, I needed a binary measure. I once again used Erin Reed's (2026) Adult Anti Trans Legal Risk Assessment Map, seen here:

![Risk assessment map, sorry don't have time for alt text](./docs/assets/anti_trans_risk_assessment_map.png)

I separated it into two categories. All states rated high risk or worse were deemed as very risky, while all else were not.

# Findings
To try to weigh the importance of each variable, I used a decision tree. A decision tree decides the most important variable and splits the data according to it, then repeats the process with different variables until each path all belongs to the same category. You can see the results of my most accurate tree here:

Works cited
https://ballotpedia.org/State_supreme_courts#sscinfo-listofcourts-1
https://www.ncsl.org/about-state-legislatures/state-partisan-composition
https://williamsinstitute.law.ucla.edu/wp-content/uploads/Trans-Adults-US-Aug-2016.pdf
https://www.erininthemorning.com/p/anti-trans-national-legal-risk-assessment-a5d
