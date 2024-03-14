### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 14-03-2024
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```
# Visitor segmentation based on characteristics
import pandas as pd
import matplotlib.pyplot as plt

# read the data
visitor_df=pd.read_csv('/content/clustervisitor (1).csv')

# Perform segmentation based on characteristics (e.g., age groups)
age_groups={
    'Young':(visitor_df['Age']<=30),
    'Middle-aged':((visitor_df['Age']>30) & (visitor_df['Age'] <=50)),
    'Eldery':(visitor_df['Age'] > 50)
}

for group,condition in age_groups.items():
  visitors_in_group=visitor_df[condition]
  print(f"Visitors in {group} age group")
  print(visitors_in_group)
  print()

```
### Output:
![Screenshot 2024-03-14 222013](https://github.com/MaithreyanDinakaran/WDM_EXP4/assets/119104032/800f1825-933a-497b-a50b-9519df5339ff)

### Visualization:
```
# Create a list to store counts of visitors in each age group
visitor_counts = []

# Count visitors in each age group
for group, condition in age_groups.items():
    count = visitor_df[condition].shape[0]
    visitor_counts.append(count)

# Define age group labels
age_group_labels = list(age_groups.keys())

# Plot a bar chart
import matplotlib.pyplot as plt

plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:
![image](https://github.com/MaithreyanDinakaran/WDM_EXP4/assets/119104032/53f1b9c6-4daf-4639-9077-131d2ec5fd25)


### Result:
Thus the cluster and visitor segmentation for navigation patterns was implemented successfully in python.
