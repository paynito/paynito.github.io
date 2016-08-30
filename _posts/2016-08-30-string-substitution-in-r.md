---
layout: post
title:  "String Substitution in R"
ref: strings1
date:   2016-08-30 09:48:44 +0100
categories: stats
lang: en
excerpt_separator: ""
---
{% highlight R %}
#! /usr/opt/local/bin/R
# manual way to open files
f606 <-spss.get("~/school/census1/f606/f606ind.por", use.value.labels = TRUE)   #2006
f607 <-spss.get("~/school/census1/f607/f607ind.por", use.value.labels = TRUE)   #2007
f608 <-spss.get("~/school/census1/f608/f608ind.por", use.value.labels = TRUE)   #2008
f609 <-spss.get("~/school/census1/f609/f609ind.por", use.value.labels = TRUE)   #2009
# attempts to automate
dates <- 606:609
for (file in dates){print(paste("f",file))}
[1] "f 606"
[1] "f 607"
[1] "f 608"
[1] "f 609"
sprintf("f%s <-spss.get(\"~/dir/f%s/f%sind.por\", use.value.labels = TRUE)", dates[1], dates[1], dates[1])
[1]"f606 <-spss.get(\"~/dir/f606/f606ind.por\", use.value.labels = TRUE)"
# now to make that a command instead of a string
# then to loop
{% endhighlight %}

^
<!--more-->
Say something. Document the code here. What is this post saying?
I felt like in Ruby I could loop through some files and open them quite easily.

{% highlight bash %}
#! /usr/bin/bash
cd ~/scratch
touch 1.por
touch 2.por
touch 3.por
{% endhighlight %}

^

<!--more-->
After creating the files we attempt to open them.

{% highlight ruby %}
for i in 1..3
    puts "f#{i} <- /dir/#{i}.txt"
end
f1 <- /dir/1.txt
f2 <- /dir/2.txt
f3 <- /dir/3.txt
##
for i in 1..3
    File.open "#{i}.por"
end
{%endhighlight%}

^
<!--more-->
Back to Bash.

{% highlight bash %}
~ git:(master)  cd scratch
scratch git:(master)  mkdir f1
scratch git:(master)  mkdir f2
scratch git:(master)  mkdir f3
scratch git:(master)  mkdir dir
scratch git:(master)  mv f1 dir/f1
scratch git:(master)  mv f2 dir/f2
scratch git:(master)  mv f3 dir/f3
scratch git:(master)  mv 1.por dir/f1/1.por
scratch git:(master)  mv 2.por dir/f2/2.por
scratch git:(master)  mv 3.por dir/f3/3.por
{% endhighlight %}
^
Back to Ruby.

{% highlight ruby %}
Dir.glob("*.por")
# => ["1.por", "2.por", "3.por"]
for i in 1..3 do
    index_val = " I have #{i}"
    instance_variable_set("@dataset#{i}", index_val)
    @dataset#{i} = file.open "#{i}.por"
end
Dir.glob("**/*/*.por")
# => ["dir/f1/1.por", "dir/f2/2.por", "dir/f3/3.por"]
for i in 1..3 do
    index_val = " I have #{i}"
    instance_variable_set("@dataset#{i}", index_val)
    @dataset#{i} = file.open "/dir/f#{i}/#{i}.por"
end
{% endhighlight %}
^
OK, that was actually much harder than I remembered ruby for loops being.
Will I need such an instance variables trick to increment over var names in R as well?  Maybe my time would have been better spent looking for the get() function that was suggested on g+.