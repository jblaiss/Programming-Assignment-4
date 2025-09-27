# Programming-Assignment-4
## Experiment 4 - Data Wrangling and Data Visualization
### Intended Learning Outcomes
1. To identify the codes and functions needed in cleaning and visualizing data
2. To be able to apply and use the different codes and functions in creating a Python program that will be used in data wranling and data visualization
### Given Problem/s
1. ECE BOARD EXAM PROBLEM

   a. Problem 1 - Part A
   
   b. Problem 1 - Part B
   
   c. Problem 2
------------------------------------------
## ECE BOARD EXAM PROBLEM
Using data wrangling and data visualization technique with storytelling, analyze the data and present different (i) data frames; and (ii) visuals using the dataset given.

------------------------------------------
## Problem 1 - Part A
Filename: Instru = [“Name”, “GEAS”, “Electronics>70”]; where track is constant as Instrumentation and hometown Luzon

### My Code (Problem 1 - Part A)
```python
import pandas as pd
```
```python
import matplotlib.pyplot as plt
```
```python
#dataframe

df = pd.read_excel('board2.xlsx')
df
```
#### Output
<img width="655" height="521" alt="image" src="https://github.com/user-attachments/assets/95557dfe-6c91-489d-8b98-6bdd71a6f460" />
<img width="654" height="499" alt="image" src="https://github.com/user-attachments/assets/4ced03ff-e876-4d9c-be00-3cb1832fd10d" />

```python
#Instru DataFrame

Instru = df.loc[(df["Hometown"] == "Luzon") & #specifies to only include students whose hometown is from Luzon
         (df["Track"] == "Instrumentation") & #specifies to only include students whose track is instrumentation
         (df['Electronics']>70)] #specifies to only include students whose grade is greater than 70

Instru = Instru [["Name", "GEAS", "Electronics"]] #table with specified columns
Instru
```
#### Output
<img width="221" height="135" alt="image" src="https://github.com/user-attachments/assets/5de504ad-702a-4aef-a650-94affb12c7fc" />

### Explanation
1. **Accessing Pandas Library** - 
To access Pandas library, the import convention must be used: import pandas as pd.
2. **Loading the Corresponding .xlsx File** -
To load the .xlsx file, we use the code: df = pd.read_excel('board2.xlsx'). This will display the dataframe
3. **Display Specified Students (Hometown = Luzon)** -
To display the specified students we use the code .loc. This will locate and let you access rows and columns by their names. Therefore the code: Instru = df.loc[(df["Hometown"] == "Luzon") will specify that the output will only display students whose hometown is Luzon
4. **Display Specified Students (Track = Instrumentation)** -
The code: (df["Track"] == "Instrumentation") will specify that the output will only display students whose track is Instrumentation
5. **Display Specified Students (Electronics > 70)** -
The code: df['Electronics']>70)] will specify that the output will only display students whose grade in Electronics is greater than 70
6. **Display Output with Specified Columns** -
The code: Instru = Instru [["Name", "GEAS", "Electronics"]] will specify that the output will only display columns of the ff. Names, GEAS, Electronics along with the specified students

------------------------------------------
## Problem 1 - Part B
Filename: Mindy = [ “Name”, “Track”, “Electronics”, “Average >=55”]; where hometown is constant as Mindanao and gender Female
### My Code (Problem 1 - Part B)
```python
import pandas as pd
```
```python
import matplotlib.pyplot as plt
```
```python
#dataframe

df = pd.read_excel('board2.xlsx')
df
```
#### Output
<img width="655" height="521" alt="image" src="https://github.com/user-attachments/assets/95557dfe-6c91-489d-8b98-6bdd71a6f460" />
<img width="654" height="499" alt="image" src="https://github.com/user-attachments/assets/4ced03ff-e876-4d9c-be00-3cb1832fd10d" />

```python
#to get the average and to add a column for average
df['Average'] = df[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1)

#Mindy DataFrame

Mindy = df.loc[(df["Hometown"] == "Mindanao") & #specifies to only include students whose hometown is from Luzon
        (df["Gender"] == "Female") & #specifies to only include students who are female 
        (df['Average'] >=55)] #specifies to only include students whose average grade is greater than or equal 55

Mindy = Mindy [["Name", "Track", "Electronics", "Average"]] #table with specified columns
Mindy 
```
#### Output
<img width="354" height="200" alt="image" src="https://github.com/user-attachments/assets/0d856856-067a-45ce-839c-13490ad37bac" />

