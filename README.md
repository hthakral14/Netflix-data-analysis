# Netflix-data-analysis
analysis the director,title,release year,cast and plot a bar graph and count plot . Filter the data in the dataset
import pandas as pd 
import seaborn as sns  
import matplotlib.pyplot as pyplot
df=pd.read_csv(r"C:\Users\ashish thakral\Downloads\archive\netflix_titles.csv")
df
#print(df.head(5))
#print(df.shape)
#print(df.columns)
#print(df.info())
df[df.duplicated()]
df.drop_duplicates(inplace=True)
df.isnull()
df.isnull().sum()
#sns.heatmap(df.isnull())
#pyplot.show()#
df.title
df[df['title'].isin(['Squid Game'])]
df[df['title'].str.contains('Squid Game')]
df.head(10)
#df.dtypes
#df['release_year'].value_counts()
#df['release_year'].value_counts().head(10).plot.bar()
#pyplot.show()


df.groupby("type").type.count()
sns.countplot(x='type',data=df)
#pyplot.show()

df[(df['type']== 'Movie') & (df['release_year']==2021)]

df['director'].value_counts().head(10)
df[(df['type']=='Movie') & (df["listed_in"]=='Comedies') ]
df[(df['type']=='TV Show') & (df["country"] =='India')]
