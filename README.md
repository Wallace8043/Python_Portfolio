# Python_Portfolio
This is the python portfolio that I learned during BISC 450C

## Python Fundamentals

```python
weight_kg = 60
```


```python
print(weight_kg)
```

    60



```python
weight_kg = 60.3
```


```python
patient_name = "Jon Smith"
```


```python
patient_id = "001"
```


```python
weight_lb = 2.2 * weight_kg
print(weight_lb)
```

    132.66



```python
patient_id = "inflam_" + patient_id
print(patient_id)
```

    inflam_001



```python
print(patient_id, "weight in kilograms:" , weight_kg)
```

    inflam_001 weight in kilograms: 60.3



```python
print(type(60.3))
print(type(patient_id))
```

    <class 'float'>
    <class 'str'>



```python
print("weight in lbs:" , 2.2 * weight_kg)
```

    weight in lbs: 132.66



```python
print(weight_kg)
```

    60.3



```python
weight_kg = 65.0
print("weight in kilograms is now:" , weight_kg)
```

    weight in kilograms is now: 65.0



```python

```

## Analyzing Data 1,2,& 3

```python
import numpy
```


```python
numpy.loadtxt(fname = "inflammation-01.csv", delimiter = ",")

```




    array([[0., 0., 1., ..., 3., 0., 0.],
           [0., 1., 2., ..., 1., 0., 1.],
           [0., 1., 1., ..., 2., 1., 1.],
           ...,
           [0., 1., 1., ..., 1., 1., 1.],
           [0., 0., 0., ..., 0., 2., 0.],
           [0., 0., 1., ..., 1., 1., 0.]])




```python
data = numpy.loadtxt(fname = "inflammation-01.csv", delimiter = ",")

```


```python
print(data)
```

    [[0. 0. 1. ... 3. 0. 0.]
     [0. 1. 2. ... 1. 0. 1.]
     [0. 1. 1. ... 2. 1. 1.]
     ...
     [0. 1. 1. ... 1. 1. 1.]
     [0. 0. 0. ... 0. 2. 0.]
     [0. 0. 1. ... 1. 1. 0.]]



```python
print(type(data))
```

    <class 'numpy.ndarray'>



```python
print(data.shape)
```

    (60, 40)



```python
print("first value in data:" , data[0,0])
```

    first value in data: 0.0



```python
print("middle value in data:" , data[29,19])
```

    middle value in data: 16.0



```python
print(data[0:4, 0:10])
```

    [[0. 0. 1. 3. 1. 2. 4. 7. 8. 3.]
     [0. 1. 2. 1. 2. 1. 3. 2. 2. 6.]
     [0. 1. 1. 3. 3. 2. 6. 2. 5. 9.]
     [0. 0. 2. 0. 4. 2. 2. 1. 6. 7.]]



```python
print(data[5:10, 0:10])
```

    [[0. 0. 1. 2. 2. 4. 2. 1. 6. 4.]
     [0. 0. 2. 2. 4. 2. 2. 5. 5. 8.]
     [0. 0. 1. 2. 3. 1. 2. 3. 5. 3.]
     [0. 0. 0. 3. 1. 5. 6. 5. 5. 8.]
     [0. 1. 1. 2. 1. 3. 5. 3. 5. 8.]]



```python
small = data[:3, 36:]
```


```python
print("small is:\n", small)
```

    small is:
     [[2. 3. 0. 0.]
     [1. 1. 0. 1.]
     [2. 2. 1. 1.]]



```python
print(numpy.mean(data))
```

    6.14875



```python
maxval, minval, stdval = numpy.amax(data), numpy.amin(data),numpy.std(data)

```


```python
print(maxval)
print(minval)
print(stdval)
```

    20.0
    0.0
    4.613833197118566



```python
maxval = numpy.amax(data)
minval = numpy.amin(data)
stdval = numpy.std(data)
```


```python
print(maxval)
print(minval)
print(stdval)
```

    20.0
    0.0
    4.613833197118566



```python
print("maximum inflammation:", maxval)
print("minimum inflammation:", minval)
print("standard deviation:", stdval)
```

    maximum inflammation: 20.0
    minimum inflammation: 0.0
    standard deviation: 4.613833197118566



```python
patient_0 = data[0, :]

print("maximum inflammation for patient 0:", numpy.amax(patient_0))
```

    maximum inflammation for patient 0: 18.0



```python
print("maximum inflammation for patient 2:", numpy.amax(data[2, :]))
```

    maximum inflammation for patient 2: 19.0



```python
print(numpy.mean(data, axis = 0))
```

    [ 0.          0.45        1.11666667  1.75        2.43333333  3.15
      3.8         3.88333333  5.23333333  5.51666667  5.95        5.9
      8.35        7.73333333  8.36666667  9.5         9.58333333 10.63333333
     11.56666667 12.35       13.25       11.96666667 11.03333333 10.16666667
     10.          8.66666667  9.15        7.25        7.33333333  6.58333333
      6.06666667  5.95        5.11666667  3.6         3.3         3.56666667
      2.48333333  1.5         1.13333333  0.56666667]



```python
print(numpy.mean(data, axis = 0).shape)
```

    (40,)



