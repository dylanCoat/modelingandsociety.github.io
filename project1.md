# Problem Definition
In the United States and abroad I've noticed a steady increase in top-down anti-LGBTQ+ sentiment. This is to say that it's a project by those who hold power, not the everyday individual. I'd seen reporting that this mostly coincided with the 2021-2022 election cycle, with trans rights as a specific target. In setting out on this project I sought to answer two questions, with a bonus one if time allowed: How has the amount of state-level anti-LGBTQ+ legislation changed over time, where, and to what effectiveness?

# Data Description
When looking for datatsets I found [this excellent table](https://doi.org/10.25949/24190026) by Dr. Tiffany Jones of Macquarie University. It is a compilation of anti-LGBTQ+ bills introduced into state (and Puerto Rico's) legislatures through 2018 to 2025, with a basic description of the bills targets and progress. Keep in mind that this is _state level_, so neither federal legislation, executive orders, nor court decisions will be represented here. Here's a screenshot of the first row, for reference:

![Screenshot of the first row of the linked dataset](./docs/assets/Spreadsheet_peek.png)

You can see that the 'Form' column provides a category of the bill's impact, while the 'Status' column has a brief summary of its status. Both of these columns are tricky because they don't adhere to a consistent format throughout the the set—any working with those columns will require working with keywords.

Now a caveat: I am not familiar with Dr. Jones and have not personally verified that this data is comprehensive. It is possible that she made a mistake or that her judgement of what qualifies as anti-LGBTQ+ is flawed. She does specialize in LGBTQ+ policy but is located in Australia, so her familiarity with US state governments may be lacking as well. All in all, this data may underrepresent reality.

# Data Cleaning & Preparation
The nature of this data meant that cleaning was not much of an issue. All of the information is public records with no sensitive or identifying qualities. There were no missing values and everything in the set was relevant to the topic—apart from the inclusion of Puerto Rico. I'm not familiar with Puerto Rican government and decided to stick to just US states. I dropped every row from Puerto Rico, but there were only 3 to begin with.

The main difficult part here was getting the data in a format agreeable to Python and Pandas. The way tht the data is gathered in a table and separated by year, along with the fact that it's in a .docx file, meant that I had to do some work before getting into VSCode. I copied the data in a spreadsheet and added a new column, 'Year', so that I could have everything sorted without repeat columns.

# Data Understanding & Visualization
The first thing I wanted to explore was if my hypothesis—that anti-LGBTQ+ legislation has significantly increased, and if so coinciding with election cycles—was true. To do that I created a histogram showing the amount  introduced over time.

![Histogram showing year on the x axis and count on the y axis. Numbers are insignificant from 2018-2020, but double to around 150 by 2021. They jump again between '22 and '24 to over 500, with another increase to over 600 by 2025](docs/assets/bills_per_year.png)

And it seems like my hypothesis was correct. Numbers are somewhat insignificant from '18-'20, but double for the '21-'22 cycle. They rocket again for the next cycle, then noticeably shift for the next. I'll get to what this might mean in the next section, but whoof. This is grim.

I next wanted to look at the state level. Where was it the worst, and where was it the best? To do this I created count plots of the top 10 for each respective end of the spectrum. For reference, the total number of bills is 2,199.

![Plot of the top 10 states in terms of bills intro'd. In order is Texas, Missouri, Oklahoma, Tennessee, Iowa, West Virginia, South Carolina, Mississippi, Kentucky, and Wisconsin, ranging from around 180 to 60](docs/assets/bigoted_states.png) ![Plot of the bottom 10 states in terms of bills intro'd. In descending order is New Mexico, Maine, Nebraska, Maryland, California, Nevada, Delaware, Vermont, and New York, with the first three tied at 12 and bottom sitting at 4](docs/assets/feckless_states.png)

Some of what you see here might line up with what you expect, but I personally was surprised to see Wisconsin in the top and Nebraska in the bottom. Of course, it's also supremely disappointing for no state to be at 0. Once again, deeper interpretation is for next section. Below is a plot with every state on it; it's messy to read and not something I initially intended to include, but I accidentally made it then figured it may be of interest.

![Plot of every state. I don't really believe anyone's actually going to use the alt text but my deepest apologies if you need it; I'm pressed for time here](docs/assets/american_century_of_humiliation.png)

I'd love to go deeper on the status of the bills, but dealing with the author's inconsistent descriptions meant that I couldn't be confident I could provide a fully-accurate depiction. Instead I moved on to my sub-question; how have trans rights, specifically, been represented here? I return once again with a plot based on years, this time focusing on bills the author classified with these phrases: "Single-sex", "TGD" (shortening of "transgender"), and "ID" (as ID laws are meant to target transgender individuals). This may not be a completely comprehensive capture, but it's the way the author classified the entries.