### Explanation
1. **Accessing Pandas Library** - 
To access Pandas library, the import convention must be used: import pandas as pd.
2. **Loading the Corresponding .xlsx File** -
To load the .xlsx file, we use the code: df = pd.read_excel('board2.xlsx'). This will display the dataframe
3. **Mean Average of the Four Subjects** -
The code: df['Average'] = df[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1) will include a new column "Average" to the dataframe and output that contains the average grade of the four subjects by adding .mean to the code. As for the (axis=1), it operates across the columns therefore helps the code .mean
4. **Display Specified Students (Hometown = Mindanao)** -
To display the specified students we use the code .loc. This will locate and let you access rows and columns by their names. Therefore the code: Mindy = df.loc[(df["Hometown"] == "Mindanao") will specify that the output will only display students whose hometown is Mindanao
5. **Display Specified Students (Gender = Female)** -
The code: (df["Gender"] == "Female") will specify that the output will only display students that are female
7. **Display Specified Students (Average >= 55)** -
The code: (df['Average'] >=55)] will specify that the output will only display students who has an average grade that is greater than or equal to 55
8. **Display Output with Specified Columns** -
The code: Mindy = Mindy [["Name", "Track", "Electronics", "Average"]] will specify that the output will only display columns of the ff. Names, Track, Electronics, and Average, along with the specified students
------------------------------------------
## Problem 2
Create a visualization that shows how the different features contributes to average grade. Does chosen track in college, gender, or hometown contributes to a higher average score? 

### My Code (Problem 2)
```python
import pandas as pd
```
```python
import matplotlib.pyplot as plt
```
```python
#dataframe

df = pd.read_excel('board2.xlsx')
df
```
#### Output
<img width="655" height="521" alt="image" src="https://github.com/user-attachments/assets/95557dfe-6c91-489d-8b98-6bdd71a6f460" />
<img width="654" height="499" alt="image" src="https://github.com/user-attachments/assets/4ced03ff-e876-4d9c-be00-3cb1832fd10d" />

### My Code (Average Grade per Track)
```python
#to get the average and to add a column for average
df['Average'] = df[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1)

#visualization
plt.figure(figsize=(8,5)) #length and width size of bargraph

avg_tr = df.groupby("Track")["Average"].mean() #includes only the average grade and each track
plt.bar(avg_tr.index, avg_tr.values, color=["steelblue", "seagreen", "tomato"]) #creates the bar chart for the x and y categories, including color
plt.title("Average Grade per Track") #title for chart
plt.xlabel("Track") #x-axis label
plt.ylabel("Average Grade") #y-axis label
plt.show() #display
```
#### Output
<img width="761" height="505" alt="image" src="https://github.com/user-attachments/assets/351a428c-3657-4e20-9676-54f9047053ef" />

### Explanation
1. **Accessing Pandas Library** - 
To access Pandas library, the import convention must be used: import pandas as pd.
2. **Accessing MatPlot Library** -
To access MatPlot library, the import convention must be used: import matplotlib.pyplot as plt. This gives us access to plotting functions of matplot for visualization
4. **Loading the Corresponding .xlsx File** -
To load the .xlsx file, we use the code: df = pd.read_excel('board2.xlsx'). This will display the dataframe
5. **Mean Average of the Four Subjects** -
The code: df['Average'] = df[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1) will include a new column "Average" to the dataframe and output that contains the average grade of the four subjects by adding .mean to the code. As for the (axis=1), it operates across the columns therefore helps the code .mean
6. **Figure / Chart Size** -
The code: plt.figure(figsize=(8,5)) this adjusts the length and width size of the figures in the bargraph
7. **Specified Columns** -
The code: avg_tr = df.groupby("Track")["Average"].mean() functions by grouping the values in the dataframe rows in the column track and only selecting the average column. Thus, it will calculate the average grade per track.
8. **Creating Bargraph** -
The code: plt.bar(avg_tr.index, avg_tr.values, color=["steelblue", "seagreen", "tomato"]). The index functions as the x-axis, holding the track categories, meanwhile the values functions as the y-axis holding the average grade.
8. **Chart Title** -
The code: plt.title("Average Grade per Track") simply functions by adding a title for the chart
9. **X and Y-axis Label** -
The code: plt.xlabel("Track") and plt.ylabel("Average Grade") simply functions by adding a title for botht he x and y-axis labels
10. **Display Output** -
The code: plt.show() simply displays the output

