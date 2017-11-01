# pandas_pandas_hw
Observations based on data

1)age group 15 – 25 had the highest spending rate.  This makes sense because they would have the most disposable income relative to expenses.  High school students live at home and can use allowances/part time job money towards their hobby.  Age group 20-24 is comprised with older college students who may have secured internships that give decent pay and fresh graduates who have their first “real job” so they can splurge money.  As the age groups get older, the sales go down.  This can coincide with growing obligations as people age.  It’s not suprising that the oldest group spends the least, because it can be assumed older people have older kids that require more financial obligation.

2)Sales are dominated by males.  This is not surprising, as gaming as a hobby is dominated by males.

3)The top item choices were interesting.  I do not have the specifics for the game, so its hard to analyze why certain items would sell more than others.  In my experience, weapons in RPGs tend to give player characters the most immediate impact.  Weapon upgrades tend to be #1 priority when gearing your character in RPGs.  It’s not surprising to see weapons dominating the top 5 purchases.  It is interesting that the #1 item is a gem.  That gem must be very versatile and powerful.



```python
#import dependencies
import pandas as pd
```


```python
#make json file readers
jsonfile = pd.read_json("purchase_data.json")
jsonfile2 = pd.read_json("purchase_data2.json")
```


```python
#make data frames with json
df1 = pd.DataFrame(jsonfile)
df2 = pd.DataFrame(jsonfile2)
```


```python
#headers for dfs make sure they ran
df1.head()
```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Age</th>
<th>Gender</th>
<th>Item ID</th>
<th>Item Name</th>
<th>Price</th>
<th>SN</th>
</tr>
</thead>
<tbody>
<tr>
<th>0</th>
<td>38</td>
<td>Male</td>
<td>165</td>
<td>Bone Crushing Silver Skewer</td>
<td>3.37</td>
<td>Aelalis34</td>
</tr>
<tr>
<th>1</th>
<td>21</td>
<td>Male</td>
<td>119</td>
<td>Stormbringer, Dark Blade of Ending Misery</td>
<td>2.32</td>
<td>Eolo46</td>
</tr>
<tr>
<th>2</th>
<td>34</td>
<td>Male</td>
<td>174</td>
<td>Primitive Blade</td>
<td>2.46</td>
<td>Assastnya25</td>
</tr>
<tr>
<th>3</th>
<td>21</td>
<td>Male</td>
<td>92</td>
<td>Final Critic</td>
<td>1.36</td>
<td>Pheusrical25</td>
</tr>
<tr>
<th>4</th>
<td>23</td>
<td>Male</td>
<td>63</td>
<td>Stormfury Mace</td>
<td>1.27</td>
<td>Aela59</td>
</tr>
</tbody>
</table>
</div>




```python
df2.head(5)
```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Age</th>
<th>Gender</th>
<th>Item ID</th>
<th>Item Name</th>
<th>Price</th>
<th>SN</th>
</tr>
</thead>
<tbody>
<tr>
<th>0</th>
<td>20</td>
<td>Male</td>
<td>93</td>
<td>Apocalyptic Battlescythe</td>
<td>4.49</td>
<td>Iloni35</td>
</tr>
<tr>
<th>1</th>
<td>21</td>
<td>Male</td>
<td>12</td>
<td>Dawne</td>
<td>3.36</td>
<td>Aidaira26</td>
</tr>
<tr>
<th>2</th>
<td>17</td>
<td>Male</td>
<td>5</td>
<td>Putrid Fan</td>
<td>2.63</td>
<td>Irim47</td>
</tr>
<tr>
<th>3</th>
<td>17</td>
<td>Male</td>
<td>123</td>
<td>Twilight's Carver</td>
<td>2.55</td>
<td>Irith83</td>
</tr>
<tr>
<th>4</th>
<td>22</td>
<td>Male</td>
<td>154</td>
<td>Feral Katana</td>
<td>4.11</td>
<td>Philodil43</td>
</tr>
</tbody>
</table>
</div>




```python
#merge the databases together
```


