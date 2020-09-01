# Indigo Slate Programming Puzzle!

Exported to Devops on 09/01/2020

Thank you for your interest in working with us at Indigo Slate!  As part of the interview process, we'd like you to to tackle this problem for us.  There are two parts to the problem, please answer at least the first.


# Motivation

Large retailers might have product lists with more than a million individual items for sale.  Amazon has more than 500 million!

Each item may have a heirarchical category assigned to it, for instance "electronics > computers > laptops".  Today, some one has come to you and asked you to process a text file containing products and categories, and they would like to know **how many items are at each level of the heirarchy and what the average cost of those items is**.   

# Data 

Please download the sample data set from Kaggle: https://www.kaggle.com/PromptCloudHQ/toy-products-on-amazon

  - The file is 10,000 lines long, but any solution you create should work equally well on a file that is 500 million lines long.
  - The most important fields in that file are **amazon_category_and_sub_category** (the category), and **price**.
  - As usual, data is noisy.  Some items may lack a category, in which case you can bucket them under 'uncategorized'.  Some items may not have prices, in which case you should count the item, but not include it in the average price.
  
# Part 1

Write a command line utility that takes an input file (provided above) and outputs a heirarchical list of categories & the counts & averages.

For example, if there were only three lines like this:

```
product_number,category_price
1,Games > Dice & Dice Games,$10
2,Games > Board Games,$15
3,Toys > Fidget Spinners,$5
```
Then the output would look like this:

```
category,count,avg_price
[all],3,$10
Games,2,$12.50
Games > Board Games,1,$15
Games > Dice & Dice Games,1,$10
Toys,1,$5
Toys > Fidget Spinners,1,$5
```

***Notice that each item can contribute to more than one bucket.***  For instance, item #2 would add to the [all] bucket, as well as Games, and Games > Board Games.

# Part 2

For bonus marks, take the output from Part 1 and build a REST API that does the following: Given a specific category, return a JSON blob that contains the count & average price.  

Your service just has to run locally -- but you'll need to supply instructions on how to start and test your service, and any requirements.  The specifics here are left intentionally vague -- what do you think the best solution is?  You tell me.

The service only has to implement a single function, and it will take a category (in some format, you decide) and output a json blob with the # of items in that category.

# Submitting your solution
Please create a github repository and send us a link.  Include a readme.md file so we know how to use your code.

# Common questions

- *"What technology/language should I use?"* - your interviewer or recruiter will give you direction here.
- *"Do I have to do both parts?"* - we understand that you are busy.  We'd love for you to tackle both parts, but if your time is limited, you can just take on part 1.
- *"How long should this take?"* - Part 1 is a real question asked of the author at work. It took about 30 minutes to complete.   Part 2 shouldn't take more than 30-60 minutes if you are familiar with a web framework.
- *"What quality bar should I aim for"* - We are looking for an understanding of how to manage & manipulate data, and setting up a basic web interaction.  Your code should have no obvious bugs, and any known limitations should be documented.  That said, this isn't intended as production code, and we won't be judging you based on handling every little possibility in the REST interaction, for instance.  
