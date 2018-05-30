# Part one: frequency plot
import matplotlib.pyplot as plt
import numpy as np
import csv
plt.style.use('ggplot')
x = []
y = []

with open('2015-totals.csv','r') as f:
    plots = csv.reader(f, delimiter=',')
    for row in plots:
        x.append(row[1])
        y.append(row[2])
plt.hist(y)
fig_size = plt.rcParams["figure.figsize"]
# Set figure width to 12 and height to 9
fig_size[0] = 10
fig_size[1] = 4
plt.rcParams["figure.figsize"] = fig_size
plt.xlabel('Radar_alt')
plt.ylabel('Counts')
plt.title('Wildebeest Movements photo counts')
plt.show()


# on the log scale
import matplotlib.pyplot as plt
import numpy as np
import csv
plt.style.use('ggplot')
x = []
y = []

with open('2015-totals.csv','r') as f:
    plots = csv.reader(f, delimiter=',')
    for column in plots:
        x.append(column[1])
        y.append(column[2])
p = np.nonzero(x)[0]  
q = np.nonzero(y)[0]
plt.semilogy(p,q)
plt.xlabel ('log(radar_alt)')
plt.ylabel ('log(counts)')
plt.title('Log(wildebeest photo counts)')
plt.show()

# scatter plot to show groups spread
import matplotlib.pyplot as plt
import numpy as np
import csv
plt.style.use('ggplot')
radar_alt = []
counts = []

with open('2015-totals.csv','r') as f:
    plots = csv.reader(f, delimiter=',')
    for column in plots:
        radar_alt.append(column[1])
        counts.append(column[2])

plt.scatter(radar_alt,counts)
fig_size = plt.rcParams["figure.figsize"]

# Set figure width to 5 and height to 5
fig_size[0] = 5
fig_size[1] = 5
plt.rcParams["figure.figsize"] = fig_size
plt.xlabel ('Radar_alt')
plt.ylabel ('Counts')
plt.title('Wildebeest Movements')
plt.show()

# Animals-Movements
#Then to develop code to allow a wildebeest to belong to a near by group
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
import seaborn
import csv
from pandas import Series, DataFrame
plt.style.use('ggplot')
radar_alt = []
count = []
date = []
animals=pd.read_csv('2015-totals.csv')
animals.columns=['date','radar_alt','count']
with open('2015-totals.csv','r') as f:
    plots = csv.reader(f, delimiter=',')

    for row in plots:
        radar_alt.append(row[1])
        counts.append(row[2])
#open('2015-totals.csv','r').readlines()[:5]
##animals.head     # To make sure that this worked out, let’s display the top of the table:
#grouping data
group_animals = animals.groupby(['date','radar_alt', 'count'])
#group_animals.size().unstack()
def name_plot(radar_alt, count):
    data = animals_index.loc[radar_alt, count]
    plt.plot(data.index, data.values)
    #plt.figure(figsize = (18, 8))

animal = ['[:5]', '[:6,10]', '[:11,15]', '[:16,20]']
for animal in r:
    animal_plot('radar_alt', count)

plt.legend(count)