```python
merged_df = df1.append(df2, ignore_index = True)
merged_df.head()
```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Age</th>
<th>Gender</th>
<th>Item ID</th>
<th>Item Name</th>
<th>Price</th>
<th>SN</th>
</tr>
</thead>
<tbody>
<tr>
<th>0</th>
<td>38</td>
<td>Male</td>
<td>165</td>
<td>Bone Crushing Silver Skewer</td>
<td>3.37</td>
<td>Aelalis34</td>
</tr>
<tr>
<th>1</th>
<td>21</td>
<td>Male</td>
<td>119</td>
<td>Stormbringer, Dark Blade of Ending Misery</td>
<td>2.32</td>
<td>Eolo46</td>
</tr>
<tr>
<th>2</th>
<td>34</td>
<td>Male</td>
<td>174</td>
<td>Primitive Blade</td>
<td>2.46</td>
<td>Assastnya25</td>
</tr>
<tr>
<th>3</th>
<td>21</td>
<td>Male</td>
<td>92</td>
<td>Final Critic</td>
<td>1.36</td>
<td>Pheusrical25</td>
</tr>
<tr>
<th>4</th>
<td>23</td>
<td>Male</td>
<td>63</td>
<td>Stormfury Mace</td>
<td>1.27</td>
<td>Aela59</td>
</tr>
</tbody>
</table>
</div>




```python
#column list for reference
merged_df.columns
```




Index(['Age', 'Gender', 'Item ID', 'Item Name', 'Price', 'SN'], dtype='object')




```python
#use len on SN value counts to find unique SNs
player_count_total = len(merged_df["SN"].value_counts())
player_count_total

```




612




```python
#purchasing analytics(number of unique items, avg purchase price,
#total purchases, total revenue)
num_of_unique = merged_df["Item ID"].value_counts()
num_of_unique = len(num_of_unique)
num_of_unique
```




184




```python
#avg purchase price
avg_pp = merged_df["Price"].mean()
avg_pp
```




2.9305710955710955




```python
#total purchases
total_purchases = merged_df["Item ID"].count()
total_purchases
```




858




```python
#total revenue
total_revenue = merged_df["Price"].sum()
total_revenue
```




2514.4299999999998




```python
#make a df for analytics
purchase_analytics = pd.DataFrame({
"Total Unique Players" : [player_count_total],
"Total Unique Items" : [num_of_unique],
"Average Purchase Price" : [avg_pp],
"Total Purchases" : [total_purchases],
"Total Revenue" : [total_revenue]
})

```


```python
#improve formatting
purchase_analytics["Average Purchase Price"] = purchase_analytics["Average Purchase Price"].map("${0:,.2f}".format)
purchase_analytics["Total Purchases"] = purchase_analytics["Total Purchases"]
purchase_analytics["Total Revenue"] = purchase_analytics["Total Revenue"].map("${0:,.2f}".format)
purchase_analytics
```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Average Purchase Price</th>
<th>Total Purchases</th>
<th>Total Revenue</th>
<th>Total Unique Items</th>
<th>Total Unique Players</th>
</tr>
</thead>
<tbody>
<tr>
<th>0</th>
<td>$2.93</td>
<td>858</td>
<td>$2,514.43</td>
<td>184</td>
<td>612</td>
</tr>
</tbody>
</table>
</div>




```python
#gender demographics(% count male, female, other/ndc)
#total members via length of unique screennames
total_members = len(merged_df["SN"].value_counts())
#make a filter for only males
male_filter = merged_df["Gender"] == "Male"
#find males
male_count = merged_df.loc[male_filter,:]
#find total unique males
male_count = len(male_count["SN"].value_counts())
#make a filter for females
female_filter = merged_df["Gender"] == "Female"
#find females
female_count = merged_df.loc[female_filter,:]
#find total unique females
female_count = len(female_count["SN"].value_counts())
other_filter = merged_df["Gender"] == "Other / Non-Disclosed"
other_count = total_members - male_count - female_count




```


```python
#% count male
percent_male = male_count / total_members
percent_male
```




0.8137254901960784




```python
#% count female
percent_female = female_count / total_members
percent_female
```




0.1830065359477124




```python
#% other
other_percent = other_count / total_members
other_percent
```




0.0032679738562091504




```python
#make a new df with this info
data = [{"Total Members" : male_count, "Percentage of Gender" : percent_male
},{"Total Members" : female_count , "Percentage of Gender" : percent_female
},
{"Total Members" : other_count , "Percentage of Gender" : other_percent}]
gender_df = pd.DataFrame(data, index = ["Male","Female","Other"])
gender_df["Percentage of Gender"] = gender_df["Percentage of Gender"] * 100
gender_df["Percentage of Gender"] = gender_df["Percentage of Gender"].map("{0:.2f}%".format)
gender_df
```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Percentage of Gender</th>
<th>Total Members</th>
</tr>
</thead>
<tbody>
<tr>
<th>Male</th>
<td>81.37%</td>
<td>498</td>
</tr>
<tr>
<th>Female</th>
<td>18.30%</td>
<td>112</td>
</tr>
<tr>
<th>Other</th>
<td>0.33%</td>
<td>2</td>
</tr>
</tbody>
</table>
</div>




