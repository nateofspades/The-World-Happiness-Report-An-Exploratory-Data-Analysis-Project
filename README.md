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

### My Learnings in Hindsight
I completed this project in 2018. Looking back on it now, with an extra year of experience in data science, I would do a number of things differently, such as: 
•Write my code under the functional programming paradigm. 
•More appropriately use whitespace in my code to make it more human-readable. 
•Use more descriptive variable-naming conventions. 
•Spend more time investigating the unintuitive evaluation system for the 6 characteristics and the target, and then replace it with an intuitive one (for example, a 0 to 10 scale by applying an appropriate linear transformation). The current system has all of the characteristics in this particular dataset ranging from 0 to 1.82, and claims that the target by definition ranges from 0 to 10. It's not clear from this information what the range of acceptable characteristic values is then; if it is, say, 0 to 2, then this would suggest a maximum happiness of at least 6x2=12 (contradiction).
•Reduce how many of the code outputs were included. For example, it's not necessary to display the dataframe structure for each of the 2015, 2016 and 2017 tables (which are similar to one another), or the numerical index used to represent Hong Kong.
•Better organize the data preprocessing; group related steps into fewer code blocks, and provide less output tables related to demonstrating why particular preprocessing steps are taken.


•Fix the scale of each of the 6 characteristics. The scale provided by the WHR has no obvious intuition behind it, with values ranging from 0 to 1.82. I would adjust this to a scale ranging from 0 to 10 by multiplying all of the characteristic values by 10/1.82.
•Look deeper into how the the values for the characteristics and happiness rating are defined in the WHR. The lowest happiness rating of all countries in, say 2017, is 1.85, and

However, it's not clear from the data what maximum value a characteristic can actually take (is the range 0 to 2?) and therefore what maximum value the happiness rating should be able to take if we are going to rescale happiness rating to something more intuitive.

this value wasn't computed from the 6 characteristics, and so there is no obvious intution about how to relate the newly-scaled characteristics to happiness rating.
