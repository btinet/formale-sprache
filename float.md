# Formale Sprache

## Dezimalzahlen darstellen

- 0,04
- -0,104
- 1340,0232
- -9830,120920
- 130
- -130

### Terminale Symbole 

- '0', '1', '2', '3', '4', '5', '6', '7', '8', '9', '-', ',', 'e'

### Nicht-terminale Symbole

- zero = '0'
- vz = '-'
- tz = ','
- integer = '1' | '2' | '3' | '4' | '5' | '6' | '7' | '8' | '9'
- integerOrZero = integer | zero
- integerNotZero = integer {integerOrZero} {integer}


- leadingZero = [vz] zero tz
- leadingInteger = [vz] integer tz

````agsl
float = ( ( (leadingZero | leadingInteger) {integerOrZero} ) | (integerNotZero {integerOrZero}) ) [(e [vz] integerOrZero {integerNotZero} )]
````