```python
#gender analytics.. find purchase count, avg pp,total value, normalized total
male_purchase_count = merged_df.loc[male_filter].count()["Item ID"]
male_purchase_count
#female purchase count
female_purchase_count = merged_df.loc[female_filter].count()["Item ID"]
female_purchase_count
#other purchase count
other_purchase_count = total_purchases - (male_purchase_count + female_purchase_count)
other_purchase_count

```




12




```python
#average purchase price per gender
male_avg_pp = merged_df.loc[male_filter].mean()["Price"]
male_avg_pp
#female
female_avg_pp = merged_df.loc[female_filter].mean()["Price"]
female_avg_pp
#other
other_avg_pp = merged_df.loc[other_filter].mean()["Price"]
other_avg_pp

```




3.1549999999999994




```python
#total purchase value per gender
male_sum_purchase = merged_df.loc[male_filter].sum()["Price"]
male_sum_purchase
#female
female_sum_purchase = merged_df.loc[female_filter].sum()["Price"]
female_sum_purchase
#other
other_sum_purchase = merged_df.loc[other_filter].sum()["Price"]
other_sum_purchase

```




37.85999999999999




```python
#normalize total per gender
male_normalized = male_sum_purchase / male_count
male_normalized
#female
female_normalized = female_sum_purchase / female_count
female_normalized
#other
other_normalized = other_sum_purchase / other_count
other_normalized
```




18.929999999999996




```python
#make a new DF with all this info
gender_data = [{"Total Purchases" : male_purchase_count, "Average Purchase"
: male_avg_pp, "Total Purchase Amount" : male_sum_purchase,
"Normalized Purchase Amount" : male_normalized},
{"Total Purchases" : female_purchase_count, "Average Purchase"
: female_avg_pp, "Total Purchase Amount" : female_sum_purchase,
"Normalized Purchase Amount" : female_normalized},
{"Total Purchases" : other_purchase_count, "Average Purchase"
: other_avg_pp, "Total Purchase Amount" : other_sum_purchase,
"Normalized Purchase Amount" : other_normalized}]
gender_analytics_df = pd.DataFrame(gender_data, index = ["Male", "Female","Other"])
gender_analytics_df
```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Average Purchase</th>
<th>Normalized Purchase Amount</th>
<th>Total Purchase Amount</th>
<th>Total Purchases</th>
</tr>
</thead>
<tbody>
<tr>
<th>Male</th>
<td>2.944448</td>
<td>4.121044</td>
<td>2052.28</td>
<td>697</td>
</tr>
<tr>
<th>Female</th>
<td>2.847584</td>
<td>3.788304</td>
<td>424.29</td>
<td>149</td>
</tr>
<tr>
<th>Other</th>
<td>3.155000</td>
<td>18.930000</td>
<td>37.86</td>
<td>12</td>
</tr>
</tbody>
</table>
</div>




```python
#format some .map("${0:,.2f}".format)
gender_analytics_df["Average Purchase"] = gender_analytics_df["Average Purchase"].map("${0:,.2f}".format)
gender_analytics_df["Normalized Purchase Amount"] = gender_analytics_df["Normalized Purchase Amount"].map("${0:,.2f}".format)
gender_analytics_df["Total Purchase Amount"] = gender_analytics_df["Total Purchase Amount"].map("${0:,.2f}".format)
gender_analytics_df
```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Average Purchase</th>
<th>Normalized Purchase Amount</th>
<th>Total Purchase Amount</th>
<th>Total Purchases</th>
</tr>
</thead>
<tbody>
<tr>
<th>Male</th>
<td>$2.94</td>
<td>$4.12</td>
<td>$2,052.28</td>
<td>697</td>
</tr>
<tr>
<th>Female</th>
<td>$2.85</td>
<td>$3.79</td>
<td>$424.29</td>
<td>149</td>
</tr>
<tr>
<th>Other</th>
<td>$3.15</td>
<td>$18.93</td>
<td>$37.86</td>
<td>12</td>
</tr>
</tbody>
</table>
</div>




