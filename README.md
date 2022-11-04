Written by: Yu Fan, Aaron Tsang, Max Mai, Jeyshinee Pyneeandee

## Analysis on variables affecting mental health during the COVID-19 pandemic in BC

### Introduction
● Motivation
COVID-19 has affected everybody’s life considerably for the past 2 years and has had
devastating consequences too. Now that the PHO has removed the mask mandate and will be
removing the Vaccine Passport program soon, this study aims at what COVID-19’s impacts
are on the mental health of British Columbia residents. This study involves three explanatory
variables: age, gender and underlying health conditions. The response variable is the
percentage of the population who feel that their mental health status has changed for the
worse, following the pandemic.
● Data collected
This study is an observational study, we selected three categorical variables as our
explanatory variables. All the data were collected by Statistics Canada, the collection period
is September 2020 to September 2021 through surveys. We were able to access the data by
going through StatsCan and selecting the wanted explanatory and response variable. We
accessed an overall data set including all three variables and additional data sets where we set
all but one variable to an “overall” group so we could isolate that one variable. Below is a
brief description of the variables we were using in our models:
➢ Age
A categorical variable with 4 levels: 18 to 34 years, 35 to 49 years, 50 to 69 years, 70
years and older. We choose the 18 to 34 years group as the baseline. Age was chosen
because different age groups were impacted differently by the pandemic. For
example, certain groups were probably worried about income loss, others about
school. All these might have impacted their mental health differently.
➢ Gender
A categorical variable with 2 levels: Male, Female. We choose male as the baseline.
Gender was chosen because it is possible that gender may play a different role in how
Yu Fan, Aaron Tsang, Max Mai, Jeyshinee Pyneeandee
people deal with mental stress and, in turn, may affect mental health status. We want
to eliminate the possibility of this as much as possible.
➢ Underlying health conditions
A categorical variable with 2 levels: Yes, No. We choose no as the baseline. Health
conditions were chosen because having any particular condition already might affect
how people emotionally reacted to a pandemic and its consequences.
● Models
Our study involves a total of 3 models, baseline model with no interaction terms, model 1
with an interaction term between gender and health conditions, and model 2 includes an
interaction term between age and health conditions
The models fitted are shown below:
➢ Baseline Model:
𝑌 = β0 + β1𝑎𝑔𝑒1 + β2 𝑎𝑔𝑒2 + β3𝑎𝑔𝑒3 + β4𝑔𝑒𝑛𝑑𝑒𝑟𝑓 + β5ℎ𝑒𝑎𝑙𝑡ℎ𝑛𝑜
➢ Model 1:
𝑌 = β0 + β1𝑎𝑔𝑒1 + β2 𝑎𝑔𝑒2 + β3𝑎𝑔𝑒3 + β4𝑔𝑒𝑛𝑑𝑒𝑟𝑓 + β5ℎ𝑒𝑎𝑙𝑡ℎ𝑛𝑜 + β6 𝑔𝑒𝑛𝑑𝑒𝑟𝑓ℎ𝑒𝑎𝑙𝑡ℎ𝑛𝑜
➢ Model 2:
𝑌 = β0 + β1𝑎𝑔𝑒1 + β2 𝑎𝑔𝑒2 + β3𝑎𝑔𝑒3 + β4𝑔𝑒𝑛𝑑𝑒𝑟𝑓 + β5ℎ𝑒𝑎𝑙𝑡ℎ𝑛𝑜 + β6𝑎𝑔𝑒1ℎ𝑒𝑎𝑙𝑡ℎ𝑛𝑜 + β7𝑎𝑔𝑒2ℎ𝑒𝑎𝑙𝑡ℎ𝑛𝑜 + β8𝑎𝑔𝑒3ℎ𝑒𝑎𝑙𝑡ℎ

### Analysis
In order to provide a visualization on our categorical variables versus the percentage of
people with worsened mental health, we’ve decided to isolate each variable (age, gender,
underlying health condition) while keeping the rest constant to provide a visualization of each
respective group’s percentage of people having worse mental health compared to
pre-pandemic. We wanted to use boxplots to give a visualization of where each category’s
mean percent of people with worse mental health since pre-pandemic. By visually comparing
and using R to find the means of each category, we’re able to much easier understand why
certain coefficients of the models are positive or negative.
% of people with worse mental health than pre-pandemic categorized by whether they have an
underlying health condition

Through calculations of the mean of the categories Yes and No, we observed that the mean of
the category No is greater than Yes. This was an unexpected result compared to our model
because we are using the No underlying health conditions as the base line. We think that this
may be due to the case of collinearity with other variables such as Age which may have
affected the coefficient. Regardless, we observed that if we were to keep all other variables
constant except the underlying health condition, there is a greater average of people with
worse mental health when they do not have an underlying health condition.
% of people with a worse mental health than pre-pandemic categorized by age group
When isolating the categorical variable, Age groups, we observed that the category with the
highest percentage average of people with worse mental health than pre-pandemic are people
ages 35 to 49 followed by age group 50 to 69, 18 to 34 and finally the age group of 70+. We
believe this is exactly what we expected based on our model using the age group 18-34 as the
baseline as well as in real situations. We think that the reason why the first three age groups
Yu Fan, Aaron Tsang, Max Mai, Jeyshinee Pyneeandee
have the highest mean is because their livelihood/ social life is greatly affected due to the
COVID-19 shutdowns and indoor restrictions. However, a different study that includes
income would be required to back up our reasoning.
% of people with a worse mental health than pre-pandemic categorized by gender
As we can clearly see through the box plot to compare the categories of gender (Male,
Female) and the mean of each category calculated through R, this is the expected signs when
comparing the differences of the mean when isolating each gender. The reason why the base
model’s coefficient for the gender variable is positive is because we are using the gender
Male as the baseline. From both the equation of the regression and this boxplot, we can
deduce that the percentage of women whose mental health has worsened is much more than
males.

