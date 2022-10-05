
!pwd
/home/cse-lab/Desktop/b192118
!ls
b192118.ipynb  MELBOURNE_HOUSE_PRICES_LESS.csv
import pandas  as pd
df = pd.read_csv("MELBOURNE_HOUSE_PRICES_LESS.csv")
df.head()
Suburb	Address	Rooms	Type	Price	Method	SellerG	Date	Postcode	Regionname	Propertycount	Distance	CouncilArea
0	Abbotsford	49 Lithgow St	3	h	1490000.0	S	Jellis	1/04/2017	3067	Northern Metropolitan	4019	3.0	Yarra City Council
1	Abbotsford	59A Turner St	3	h	1220000.0	S	Marshall	1/04/2017	3067	Northern Metropolitan	4019	3.0	Yarra City Council
2	Abbotsford	119B Yarra St	3	h	1420000.0	S	Nelson	1/04/2017	3067	Northern Metropolitan	4019	3.0	Yarra City Council
3	Aberfeldie	68 Vida St	3	h	1515000.0	S	Barry	1/04/2017	3040	Western Metropolitan	1543	7.5	Moonee Valley City Council
4	Airport West	92 Clydesdale Rd	2	h	670000.0	S	Nelson	1/04/2017	3042	Western Metropolitan	3464	10.4	Moonee Valley City Council
df.head(3)
Suburb	Address	Rooms	Type	Price	Method	SellerG	Date	Postcode	Regionname	Propertycount	Distance	CouncilArea
0	Abbotsford	49 Lithgow St	3	h	1490000.0	S	Jellis	1/04/2017	3067	Northern Metropolitan	4019	3.0	Yarra City Council
1	Abbotsford	59A Turner St	3	h	1220000.0	S	Marshall	1/04/2017	3067	Northern Metropolitan	4019	3.0	Yarra City Council
2	Abbotsford	119B Yarra St	3	h	1420000.0	S	Nelson	1/04/2017	3067	Northern Metropolitan	4019	3.0	Yarra City Council
df.tail(1)
Suburb	Address	Rooms	Type	Price	Method	SellerG	Date	Postcode	Regionname	Propertycount	Distance	CouncilArea
63022	Williams Landing	1 Diadem Wy	4	h	NaN	SP	Aussie	31/03/2018	3027	Western Metropolitan	1999	17.6	Wyndham City Council
df.dropna()
Suburb	Address	Rooms	Type	Price	Method	SellerG	Date	Postcode	Regionname	Propertycount	Distance	CouncilArea
0	Abbotsford	49 Lithgow St	3	h	1490000.0	S	Jellis	1/04/2017	3067	Northern Metropolitan	4019	3.0	Yarra City Council
1	Abbotsford	59A Turner St	3	h	1220000.0	S	Marshall	1/04/2017	3067	Northern Metropolitan	4019	3.0	Yarra City Council
2	Abbotsford	119B Yarra St	3	h	1420000.0	S	Nelson	1/04/2017	3067	Northern Metropolitan	4019	3.0	Yarra City Council
3	Aberfeldie	68 Vida St	3	h	1515000.0	S	Barry	1/04/2017	3040	Western Metropolitan	1543	7.5	Moonee Valley City Council
4	Airport West	92 Clydesdale Rd	2	h	670000.0	S	Nelson	1/04/2017	3042	Western Metropolitan	3464	10.4	Moonee Valley City Council
...	...	...	...	...	...	...	...	...	...	...	...	...	...
63016	Frankston	4/34 Petrie St	2	u	347700.0	SP	Aquire	31/03/2018	3199	South-Eastern Metropolitan	17055	38.0	Frankston City Council
63017	Preston	229 Murray Rd	3	h	808000.0	S	RW	31/03/2018	3072	Northern Metropolitan	14577	8.4	Darebin City Council
63018	Roxburgh Park	3 Carr Pl	3	h	566000.0	S	Raine	31/03/2018	3064	Northern Metropolitan	5833	20.6	Hume City Council
63019	Roxburgh Park	9 Parker Ct	3	h	500000.0	S	Raine	31/03/2018	3064	Northern Metropolitan	5833	20.6	Hume City Council
63020	Roxburgh Park	5 Parkinson Wy	3	h	545000.0	S	Raine	31/03/2018	3064	Northern Metropolitan	5833	20.6	Hume City Council
48433 rows × 13 columns

print(df.shape)
(63023, 13)
rooms=df["Rooms]

rooms=df["Rooms"]
print(rooms)
0        3
1        3
2        3
3        3
4        2
        ..
63018    3
63019    3
63020    3
63021    3
63022    4
Name: Rooms, Length: 63023, dtype: int64
price=df["Price"]
import matplotlib.pyplot as plt
fig = plt.figure()
plt.hist(x =price, color = "lightblue", ec="black", lw=2, bins=20)
plt.xlabel("Price range")
plt.ylabel("Number of houses")
plt.title("HISTOGRAPH OF HOUSES", color = "blue")
plt.grid(True)
plt.show()
/home/cse-lab/anaconda3/lib/python3.7/site-packages/numpy/lib/histograms.py:839: RuntimeWarning: invalid value encountered in greater_equal
  keep = (tmp_a >= first_edge)
/home/cse-lab/anaconda3/lib/python3.7/site-packages/numpy/lib/histograms.py:840: RuntimeWarning: invalid value encountered in less_equal
  keep &= (tmp_a <= last_edge)

rooms_count = df["Rooms"].value_counts()
rooms_count = dict(rooms_count)
rooms_count
{3: 27950,
 4: 15747,
 2: 13248,
 5: 3434,
 1: 2111,
 6: 424,
 7: 61,
 8: 29,
 10: 7,
 9: 5,
 12: 4,
 31: 1,
 16: 1,
 11: 1}
print(min(price))
print(max(price))
85000.0
11200000.0
print(rooms_count)
{3: 27950, 4: 15747, 2: 13248, 5: 3434, 1: 2111, 6: 424, 7: 61, 8: 29, 10: 7, 9: 5, 12: 4, 31: 1, 16: 1, 11: 1}
a = rooms_count.keys()

b = rooms_count.values()
region_count= dict(region_count)
fig = plt.figure(figsize=(6,6))
plt.pie(x =b, labels = a)
plt.legend()
plt.show()

region_count=df["Regionname"].value_counts()
region_count = dict(region_count)
r=list(region_count.keys())
rc=list(region_count.values())
fig = plt.figure(figsize=(6,6))
plt.pie(x =rc, labels=r)
plt.legend()
plt.show()

 
fig = plt.figure(figsize=(10,10))
plt.bar(height =b, x= a)
plt.xlabel("no.of rooms")
plt.ylabel("no.of houses")
plt.show()

price=df["Price"]
price=list(price)
price = list(price)

distance=df["Distance"]
distance= list(distance)
fig=plt.figure(figsize = (10, 10))
plt.plot(distance, price, color = "darkblue", linestyle="", marker="o", markeredgecolor = "black", markerfacecolor = "red")
plt.xlabel("Distance")
plt.ylabel("Price")
plt.title("Distance vs Price")
plt.show()

 