```python
#age demographics, use bins per 4 years. <10,10-14,15-19,etc
age_bins = [0,10,15,20,25,30,35,40,1000]
age_labels = ["Less than 10","10 - 14","15 - 19","20 - 24","25 - 29",
"30 - 34","35 - 39","40 and older"]
pd.cut(merged_df["Age"],age_bins,labels = age_labels )
merged_df["Age Group"] = pd.cut(merged_df["Age"],age_bins,labels = age_labels )
merged_df.head()

```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Age</th>
<th>Gender</th>
<th>Item ID</th>
<th>Item Name</th>
<th>Price</th>
<th>SN</th>
<th>Age Group</th>
</tr>
</thead>
<tbody>
<tr>
<th>0</th>
<td>38</td>
<td>Male</td>
<td>165</td>
<td>Bone Crushing Silver Skewer</td>
<td>3.37</td>
<td>Aelalis34</td>
<td>35 - 39</td>
</tr>
<tr>
<th>1</th>
<td>21</td>
<td>Male</td>
<td>119</td>
<td>Stormbringer, Dark Blade of Ending Misery</td>
<td>2.32</td>
<td>Eolo46</td>
<td>20 - 24</td>
</tr>
<tr>
<th>2</th>
<td>34</td>
<td>Male</td>
<td>174</td>
<td>Primitive Blade</td>
<td>2.46</td>
<td>Assastnya25</td>
<td>30 - 34</td>
</tr>
<tr>
<th>3</th>
<td>21</td>
<td>Male</td>
<td>92</td>
<td>Final Critic</td>
<td>1.36</td>
<td>Pheusrical25</td>
<td>20 - 24</td>
</tr>
<tr>
<th>4</th>
<td>23</td>
<td>Male</td>
<td>63</td>
<td>Stormfury Mace</td>
<td>1.27</td>
<td>Aela59</td>
<td>20 - 24</td>
</tr>
</tbody>
</table>
</div>




```python
#group by object
grouped_age = merged_df.groupby("Age Group")
#total purchases by age
purchases_by_age = grouped_age["Price"].count()
```


```python
#calculate the mean
avg_pp_by_age = grouped_age["Price"].mean()
avg_pp_by_age
```




Age Group
Less than 10    2.984865
10 - 14         2.882439
15 - 19         2.859951
20 - 24         2.967544
25 - 29         2.882375
30 - 34         2.995846
35 - 39         3.004286
40 and older    2.880000
Name: Price, dtype: float64




```python
#sum the total values
age_total_value = grouped_age["Price"].sum()
age_total_value
```




Age Group
Less than 10     110.44
10 - 14          236.36
15 - 19          583.43
20 - 24         1003.03
25 - 29          230.59
30 - 34          194.73
35 - 39          147.21
40 and older       8.64
Name: Price, dtype: float64




```python
#find normalized value
age_demo_total_players = grouped_age["SN"].nunique()
age_demo_total_players

```




Age Group
Less than 10     27
10 - 14          57
15 - 19         159
20 - 24         259
25 - 29          56
30 - 34          50
35 - 39          30
40 and older      3
Name: SN, dtype: int64




```python
#find normalized values
normalized_age_value = age_total_value / age_demo_total_players
normalized_age_value
```




Age Group
Less than 10    4.090370
10 - 14         4.146667
15 - 19         3.669371
20 - 24         3.872703
25 - 29         4.117679
30 - 34         3.894600
35 - 39         4.907000
40 and older    2.880000
dtype: float64




```python
age_demo_data = {"Total Purchases" : purchases_by_age,
"Average Purchase by Age" : avg_pp_by_age,
"Total Purchase Value" : age_total_value,
"Normalized Value" : normalized_age_value}
age_demo_df = pd.DataFrame(age_demo_data)
age_demo_df
```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Average Purchase by Age</th>
<th>Normalized Value</th>
<th>Total Purchase Value</th>
<th>Total Purchases</th>
</tr>
<tr>
<th>Age Group</th>
<th></th>
<th></th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr>
<th>Less than 10</th>
<td>2.984865</td>
<td>4.090370</td>
<td>110.44</td>
<td>37</td>
</tr>
<tr>
<th>10 - 14</th>
<td>2.882439</td>
<td>4.146667</td>
<td>236.36</td>
<td>82</td>
</tr>
<tr>
<th>15 - 19</th>
<td>2.859951</td>
<td>3.669371</td>
<td>583.43</td>
<td>204</td>
</tr>
<tr>
<th>20 - 24</th>
<td>2.967544</td>
<td>3.872703</td>
<td>1003.03</td>
<td>338</td>
</tr>
<tr>
<th>25 - 29</th>
<td>2.882375</td>
<td>4.117679</td>
<td>230.59</td>
<td>80</td>
</tr>
<tr>
<th>30 - 34</th>
<td>2.995846</td>
<td>3.894600</td>
<td>194.73</td>
<td>65</td>
</tr>
<tr>
<th>35 - 39</th>
<td>3.004286</td>
<td>4.907000</td>
<td>147.21</td>
<td>49</td>
</tr>
<tr>
<th>40 and older</th>
<td>2.880000</td>
<td>2.880000</td>
<td>8.64</td>
<td>3</td>
</tr>
</tbody>
</table>
</div>




