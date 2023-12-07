```python
import numpy as np
```


```python
f = ('tipsf (2).csv')
```


```python
x=np.genfromtxt(f,delimiter=',',skip_header = True)
x
```




    array([[  0.  ,  16.99,   1.01, ...,   1.  ,   0.  ,   2.  ],
           [  1.  ,  10.34,   1.66, ...,   1.  ,   0.  ,   3.  ],
           [  2.  ,  21.01,   3.5 , ...,   1.  ,   0.  ,   3.  ],
           ...,
           [241.  ,  22.67,   2.  , ...,   0.  ,   0.  ,   2.  ],
           [242.  ,  17.82,   1.75, ...,   0.  ,   0.  ,   2.  ],
           [243.  ,  18.78,   3.  , ...,   2.  ,   0.  ,   2.  ]])



## 1) What is the total bill value?


```python
total_billvalue = np.sum(x[:,1])
total_billvalue

```




    4827.77



## 2)what is the total tip value?


```python
total_tip = np.sum(x[:,2])
total_tip
```




    731.5799999999999



## 3) count how may sun,sat,thu,fri, are there?


```python
a,c =np.unique(x[:,5],return_counts = True)
a,c
```




    (array([0., 1., 2., 3.]), array([87, 76, 62, 19], dtype=int64))




```python
for i,g in zip(a,c):
    print(f'{int(i)},{g}')
```

    0,87
    1,76
    2,62
    3,19
    

## 4)How many smokers are there?


```python
b,d = np.unique(x[:,4],return_counts = True)
b,d
```




    (array([0., 1.]), array([151,  93], dtype=int64))




```python
for a,c in zip(b,d):
    print(f'{int(a)},{c}')
```

    0,151
    1,93
    

## 5) What is the avg tip given by female and male?


```python
f = np.unique(x[:,3],return_counts=True)
f
```




    (array([0., 1.]), array([ 87, 157], dtype=int64))




```python
h ,k = x[:,2], x[:,3]
```


```python
import numpy as np  # Make sure to import numpy if you're using np.mean()

for i in k:
    if i == 0:
        n = np.mean(h[k==0])  # Calculate mean based on condition i == 0
    elif i == 1:
        m = np.mean(h[k==1])  # Calculate mean based on condition i == 1
print(n,m)

```

    2.8334482758620685 3.0896178343949043
    

## 6)How much amount have been spent by female & male?


```python
tip_column=x[:,2]
gender_column=x[:,3]
bill_column=x[:,1]
```


```python
female_tip = np.sum(tip_column[gender_column==0])
male_tip = np.sum(tip_column[gender_column==1])
```


```python
female_tip
```




    246.50999999999996




```python
male_tip
```




    485.07




```python
female_bill = np.sum(bill_column[gender_column==0])
male_bill = np.sum(bill_column[gender_column==1])
```


```python
female_bill
```




    1570.9499999999996




```python
male_bill
```




    3256.8199999999997




```python
total_female_spent,total_male_spent=female_bill+female_tip,male_bill+male_tip
```


```python
print(f'female total spent is :{total_female_spent}')
print(f'male total spent is :{total_male_spent}')
```

    female total spent is :1817.4599999999996
    male total spent is :3741.89
    

## 7)what is the min and max tip given?


```python
min_tip = np.min(tip)
max_tip = np.max(tip)
print(f'the min tip given is:{min_tip}')
print(f'the max tip given is:{max_tip}')
```

    the min tip given is:1.0
    the max tip given is:10.0
    

## 8)How many males and females are going for dinner ?


```python
gender = x[:,3]
time =x[:,6] 
female_dinner = np.sum((gender==0) & (time==1))
male_dinner = np.sum((gender==1) & (time==1))
print(f'the no of females going to dinner is:{female_dinner}')
print(f'the no of males going to dinner is:{male_dinner}')
      
```

    the no of females going to dinner is:35
    the no of males going to dinner is:33
    

## How many males and females are going for lunch?


```python
gender = x[:,3]
time =x[:,6] 
female_lunch = np.sum((gender==0) & (time==0))
male_lunch = np.sum((gender==1) & (time==0))
print(f'the no of females going to lunch is:{female_lunch}')
print(f'the no of males going to lunch is:{male_lunch}')
      
```

    the no of females going to lunch is:52
    the no of males going to lunch is:124
    

## 9)Find out the Average of Size?


```python
size = x[:,7]
```


```python
avg_size = np.mean(size)
print(f'the average size is:{avg_size}')
```

    the average size is:2.569672131147541
    

## 10) How many female and male smokers are there?


```python
gender = (x[:,3])
smokers =(x[:,4])
female_smoker = np.sum((gender==0) & (smokers==1))
male_smoker = np.sum((gender==1) & (smokers==1))
print(f'the female smokers are:{female_smoker}')
print(f'the male smokers are:{male_smoker}')
```

    the female smokers are:33
    the male smokers are:60
    


```python

```