```python
print(numpy.mean(data, axis = 1))
```

    [5.45  5.425 6.1   5.9   5.55  6.225 5.975 6.65  6.625 6.525 6.775 5.8
     6.225 5.75  5.225 6.3   6.55  5.7   5.85  6.55  5.775 5.825 6.175 6.1
     5.8   6.425 6.05  6.025 6.175 6.55  6.175 6.35  6.725 6.125 7.075 5.725
     5.925 6.15  6.075 5.75  5.975 5.725 6.3   5.9   6.75  5.925 7.225 6.15
     5.95  6.275 5.7   6.1   6.825 5.975 6.725 5.7   6.25  6.4   7.05  5.9  ]



```python
import matplotlib.pyplot
image = matplotlib.pyplot.imshow(data)
matplotlib.pyplot.show()
```


![png](output_23_0.png)
![output_23_0](https://github.com/user-attachments/assets/aa32a84f-a8b6-47c3-a670-67b92a42aa91)



```python
ave_inflammation = numpy.mean(data, axis = 0)
ave_plot = matplotlib.pyplot.plot(ave_inflammation)
matplotlib.pyplot.show()
```


![png](output_24_0.png)
![output_24_0](https://github.com/user-attachments/assets/6e7559ce-3764-432b-8372-4e35be5231ff)



```python
max_plot = matplotlib.pyplot.plot(numpy.amax(data, axis = 0))
matplotlib.pyplot.show()
```


![png](output_25_0.png)
![output_25_0](https://github.com/user-attachments/assets/3f2c019c-ebf8-4207-b85b-5bf0db15df73)



```python
min_plot = matplotlib.pyplot.plot(numpy.amin(data, axis = 0))
matplotlib.pyplot.show()
```


![png](output_26_0.png)
![output_26_0](https://github.com/user-attachments/assets/6713cbd0-153e-4052-95f0-c393ec6a733f)



```python
fig = matplotlib.pyplot.figure(figsize =(10.0, 3.0))

axes1 = fig.add_subplot(1, 3, 1)
axes2 = fig.add_subplot(1, 3, 2)
axes3 = fig.add_subplot(1, 3, 3)

axes1.set_ylabel("average")
axes1.plot(numpy.mean(data, axis = 0))

axes2.set_ylabel("max")
axes2.plot(numpy.amax(data, axis = 0))

axes3.set_ylabel("min")
axes3.plot(numpy.amin(data, axis = 0))

fig.tight_layout()

matplotlib.pyplot.savefig("inflammation.png")
matplotlib.pyplot.show()
```


![png](output_27_0.png)
![output_27_0](https://github.com/user-attachments/assets/3b29204f-8482-4ef8-90eb-d2c78456cf10)



```python

```

## Storing Values in Lists

```python
odds = [1, 3, 5, 7]
print("odds are:", odds)
```

    odds are: [1, 3, 5, 7]



```python
print("first element:", odds[0])
print("last element:", odds[3])
print('"-1" element:', odds[-1])
```

    first element: 1
    last element: 7
    "-1" element: 7



```python
names = ["Curie", "Darwing", "Turing"]

print("names is originally:", names)
names[1] = "Darwin"
print("final value of names:", names)
```

    names is originally: ['Curie', 'Darwing', 'Turing']
    final value of names: ['Curie', 'Darwin', 'Turing']



```python
odds.append(11)
print("odds after adding a value:", odds)
```

    odds after adding a value: [1, 3, 5, 7, 11]



```python
removed_element = odds.pop(0)
print("odds after removing the first element:", odds)
print("removed_element:", removed_element)
```

    odds after removing the first element: [3, 5, 7, 11]
    removed_element: 1



```python
odds.reverse()
print("odds after reversing:", odds)
```

    odds after reversing: [11, 7, 5, 3]



```python
odds = [3, 5, 7]
primes = odds
primes.append(2)
print("primes:", primes)
print("odds:", odds)
```

    primes: [3, 5, 7, 2]
    odds: [3, 5, 7, 2]



```python
odds = [3, 5, 7]
primes = list(odds)
primes.append(2)
print("primes:", primes)
print("odds:", odds)
```

    primes: [3, 5, 7, 2]
    odds: [3, 5, 7]



```python
binomial_name = "Drosophila melanogaster"
group = binomial_name[0:10]
print("group:", group)

species = binomial_name[11:23]
print("species:", species)

chromosomes = ['X','Y','2','3','4']
autosomes = chromosomes[2:5]
print("autosomes:", autosomes)

last = chromosomes[-1]
print("last:", last)
```

    group: Drosophila
    species: melanogaster
    autosomes: ['2', '3', '4']
    last: 4



```python
date = "Monday 4 January 2023"
day = date[0:6]
print("Using 0 to begin range:", day)
day = date[:6]
print("Omitting beginning index:", day)
```

    Using 0 to begin range: Monday
    Omitting beginning index: Monday



```python
months = ['jan', 'feb', 'mar', 'apr', 'may', 'jun', 'jul', 'aug', 'sep','oct','nov','dec']
sond = months[8:12]
print("With known last position:", sond)

sond = months[8:len(months)]
print("Using len() to get last entry:", sond)

sond = months[8:]
print("Omitting ending index:", sond)
```

    With known last position: ['sep', 'oct', 'nov', 'dec']
    Using len() to get last entry: ['sep', 'oct', 'nov', 'dec']
    Omitting ending index: ['sep', 'oct', 'nov', 'dec']



```python

```