```python
#formatting
age_demo_df["Average Purchase by Age"] = age_demo_df["Average Purchase by Age"].map("${0:,.2f}".format)
age_demo_df["Normalized Value"] = age_demo_df["Normalized Value"].map("${0:,.2f}".format)
age_demo_df["Total Purchase Value"] = age_demo_df["Total Purchase Value"].map("${0:,.2f}".format)
age_demo_df

```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Average Purchase by Age</th>
<th>Normalized Value</th>
<th>Total Purchase Value</th>
<th>Total Purchases</th>
</tr>
<tr>
<th>Age Group</th>
<th></th>
<th></th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr>
<th>Less than 10</th>
<td>$2.98</td>
<td>$4.09</td>
<td>$110.44</td>
<td>37</td>
</tr>
<tr>
<th>10 - 14</th>
<td>$2.88</td>
<td>$4.15</td>
<td>$236.36</td>
<td>82</td>
</tr>
<tr>
<th>15 - 19</th>
<td>$2.86</td>
<td>$3.67</td>
<td>$583.43</td>
<td>204</td>
</tr>
<tr>
<th>20 - 24</th>
<td>$2.97</td>
<td>$3.87</td>
<td>$1,003.03</td>
<td>338</td>
</tr>
<tr>
<th>25 - 29</th>
<td>$2.88</td>
<td>$4.12</td>
<td>$230.59</td>
<td>80</td>
</tr>
<tr>
<th>30 - 34</th>
<td>$3.00</td>
<td>$3.89</td>
<td>$194.73</td>
<td>65</td>
</tr>
<tr>
<th>35 - 39</th>
<td>$3.00</td>
<td>$4.91</td>
<td>$147.21</td>
<td>49</td>
</tr>
<tr>
<th>40 and older</th>
<td>$2.88</td>
<td>$2.88</td>
<td>$8.64</td>
<td>3</td>
</tr>
</tbody>
</table>
</div>




```python
#top 5 spenders
#group by SN
grouped_df = merged_df.groupby("SN")
#sum prices by group
grouped_df = grouped_df.sum()["Price"]
#sort, descending order
grouped_df = grouped_df.sort_values(ascending = False)
#print top 5
grouped_df.head()
```




SN
Undirrala66      17.06
Aerithllora36    15.10
Saedue76         13.56
Sondim43         13.02
Mindimnya67      12.74
Name: Price, dtype: float64




```python
#find purchases per user
undi = merged_df["SN"] == "Undirrala66"
undi = merged_df[undi]["Item ID"].count()
aeri = merged_df["SN"] == "Aerithllora36"
aeri = merged_df[aeri]["Item ID"].count()
saed = merged_df["SN"] == "Saedue76"
saed = merged_df[saed]["Item ID"].count()
sond = merged_df["SN"] == "Sondim43"
sond = merged_df[sond]["Item ID"].count()
mind = merged_df["SN"] == "Mindimnya67"
mind = merged_df[mind]["Item ID"].count()

```


```python
#find total values for each person
undi_total = merged_df["SN"] == "Undirrala66"
undi_total = merged_df[undi_total]["Price"].sum()
aeri_total = merged_df["SN"] == "Aerithllora36"
aeri_total = merged_df[aeri_total]["Price"].sum()
saed_total = merged_df["SN"] == "Saedue76"
saed_total = merged_df[saed_total]["Price"].sum()
sond_total = merged_df["SN"] == "Sondim43"
sond_total = merged_df[sond_total]["Price"].sum()
mind_total = merged_df["SN"] == "Mindimnya67"
mind_total = merged_df[mind_total]["Price"].sum()

```