We then continue by fitting a regression model which we will call the base model (base_reg).
This model includes no interaction between any of the 3 variables. We have decided to take
the age group of 18-34, male gender and not having an underlying health condition as the
baseline for the models.
We can note that the adjusted R-squared value of our base model is 0.4566. By
looking at the above output and comparing the p-values, we can see that the intercept and the
Gender variables are both very significant (***) and so is the Age variable at level 3 (which
is people aged 70 years and older) and at level 1(people aged between 35 and 49 years old).
However, we can also see that the Age variable at level 2, which is people aged between 50
and 69 years old) and the Underlying Health variable have relatively larger P-values which
might suggest that they are not as significant. This might also suggest that there might be
some interaction between these two variables.
We can further investigate by re-fitting the model (model1_reg) and this time,
including the interaction between Age and Underlying health. We decided to use the
interaction between age and underlying health because one may influence the other.

We can note that the adjusted R-squared decreased, but not by a significant amount, to
0.4505. The decrease of the adjusted R-squared value can be interpreted as the addition of the
extra variable may indicate that it is not a good idea to include it because it does not add
“value” to the model in explaining the response variable.
The P-values of this model are clearly different from the base/previous model. The
increased P-values could possibly be due to collinearity between variables. It makes sense
that there may be signs of multicollinearity between having an underlying health condition
and age. As people get older, it is more likely for the person to have an underlying health
condition. The increase may also be due to the loss of degrees of freedom which when
estimating more parameters, costs us precision which leads to a lower t-statistic and thus
higher p-values.
Another pair of variables that might have some underlying interaction is Gender and
Underlying Health conditions. E.g., females can be more prone to certain medical conditions
such as breast cancer and strokes, while males can be more prone to lung cancer. We explore
that by fitting another model (model2_reg).

The adjusted R-squared value has now increased to 0.4666. In this model, the increased
adjusted r-squared value indicates that the inclusion of the interaction between gender and
underlying health condition is beneficial in explaining the response variable, the percentage
of people whose current mental health is worse than pre-pandemic.
In this model the following variables are considered statistically significant, intercept, age
group 1 (35-49 years), Age group 3 (70 and older) and gender. The p values of the variables
compared to the base model are not that different thus this suggests that the change in
p-values is likely to be caused by the loss of degrees of freedom rather than collinearity.
Comparing the summary of the three models, it would seem that model2_reg is so far
considered the “best” model based on the adjusted R-squared value. The adjusted R-squared
is used to explain the variation of the response variable based on the parameters. Thus, by
maximizing this value, the model with the largest adjusted R-squared is generally considered
a better fit.
Another quick analysis can also be done to compare
We can also further compare between these variables and models by calculating Mallows’ CP
for each.

For model 1: p + 1 = 3, Mallows’ CP =23.424
For model 2: p + 1 = 4, Mallows’ CP = 9.930
For model 3: p + 1 = 5, Mallows’ CP = 4.132
For model 4: p + 1 = 6, Mallows’ CP = 3.913
For model 5: p + 1 = 7, Mallows’ CP = 5.496
For model 6: p + 1 = 8, Mallows’ CP = 7.000
We can see from the above that model 3 has a value for Mallow’s Cp (4.13) that is closest to
p +1 (5), which indicates that it is the best model that leads to the least amount of bias
among the 6 potential models. Model 3 is the model which includes the intercept, with Age
and Gender as variables.

### Conclusion:
In conclusion, we can see that COVID-19 has affected the mental health of people from
different groups variously. We can see from the boxplots above, people ages from 35-49,
people whose gender is female and people who do NOT have underlying health conditions
seem to have worse mental health status during the pandemic. As for the models above we
fitted, we conclude that model 2 is the “best” fitted model among the three, which includes an
interaction term between age and underlying health conditions, with intercept, age group 1
(35-49 years), Age group 3 (70 and older) and gender as significant variables. The reason that
we consider model 2 as the best model is that the model has the greatest adjusted R-squared
value. We compare the adjusted R-squared value rather than R-squared because adjusted R^2
is able to penalize usage of useless variables where as R-squared will increases as # of
variables increase which is not a good way to compare models of different sizes. At last, by
calculating Mallows’ CP, we can see the best model should include age1(35 to 49 years old),
age3(70 years old or above) and gender as variables.
To conclude our research, through our methods of finding the regression model and providing
visualizations on our categorical variables, the variables age, gender and underlying health
conditions played a role in the mental wellbeing of people during the pandemic. By setting
the age group 18-34, male and no underlying health condition as the baseline we have
observed that there is a higher percentage of people with worse mental health in the age
groups 18 to 34 years, 35 to 49 years, 50 to 69 years except 70 years and older. There is also a
higher percentage in female individuals and when people have an underlying health
condition.
