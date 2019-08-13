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

### The target variable (at the level of countries)  <br />
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
