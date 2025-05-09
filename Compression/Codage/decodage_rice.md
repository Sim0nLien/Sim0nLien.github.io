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

    # Lire le code unaire : nombre de 1 avant le premier 0
    while encoded[parse] == 1:
        q += 1
        parse += 1

    # Sauter le '0' final du code unaire
    parse += 1

    # Lire k bits pour le reste
    r_bits = encoded[parse:parse + k]
    r_str = ''.join(str(bit) for bit in r_bits)  # convertir en chaîne binaire
    r = int(r_str, 2)

    # Calculer la valeur originale
    valeur = q * (2 ** k) + r
    return valeur






```


```python
resultat = Rice_decode(binaires, k)

print("Le résultat de la décompression est : ", resultat)

```

    Le résultat de la décompression est :  25

