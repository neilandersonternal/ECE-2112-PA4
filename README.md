# ECE-2112-PA4


This is mainly for the content of the repository that I've submitted which covers the three Python problems from our assignment from the course
ECE 2112(Advanced Computer Programming). In which includes Base Computing using Python as a language.


# **A. VISAYAS COMMUNICATION DATAFRAME**


**Objectives:**
Create a DataFrame named VisComm containing students whose Hometown is Visayas and whose Track
is Communication. Retain only these columns, in the stated order: Name, Gender, Math, Electronics, Average

Display the resulting DataFrame and its number of rows. Both filtering conditions must be applied to
the source dataset before the columns are selected.

 The functions that I made in this problem are:

```python
VisComm = df[(df['Hometown'] == 'Visayas') & (df['Track'] == 'Communication')]
```

This simply gets the data from the people in the data frame that were from the specified hometown Visayas. Moreover,
I used an "&" attribute to narrow it down more with the specified track of Communication. So with this function, this will locate
people from the data frame that has a hometown from Visayas and has a track of Communication stocked into the 'VisComm'.

However, as what the instruction implies 'VisComm' should only retain the follow: Name, Gender, Math, Electronics, Average.
That's why I made this another function

```python
VisComm = VisComm[['Name', 'Gender', 'Math', 'Electronics', 'Average']]
```

This lets Name, Gender, Math, Electronics, and Average retain only from the VisComm data frame.

Finally, to display the data frame and the number of rows, I used 

```python
display() - this used particularly in numpy or pandas, an alternative version of print but print is only used for
strings, int, etc.
```

I used display mainly for displaying the dataframe itself.
And to finally count the rows of the specified data frame, I used:

```python
len() -  function in Python returns the number of items in an object. 
```




# **B. VISAYAS FEMALE DATAFRAME**


**Objectives:**

Create a second DataFrame named VisFemale containing students whose Hometown is Visayas and
whose Gender is Female. Retain only: Name, Track, GEAS, Electronics, Average.

Display VisFemale. Then display only the rows of VisFemale whose Average is at least 60. Do not
overwrite VisFemale when performing this second filter.

```python
VisFemale = df[(df['Hometown'] == 'Visayas') & (df['Gender'] == 'Female')]
```

This user-defined function is constructed to get the datas specifically from the dataframe that is a Female and has a hometown of
Visayas. This function inspects the whole dataframe and locate the datas that is set by this function. Which is 
getting the datas from the people from Visayas at the same time has a gender of a Female.

For the next instruction, I made the function:

```python
VisFemale = VisFemale[['Name', 'Track', 'GEAS', 'Electronics', 'Average']]
```

This gets all the data from the first dataframe 'VisFemale' but with specified datas only. Which in this case are:
'Name', 'Track', 'GEAS', 'Electronics', 'Average'. This user-defined function aims to include only the specified categories.

And finally,
```python
display(VisFemale[VisFemale['Average'] >= 60])
```

This function allows to display the dataframe but has a condition of displaying only those
who has the average greater than 60.




# **C. CATEGORY-AVERAGE VISUALIZATION**

**Objectives:**

Examine how the recorded Average differs across the three categorical features Track, Gender, and
Hometown.
a. For each feature, compute the mean of Average for every category using Pandas.
b. Display the three summary tables.
c. Create one figure containing three bar charts: mean Average by Track, by Gender, and by
Hometown.
d. Below the figure, write three concise statements identifying the category with the highest sample
mean for each feature



So for this problem, I used multiple user-defined functions. And for the first function, the aim is to
get the 'Average' datas for each category. 

```python
track_mean = df.groupby('Track')['Average'].mean().reset_index()
gender_mean = df.groupby('Gender')['Average'].mean().reset_index()
hometown_mean = df.groupby('Hometown')['Average'].mean().reset_index()
```

the main function that I used for that is the:

```python
df.groupby() - You can group by multiple categories at once by passing a list of column names
```

this function only gets the specified categories which is in this case is the Track and the Average.
I used the function thrice, with three different categories. I also used the function ``` .mean()```, to get the 
average for each categories. I also used the function ``` .reset_index()``` , this resets the number of the data
back from 0.

Finally, I used the functions:

```python
plt.subplot() -  It acts as a wrapper that automatically initializes a Figure object that can have multiple plots
plt.bar() - this function is used to set the vertical bar graphs.
plt.title() - this is the name of the specified graph.
plt.xlabel() - this is the label that is in the x-axis, where in this case are the categories.
plt.ylabel() - this the name or the label for the y-axis, where in this case is the mean average.
```
This 5 functions are used to create the multiple bar graphs. However, what made the graphs visible is the
```plt.tight_layout()``` and the ```plt.show()```. The 'plt.show' showed the designed graph, and the 
'plt.tight_layout' made the graphs not overlap each other.

That's all for my fourth assignment. Thank you for reading!!

**README** file version history:

September 14, 2026: Initial README output uploaded.

September 17, 2026: Revised README output was uploaded.



































