# Decodage_Rice

### fonction :


```python
# Les variables : 

binaires = [1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 1]
k = 10
```


```python
import numpy as numpy


def Rice_decode(encoded, k):
    valeur = 0
    parse = 0
    while encoded[parse] == 1:
        parse += 1
    valeur = parse * k
    print("valeur = ", valeur)
    parse += 1
    reste = 0
    test = int(numpy.log2(k))
    for i in range(test, 0, -1):
        print("i = ", i)
        reste = reste + encoded[parse + i] * (2 ** i)
    parse += 1
    print("reste", reste)
    valeur += reste
    return valeur





```


```python
resultat = Rice_decode(binaires, k)

print("Le résultat de la décompression est : ", resultat)

```

    valeur =  20
    i =  3
    i =  2
    i =  1
    reste 0
    Le résultat de la décompression est :  20