```python
#find averages
undi_avg = undi_total / undi
aeri_avg = aeri_total / aeri
saed_avg = saed_total / saed
sond_avg = sond_total / sond
mind_avg = mind_total / mind
```


```python
#make a df with all t his data
spenders_data = {"SN" : ["Undirrala66","Aerithllora36","Saedue76","Sondim43","Mindimnya67"],
"Total Purchases" : [undi,aeri,saed,sond,mind], "Total Purchase Amount" :
[undi_total,aeri_total,saed_total,sond_total,mind_total],
"Average Purchase" : [undi_avg,aeri_avg,saed_avg,sond_avg,mind_avg]}
top_5_users_df = pd.DataFrame(spenders_data,index = ["First","Second","Third","Fourth","Fifth"])
top_5_users_df
```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Average Purchase</th>
<th>SN</th>
<th>Total Purchase Amount</th>
<th>Total Purchases</th>
</tr>
</thead>
<tbody>
<tr>
<th>First</th>
<td>3.412</td>
<td>Undirrala66</td>
<td>17.06</td>
<td>5</td>
</tr>
<tr>
<th>Second</th>
<td>3.775</td>
<td>Aerithllora36</td>
<td>15.10</td>
<td>4</td>
</tr>
<tr>
<th>Third</th>
<td>3.390</td>
<td>Saedue76</td>
<td>13.56</td>
<td>4</td>
</tr>
<tr>
<th>Fourth</th>
<td>3.255</td>
<td>Sondim43</td>
<td>13.02</td>
<td>4</td>
</tr>
<tr>
<th>Fifth</th>
<td>3.185</td>
<td>Mindimnya67</td>
<td>12.74</td>
<td>4</td>
</tr>
</tbody>
</table>
</div>




```python
#formatting
top_5_users_df["Average Purchase"] = top_5_users_df["Average Purchase"].map("${0:,.2f}".format)
top_5_users_df["Total Purchase Amount"] = top_5_users_df["Total Purchase Amount"].map("${0:,.2f}".format)
top_5_users_df
```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Average Purchase</th>
<th>SN</th>
<th>Total Purchase Amount</th>
<th>Total Purchases</th>
</tr>
</thead>
<tbody>
<tr>
<th>First</th>
<td>$3.41</td>
<td>Undirrala66</td>
<td>$17.06</td>
<td>5</td>
</tr>
<tr>
<th>Second</th>
<td>$3.77</td>
<td>Aerithllora36</td>
<td>$15.10</td>
<td>4</td>
</tr>
<tr>
<th>Third</th>
<td>$3.39</td>
<td>Saedue76</td>
<td>$13.56</td>
<td>4</td>
</tr>
<tr>
<th>Fourth</th>
<td>$3.25</td>
<td>Sondim43</td>
<td>$13.02</td>
<td>4</td>
</tr>
<tr>
<th>Fifth</th>
<td>$3.18</td>
<td>Mindimnya67</td>
<td>$12.74</td>
<td>4</td>
</tr>
</tbody>
</table>
</div>




```python
#top 5 popular items
popular_5 = merged_df["Item ID"].value_counts()
popular_5.head(5)
```




84    12
39    11
31    10
34     9
44     9
Name: Item ID, dtype: int64




```python
#find data for each item
item_84 = merged_df["Item ID"] == 84
item_39 = merged_df["Item ID"] == 39
item_31 = merged_df["Item ID"] == 31
item_34 = merged_df["Item ID"] == 34
item_44 = merged_df["Item ID"] == 44
#find name for each item
item_84_name = merged_df.loc[item_84]["Item Name"].values[0]
item_39_name = merged_df.loc[item_39]["Item Name"].values[0]
item_31_name = merged_df.loc[item_31]["Item Name"].values[0]
item_34_name = merged_df.loc[item_34]["Item Name"].values[0]
item_44_name = merged_df.loc[item_44]["Item Name"].values[0]

```


```python
#find the amounts each item was purchased
item_84_purchase = len(merged_df.loc[item_84])
item_39_purchase = len(merged_df.loc[item_39])
item_31_purchase = len(merged_df.loc[item_31])
item_34_purchase = len(merged_df.loc[item_34])
item_44_purchase = len(merged_df.loc[item_44])
```


```python
#find item price
item_84_price = merged_df.loc[item_84]["Price"].values[0]
item_39_price = merged_df.loc[item_39]["Price"].values[0]
item_31_price = merged_df.loc[item_31]["Price"].values[0]
item_34_price = merged_df.loc[item_34]["Price"].values[0]
item_44_price = merged_df.loc[item_44]["Price"].values[0]

```


