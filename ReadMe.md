# IRIS Data Set Analysis

*The IRIS dats set contains 3 types of species.*
	_Species are named as following :_
	..* Setosa
	..* Virginica
	..* Versicolor

### Libraries and Packages required
	_In order to analyze the data set, we have to import the following libraries.(For the current github code)_
	..-> pandas
	..-> matplotlib
	..-> IPython
	..-> pygal
	..-> seaborn
	..-> numpy
	

### Read CSV file
_*To analyse a data, we have to read the cvs file, which can be done using pandas.*_

_Below snipet will help to understand, how we can read a csv file._

```python
iris = pd.read_csv("path/urfile.csv")
```

### Analyse Data 

_We can use this extracted data frame of iris to analyse._

For Example : 

```python
	iris.head()
```

This will give us number of data sets present for each species.

_In case of IRIS data set, below will be the output :_


|Id	|SepalLengthCm|	SepalWidthCm|	PetalLengthCm|	PetalWidthCm|	Species		|
|---|:-----------:|:-----------:|:--------------:|:------------:|--------------:|
| 0	| 5.1		  |  3.5		|	1.4			 |	0.2			|	Iris-setosa |
| 1	| 4.9		  |	 3.0 	    |	1.4			 |	0.2			|	Iris-setosa |
| 2	| 4.7		  |	 3.2		|	1.3			 |	0.2			|	Iris-setosa |
| 3	| 4.6		  |	 3.1		|	1.5			 |	0.2			|	Iris-setosa |
| 4	| 5.0		  |	 3.6		|	1.4			 |	0.2		  	|	Iris-setosa |



### How to plot graphs of the data analyzed.

_We have to first collect some data from the csv file, so that we can input
our data to the graph. _

In this example, the graph ploted is bar graph.This graph is ploting the data 
of the number od data available for each Species.

Below is the snipet for the bargraph.
Note : In this code, we are mostly using pygal to plot graphs.

```python
bar = pygal.Bar()
bar.title = 'Analyzing Data of Species'
bar.x_labels = map (str,('Setosa', 'Versicolor','Virginica'))
bar.add('Iris Data Set', iris["Species"].value_counts())
bar.render_to_file('Species_data_set_count.svg')
HTML(html_pygal.format(pygal_render=bar.render()))
```






