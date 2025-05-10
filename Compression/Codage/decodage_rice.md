# Decodage_Rice

### fonction :


```python
# Les variables : 

binaires = [1, 0, 1, 0, 0, 1]
k = 4
```


```python
import numpy as numpy


def Rice_decode(encoded, k):
    parse = 0
    q = 0

    while encoded[parse] == 1:
        q += 1
        parse += 1

    parse += 1

    r_bits = encoded[parse:parse + k]
    r_str = ''.join(str(bit) for bit in r_bits)
    r = int(r_str, 2)

    valeur = q * (2 ** k) + r
    return valeur






```


```python
resultat = Rice_decode(binaires, k)

print("Le résultat de la décompression est : ", resultat)

```

    Le résultat de la décompression est :  25

