---
layout: post
title:  "Linear Regression in Python"
ref: postTwo
date:   2016-10-12 09:48:44 +0100
categories: course stats python gapMinder
lang: en
excerpt_separator: ""
---
# Assignment 2:["Regression Modeling in Practice"](https://www.coursera.org/learn/regression-modeling-practice)

This week's assignment asks you to test a basic linear regression model for the association between 
your primary explanatory variable and a response variable, and to create a blog entry describing your results.

{% highlight python %}
modelname = smf.ols(formula='QUANT_RESPONSE ~ QUANT_EXPLANATORY',
data =dataframe).fit()
print(modelname.summary())
{% endhighlight %}