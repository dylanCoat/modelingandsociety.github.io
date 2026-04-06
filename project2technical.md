#### lowkey still working on this, pls have mercy, it'll be done in an hour or two
# The Dataset
Ultimately I wanted to gather up several political and social factors in order to explore feature importance for what caused a state to be high-risk to transgender people. The dataset is comprised of several sources that I put together, you can find them at the bottom of this page. The file for the full data can be found [here](./docs/assets/trans_risk.ods) but below is a screenshot of every column name:

![still no time for alt text, sorry!](./docs/assets/project_columns.png)

A lot of this data, like the Mandatory Retirement Age column, is stuff that I never intended to use. It came with the data I was trying to find, so I figured I may as well include it and let the model sort through what matters. As you'll see, this was not a good idea.

# The Workflow
The data was already organized properly due to myself being the one to compile it in a spreadsheet. The first step here was to handle null values.