```python
#find total purchase value
item_84_value = merged_df.loc[item_84]["Price"].sum()
item_39_value = merged_df.loc[item_39]["Price"].sum()
item_31_value = merged_df.loc[item_31]["Price"].sum()
item_34_value = merged_df.loc[item_34]["Price"].sum()
item_44_value = merged_df.loc[item_44]["Price"].sum()

```


```python
#final index
top_5_items_data = {"Item Name" : [item_84_name,item_39_name,item_31_name,item_34_name,item_44_name],
"Total Purchases" : [item_84_purchase,item_39_purchase,item_31_purchase,item_34_purchase,item_44_purchase],
"Item Price" : [item_84_price,item_39_price,item_31_price,item_34_price,item_44_price],
"Total Revenue" : [item_84_value,item_39_value,item_31_value,item_34_value,item_44_value]}
top_5_items_df = pd.DataFrame(top_5_items_data,index = ["First","Second","Third","Fourth","Fifth"])
top_5_items_df
```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Item Name</th>
<th>Item Price</th>
<th>Total Purchases</th>
<th>Total Revenue</th>
</tr>
</thead>
<tbody>
<tr>
<th>First</th>
<td>Arcane Gem</td>
<td>2.23</td>
<td>12</td>
<td>29.34</td>
</tr>
<tr>
<th>Second</th>
<td>Betrayal, Whisper of Grieving Widows</td>
<td>2.35</td>
<td>11</td>
<td>25.85</td>
</tr>
<tr>
<th>Third</th>
<td>Trickster</td>
<td>2.07</td>
<td>10</td>
<td>23.22</td>
</tr>
<tr>
<th>Fourth</th>
<td>Retribution Axe</td>
<td>4.14</td>
<td>9</td>
<td>37.26</td>
</tr>
<tr>
<th>Fifth</th>
<td>Bonecarvin Battle Axe</td>
<td>2.46</td>
<td>9</td>
<td>24.04</td>
</tr>
</tbody>
</table>
</div>




```python
#formatting
top_5_items_df["Item Price"] = top_5_items_df["Item Price"].map("${0:,.2f}".format)
top_5_items_df["Total Revenue"] = top_5_items_df["Total Revenue"].map("${0:,.2f}".format)
top_5_items_df
```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Item Name</th>
<th>Item Price</th>
<th>Total Purchases</th>
<th>Total Revenue</th>
</tr>
</thead>
<tbody>
<tr>
<th>First</th>
<td>Arcane Gem</td>
<td>$2.23</td>
<td>12</td>
<td>$29.34</td>
</tr>
<tr>
<th>Second</th>
<td>Betrayal, Whisper of Grieving Widows</td>
<td>$2.35</td>
<td>11</td>
<td>$25.85</td>
</tr>
<tr>
<th>Third</th>
<td>Trickster</td>
<td>$2.07</td>
<td>10</td>
<td>$23.22</td>
</tr>
<tr>
<th>Fourth</th>
<td>Retribution Axe</td>
<td>$4.14</td>
<td>9</td>
<td>$37.26</td>
</tr>
<tr>
<th>Fifth</th>
<td>Bonecarvin Battle Axe</td>
<td>$2.46</td>
<td>9</td>
<td>$24.04</td>
</tr>
</tbody>
</table>
</div>




```python
#top 5 profitable items
#group them by item id
grouped_df = merged_df.groupby("Item ID")
#sum the revenue
grouped_df = grouped_df["Price"].sum()
#descending order
grouped_df = grouped_df.sort_values(ascending = False)
#top 5
grouped_df.head(5)
```




Item ID
34     37.26
107    33.03
115    29.75
32     29.70
84     29.34
Name: Price, dtype: float64




```python
#find data for each item
item_34 = merged_df["Item ID"] == 34
item_107 = merged_df["Item ID"] == 107
item_115 = merged_df["Item ID"] == 115
item_32 = merged_df["Item ID"] == 32
item_84 = merged_df["Item ID"] == 84
#find name for each item
item_34_name = merged_df.loc[item_34]["Item Name"].values[0]
item_107_name = merged_df.loc[item_107]["Item Name"].values[0]
item_115_name = merged_df.loc[item_115]["Item Name"].values[0]
item_32_name = merged_df.loc[item_32]["Item Name"].values[0]
item_84_name = merged_df.loc[item_84]["Item Name"].values[0]
```


