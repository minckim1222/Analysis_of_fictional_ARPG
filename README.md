# Analysis of Game Sales Data

Analysis was done on a fictional gaming company.  The company sells in-game items to players to improve their characters.  The analysis was done in a Jupyter Notebook file, using Python and Pandas.  [Here is a link to the final Jupyter Notebook file.](https://github.com/minckim1222/Analysis_of_fictional_ARPG/blob/master/heroes_of_pymoli/Heroes_of_PyMoli.ipynb)

### Initializing the database

The first step was to import the given dataset files into Pandas and converting them into a Pandas dataframe.  The given file sets were in JSON format.  Pandas `read_json` function was used to convert the JSON files into a PD dataframe.

### Gender analytics

The second step was to do basic analysis on the gender groups.  The three genders were: Male, Female, and Other.  Other is comprised of people who did not specify gender.  The genders were grouped and them put into a dataframe to show how many users of each gender made purchases.  Here is the intial table:

![Gender Members](https://github.com/minckim1222/Analysis_of_fictional_ARPG/blob/master/images/main_gender.png)

Now that I had the user count of each gender, I could then make a dataframe showing the purchase information per gender.  The dataframe shows total purchases, total purchase amount, average purchase amount, and normalized purchase amount.

![Gender Purchases](https://github.com/minckim1222/Analysis_of_fictional_ARPG/blob/master/images/gender_purchases.png)

### Age analysis

The users were broken down into 8 different age groups.  Analysis was done on each age group to see who spends the most money on the game.

![Age Statistics](https://github.com/minckim1222/Analysis_of_fictional_ARPG/blob/master/images/age_statistics.png)

### Top Sellers Analysis

The database was sorted by purchase amount to see who the top spending users were.  The top 5 users are:

![Top Five Users](https://github.com/minckim1222/Analysis_of_fictional_ARPG/blob/master/images/top_five_users.png)

Next, the top 5 selling items by amount and volume were sorted:

![Top Five Item Sales](https://github.com/minckim1222/Analysis_of_fictional_ARPG/blob/master/images/top_five_items.png)

![Top Five Items by Revenue](https://github.com/minckim1222/Analysis_of_fictional_ARPG/blob/master/images/top_five_items_revenue.png)


## Observations based on data

1)Age group 15 – 25 had the highest spending rate.  This makes sense because they would have the most disposable income relative to expenses.  High school students live at home and can use allowances/part time job money towards their hobby.  Age group 20-24 is comprised with older college students who may have secured internships that give decent pay and fresh graduates who have their first “real job” so they can splurge money.  As the age groups get older, the sales go down.  This can coincide with growing obligations as people age.  It’s not suprising that the oldest group spends the least, because it can be assumed older people have older kids that require more financial obligation.

2)Sales are dominated by males.  This is not surprising, as gaming as a hobby is dominated by males.  

3)The top item choices were interesting.  I do not have the specifics for the game, so its hard to analyze why certain items would sell more than others.  In my experience, weapons in RPGs tend to give player characters the most immediate impact.  Weapon upgrades tend to be #1 priority when gearing your character in RPGs.  It’s not surprising to see weapons dominating the top 5 purchases.  It is interesting that the #1 item is a gem.  That gem must be very versatile and powerful.
