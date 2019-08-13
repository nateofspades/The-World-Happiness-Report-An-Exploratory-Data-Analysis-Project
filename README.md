# The World Happiness Report - EDA

The project can be seen in the .ipynb file.

### Introduction
This EDA project looks at data from the 2015, 2016 and 2017 iterations of the World Happiness Report to see how various characteristics of a country correlate with the mean subjective happiness scores of a country. It also uses the ggmap API to extract map data. The WHR data and the ggmap data were relatively clean in isolation, but some data preprocessing had to be done when joining the two.

### The Characteristics (at the level of countries) <br />
•GDP per capita <br />
•Family quality <br />
•Health <br />
•Freedom <br />
•Generosity  of citizens <br />
•Trust in government

### The Target Variable (at the level of countries)  <br />
•Mean subjective happiness score

### Happiness Heat Map
A heat map of the world where countries are colored by their happiness scores reveals a strong positive correlation between how developed a country is and how happy its average citizen is. Australia, New Zealand, North America and Western Europe are the happiest regions of the world, while Sub-Saharan Africa and Southern Asia are the least happy regions of the world.

### Predictors of Happiness
•GDP, health and family quality each showed an undeniable positive correlation with happiness. <br /> 
•How much personal freedom the average individual experience also shows a positive correlation with happiness, but not quite as strong. <br />
•When trust in government is low, there is no linear relationship between trust in government and happiness, but when trust in government is higher, there is a positive correlation. <br />
•There is no correlation between how generous the average citizen is and happiness.

### Correlation Matrix
The characteristics were all pairwise positively correlated, except for the Generosity/GDP pair (correlation: -0.01). The largest of all of these pairwise correlations was 0.78, but the next two largest were 0.58 and 0.48, so multicollinearity probably wouldn't be too big of an issue if this  were extended to a machine learning project.

### Multivariate Heat Maps
This part of the project looks further into the top three predictors of happiness: GDP, health and family. For each of the three pairs of these predictors a heat map is built, where the x and y coordinates correspond to the two predictors in question and the color corresponds to happiness. What was found is that as any two of these three predictors increase, there is an unmistakeable rise in happiness. Furthermore, when any of the three predictors is compared to happiness by region (where a region corresponds to multiple countries), a similar trend is seen within each region: as the characteristic improves, happiness increases.

### What I Learned in Hindsight
I completed this project in 2018. Looking back on it now, with an extra year of experience in data science, I would do a number of things differently, such as: <br /> <br />
•Write my code under the functional programming paradigm; a lot of duplication of code could be avoided (for example when building and plotting various similar linear regression models - the current code blocks for these are long and messy). <br />
•More appropriately use whitespace in my code to make it more human-readable. <br /> 
•Use more descriptive variable-naming conventions. <br /> 
•Spend more time investigating the unintuitive evaluation system for the 6 characteristics and the target, and then replace it with an intuitive one (for example, a 0 to 10 scale by applying an appropriate linear transformation). The current system has all of the characteristics in this particular dataset ranging from 0 to 1.82, and claims that the target by definition ranges from 0 to 10. It's not clear from this information what the range of acceptable characteristic values is then; if it is, say, 0 to 2, then this would suggest a maximum happiness of at least 6x2=12 (contradiction). <br />
•Reduce how many of the code outputs were included. For example, it's not necessary to display the dataframe structure for each of the 2015, 2016 and 2017 tables (which are similar to one another), or the numerical index used to represent Hong Kong. <br />
•Better organize the data preprocessing; group related steps into fewer code blocks. <br />
•Rather than partitioning the data into a training set and a test set, I would retain the original dataset as one, and focus this project entirely on EDA; the dataset is too small to perform the Holdout Method respectably. <br />
•Fix the univariate analysis of the 6 characteristics by including a separate scatterplot for each of the 3 years. This would show that the distribution for each characteristic is similar from one year to the next. To improve aesthetics, I would also create these visualizations in ggplot rather than base R (that is, if I were to redo this project in R rather than Python). <br />
•Fix the resolution of the Happiness Boxplots by Region and World Happiness by Country visualizations. Both have a height:width ratio which is too high, making them less attractive and more difficult to read. <br />
•Fix the size of the above visualizations, as well as correlation matrix; they are too big and therefore difficult to read at once.