### My Code (Average Grade per Gender)
```python
#to get the average and to add a column for average
df['Average'] = df[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1)

#visualization
plt.figure(figsize=(8,5)) #length and width size of bargraph

avg_tr = df.groupby("Gender")["Average"].mean() #includes only the average grade and gender
plt.bar(avg_tr.index, avg_tr.values, color=["fuchsia", "skyblue"]) #creates the bar chart for the x and y categories, including color
plt.title("Average Grade per Gender") #title for chart
plt.xlabel("Gender") #x-axis label
plt.ylabel("Average Grade") #y-axis label
plt.show() #display
```
#### Output
<img width="632" height="428" alt="image" src="https://github.com/user-attachments/assets/e9f30b97-8730-42a3-abf6-fe785092c9e7" />

### Explanation
1. **Accessing Pandas Library** - 
To access Pandas library, the import convention must be used: import pandas as pd.
2. **Accessing MatPlot Library** -
To access MatPlot library, the import convention must be used: import matplotlib.pyplot as plt. This gives us access to plotting functions of matplot for visualization
4. **Loading the Corresponding .xlsx File** -
To load the .xlsx file, we use the code: df = pd.read_excel('board2.xlsx'). This will display the dataframe
5. **Mean Average of the Four Subjects** -
The code: df['Average'] = df[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1) will include a new column "Average" to the dataframe and output that contains the average grade of the four subjects by adding .mean to the code. As for the (axis=1), it operates across the columns therefore helps the code .mean
6. **Figure / Chart Size** -
The code: plt.figure(figsize=(8,5)) this adjusts the length and width size of the figures in the bargraph
7. **Specified Columns** -
The code: avg_tr = df.groupby("Gender")["Average"].mean() functions by grouping the values in the dataframe rows in the gender column and only selecting the average column. Thus, it will calculate the average grade per gender.
8. **Creating Bargraph** -
The code: plt.bar(avg_tr.index, avg_tr.values, color=["fuchsia", "skyblue"]). The index functions as the x-axis, holding the gender categories, meanwhile the values functions as the y-axis holding the average grade.
8. **Chart Title** -
The code: plt.title("Average Grade per Gender") simply functions by adding a title for the chart
9. **X and Y-axis Label** -
The code: plt.xlabel("Gender") and plt.ylabel("Average Grade") simply functions by adding a title for botht he x and y-axis labels
10. **Display Output** -
The code: plt.show() simply displays the output

### My Code (Average Grade per Hometown)
```python
#to get the average and to add a column for average
df['Average'] = df[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1)

#visualization
plt.figure(figsize=(8,5)) #length and width size of bargraph

avg_tr = df.groupby("Hometown")["Average"].mean() #includes only the average grade and each hometown
plt.bar(avg_tr.index, avg_tr.values, color=["slateblue", "gold", "crimson"]) #creates the bar chart for the x and y categories, including color
plt.title("Average Grade per Hometown") #title for chart
plt.xlabel("Hometown") #x-axis label
plt.ylabel("Average Grade") #y-axis label
plt.show() #displays
```
#### Output
<img width="629" height="429" alt="image" src="https://github.com/user-attachments/assets/0cc84e80-ba81-4e52-ba72-029beec6656c" />

### Explanation
1. **Accessing Pandas Library** - 
To access Pandas library, the import convention must be used: import pandas as pd.
2. **Accessing MatPlot Library** -
To access MatPlot library, the import convention must be used: import matplotlib.pyplot as plt. This gives us access to plotting functions of matplot for visualization
4. **Loading the Corresponding .xlsx File** -
To load the .xlsx file, we use the code: df = pd.read_excel('board2.xlsx'). This will display the dataframe
5. **Mean Average of the Four Subjects** -
The code: df['Average'] = df[['Math', 'Electronics', 'GEAS', 'Communication']].mean(axis=1) will include a new column "Average" to the dataframe and output that contains the average grade of the four subjects by adding .mean to the code. As for the (axis=1), it operates across the columns therefore helps the code .mean
6. **Figure / Chart Size** -
The code: plt.figure(figsize=(8,5)) this adjusts the length and width size of the figures in the bargraph
7. **Specified Columns** -
The code: avg_tr = df.groupby("Hometown")["Average"].mean() functions by grouping the values in the dataframe rows in the hometown column and only selecting the average column. Thus, it will calculate the average grade per gender.
8. **Creating Bargraph** -
The code: plt.bar(avg_tr.index, avg_tr.values, color=["slateblue", "gold", "crimson"]). The index functions as the x-axis, holding the hometown categories, meanwhile the values functions as the y-axis holding the average grade.
8. **Chart Title** -
The code: plt.title("Average Grade per Hometown") simply functions by adding a title for the chart
9. **X and Y-axis Label** -
The code: plt.xlabel("Hometown") and plt.ylabel("Average Grade") simply functions by adding a title for botht he x and y-axis labels
10. **Display Output** -
The code: plt.show() simply displays the output

























