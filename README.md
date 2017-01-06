# Code-and-Report

# -*- coding:
utf-8 -*-

from
sklearn.cluster import KMeans

from
sklearn.decomposition import PCA

from sklearn
import preprocessing

 
import csv

 

data=[]

final =
csv.reader(open('C:/Users/xiaogenggeng/Desktop/xalan-2.4.csv','rb'))

for line in
final:

  data.append(line)

 
feature =
[[float(x) for x in row[3:]] for row in data]

 

feature=preprocessing.scale(feature)

print feature

 

#调用kmeans类

clf =
KMeans(n_clusters=2)

s=
clf.fit(feature)

 

L=len(clf.labels_)

with
open('C:/Users/xiaogenggeng/Desktop/factbug.csv', 'wb') as csvfile:

  spamwriter =
csv.writer(csvfile,dialect='excel')

  for i in range(0, L): 

     spamwriter.writerow([clf.labels_[i]])
