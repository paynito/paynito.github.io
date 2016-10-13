---
layout: post
title:  "PostOne - Describe Data Set"
ref: postOne
date:   2016-10-10 09:48:44 +0100
categories: course, stats, python, gapMinder
lang: en
excerpt_separator: ""
---
Assignment 1 for course "Regression Modeling in Practice"
https://www.coursera.org/learn/regression-modeling-practice
Blog for assignment: How to Write About Your Data

# describe
 a)sample
   i) who or what was studied (people/animals)

 The dataset I am using for this course is a /portion of the GapMinder dataset/.
 Information about how the individual indicators are studied and calculated is available at
 https://www.gapminder.org/data/documentation/#gd001

# The complete GapMinder dataset inclues information on all 192 UN member nations
 and 24 other areas, for a total of 215 areas.
 It includes more than 200 indicators.

# The excerpted portion utilized in this course includes
 
## 15 variables:
 1. 2010 GDP/person
 2. 2008 alcohol consumption/person
 3. % of labour force in the military
 4. 2002 new cases of breast cancer/100,000 females residents
 5. 2006 cumulative CO2 emissions
 6. 2007 female employment rate
 7. 2007 total employment rate
 8. 2009 estimated HIV rate
 9. 2010 internet connectivity rate (/100 people)
 10. 2011 life expectancy at birth
 11. 2010 oil consumption (tonnes/yr/person)
 12. 2009 polity score (ranges from -10 autocracy to 10 democracy)
 13. 2008 residental electricity usage (kWh/year/person)
 14. 2005 suicide rate
 15. 2008 urban rate

## sample
  * what level of analysis  (individual/group/aggregate)
  
  This data is often reported in terms of meaningful units.
  The first two variables make sense in terms of individuals,
  the total GDP is calculated and then divided by the population
  to give the per-capita GDP figure, such as $1,064/person in Mozambique.
  Alcohol consumption is reported in liters/person/year. In the Czech
  Republic people above 15 years of age drink on average 13 liters of
  alcohol per year. The third variable does not make sense in terms
  of a per-person number. It's not that in some country you spend 97%
  of your time in a civilan job and 3% in the military. Instead, it
  means that out of 100 people in the labour force, 3 were employed by
  the military.

## all of these are quantitative variables

## procedure
  This varies widely by indicator and by country. The above mentioned
  alcohol consumption included both a survey, where people self-reported
  and empirical investigations and expert judgments. Czechs self-reported
  11.8 liters of alcohol consumption, but the experts estimated 1.2 liters
  of unrecorded consumption, to give the total of 13 liters.

## My Project:
  * my Variables and research Question:
    In this course I will be studying the relationship between oil consumption and breast cancer.
    I am using the data to test the hypothesis that burning oil in a country pollutes the air and
    increases breast cancer in the population.
  *the data collection procedure:
   1. data source: International Agency for Research on Cancer http://www.iarc.fr/
   again, varies by country, people go to the doctor/hospital, suveyor calls or emails hospital and asks, "How many new cases of
   cancer did you get this month?"
   2. British Petroleum's /World Statistical Review 2008/
    - includes data from OECD Commercial Inventories, etc.

## WHAT TO SUBMIT:

Following completion of the steps described above, create a blog entry and submit the URL. 
In your blog entry, you should describe your sample, the data collection procedure,
 and how you managed your data.
 
### Review criteria
DEADLINE: <2016-10-16 Sun>
Your assessment will be based on the evidence you provide that you have completed all of the steps.
 When relevant, gradients in the scoring will be available to reward clarity
 (for example, you will get one point for submitting text that indicates an attempt to 
address the the criteria for each step, but two points for being clear). 
In all cases, consider that the peer assessing your work is likely not an expert in the field
you are analyzing. You will be assessed equally for each step of the assignment. 


{% highlight ruby %}
puts "Thank you."
{% endhighlight %}