```python
#find the amounts each item was purchased
item_34_purchase = len(merged_df.loc[item_34])
item_107_purchase = len(merged_df.loc[item_107])
item_115_purchase = len(merged_df.loc[item_115])
item_32_purchase = len(merged_df.loc[item_32])
item_84_purchase = len(merged_df.loc[item_84])
```


```python
#find item price
item_34_price = merged_df.loc[item_34]["Price"].values[0]
item_107_price = merged_df.loc[item_107]["Price"].values[0]
item_115_price = merged_df.loc[item_115]["Price"].values[0]
item_32_price = merged_df.loc[item_32]["Price"].values[0]
item_84_price = merged_df.loc[item_84]["Price"].values[0]
```


```python
#find total purchase value
item_34_value = merged_df.loc[item_34]["Price"].sum()
item_107_value = merged_df.loc[item_107]["Price"].sum()
item_115_value = merged_df.loc[item_115]["Price"].sum()
item_32_value = merged_df.loc[item_32]["Price"].sum()
item_84_value = merged_df.loc[item_84]["Price"].sum()
```


```python
#get final table
top_5_profit_data = {"Item Name" : [item_34_name,item_107_name,item_115_name,item_32_name,item_84_name],
"Total Purchases" : [item_34_purchase,item_107_purchase,item_115_purchase,item_32_purchase,item_84_purchase],
"Item Price" : [item_34_price,item_107_price,item_115_price,item_32_price,item_84_price],
"Total Revenue" : [item_34_value,item_107_value,item_115_value,item_32_value,item_84_value]}
top_5_profit_df = pd.DataFrame(top_5_profit_data,index = ["First","Second","Third","Fourth","Fifth"])
top_5_profit_df
```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Item Name</th>
<th>Item Price</th>
<th>Total Purchases</th>
<th>Total Revenue</th>
</tr>
</thead>
<tbody>
<tr>
<th>First</th>
<td>Retribution Axe</td>
<td>4.14</td>
<td>9</td>
<td>37.26</td>
</tr>
<tr>
<th>Second</th>
<td>Splitter, Foe Of Subtlety</td>
<td>3.61</td>
<td>9</td>
<td>33.03</td>
</tr>
<tr>
<th>Third</th>
<td>Spectral Diamond Doomblade</td>
<td>4.25</td>
<td>7</td>
<td>29.75</td>
</tr>
<tr>
<th>Fourth</th>
<td>Orenmir</td>
<td>4.95</td>
<td>6</td>
<td>29.70</td>
</tr>
<tr>
<th>Fifth</th>
<td>Arcane Gem</td>
<td>2.23</td>
<td>12</td>
<td>29.34</td>
</tr>
</tbody>
</table>
</div>




```python
# #formatting
top_5_profit_df["Item Price"] = top_5_profit_df["Item Price"].map("${0:,.2f}".format)
top_5_profit_df["Total Revenue"] = top_5_profit_df["Total Revenue"].map("${0:,.2f}".format)
top_5_profit_df
```




<div>
<style>
.dataframe thead tr:only-child th {
text-align: right;
}

.dataframe thead th {
text-align: left;
}

.dataframe tbody tr th {
vertical-align: top;
}
</style>
<table border="1" class="dataframe">
<thead>
<tr style="text-align: right;">
<th></th>
<th>Item Name</th>
<th>Item Price</th>
<th>Total Purchases</th>
<th>Total Revenue</th>
</tr>
</thead>
<tbody>
<tr>
<th>First</th>
<td>Retribution Axe</td>
<td>$4.14</td>
<td>9</td>
<td>$37.26</td>
</tr>
<tr>
<th>Second</th>
<td>Splitter, Foe Of Subtlety</td>
<td>$3.61</td>
<td>9</td>
<td>$33.03</td>
</tr>
<tr>
<th>Third</th>
<td>Spectral Diamond Doomblade</td>
<td>$4.25</td>
<td>7</td>
<td>$29.75</td>
</tr>
<tr>
<th>Fourth</th>
<td>Orenmir</td>
<td>$4.95</td>
<td>6</td>
<td>$29.70</td>
</tr>
<tr>
<th>Fifth</th>
<td>Arcane Gem</td>
<td>$2.23</td>
<td>12</td>
<td>$29.34</td>
</tr>
</tbody>
</table>
</div>




```python
#Finish!
```


```python

```
