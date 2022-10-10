# Python Cheat Sheet
Koden till detta Cheat Sheet kan kompileras till pdf med en valfri markdown-kompilator. Ett exempel på en fri sådan, som finns online, är [dillinger.io](https://dillinger.io/) (det är bara att göra en copy-paste av koden, inget konto behöver skapas!).
## Matematiska operatorer
| Operator | Operation | Exempel|
| ------ | ------ | ------ |
| `**` | Upphöjt till | `3 ** 2 # Resultat: 9`
| `%` | Modulo | `9 % 2 # Resultat: 1`
| `//` | Heltalsdivision | `9  // 2 # Resultat: 4`
| `/` | Division | `9 / 2 # Resultat: 4.5`
| `*` | Multiplikation  | `2 * 3 # Resultat: 6`
| `-` | Subtraktion | `2 - 3 # Resultat: -1`
| `+` | Addition | `2 + 3 # Resultat: 5`|

Operatorerna ovan är listade i prioriteringsordning.
## Variabler
En variabel är ett namn med ett värde knutet till sig. En variabel är av en specifik *datatyp*. Variabler *tilldelas* ett värde enligt följande exempel (datatyp inom parentes):
```python
pris    = 10                # Heltal (int), utan decimalpunkt
sträcka = 4.5               # Flyttal (float), med decimalpunkt
namn    = "Ada"             # Sträng (str)
is_game_on = True           # Boolesk variabel (bool), kan anta värdena True och False
even5   = [2, 4, 6, 8, 10]  # Lista (list)
```

En variabel kan förändras med t ex `pris += 0.5` (nu kommer `pris` att ha värdet `10.5`, och således också ha bytt datatyp till `float`).
Ett annat exempel är `namn += " Lovelace"`. Nu kommer `namn` att utgöras av strängen `"Ada Lovelace"`.

Vissa datatyper går att konvertera till andra datatyper. T ex ger `str(3.14)` resultatet `"3.14"` (konvertering från `float` till `str`) och `int("9")` ger resultatet `9` (konvertering från `str` till `int`).

## `print`-satsen
För att skriva ut något till konsolen kan en `print`-sats användas. Exempel:
```python
print("Hello, world") # Skriver ut: Hello, world
favorite_number = 42
print(favorite_number) # Skriver ut: 42
print(f"Mitt favorittal är {favorite_number}, förstås.")
# Skriver ut: Mitt favorittal är 42, förstås.
```
## `input`-satsen
Ett program kan vänta på indata från konsolen genom funktionen `input`. Denna funktion returnerar alltid en sträng (`str`). Exempel:
```python
given_name = input("Ange ditt förnamn -> ")
print(f"Hej, {given_name}!")
```

## Jämförelseoperatorer
Följande tilldelningar görs: `a = -2`, `b = a` och `c = 0`. Då kan dessa variabler jämföras t ex enligt följande:

| Operator | Operation | Resultat|
| ------ | ------ | ------ |
| Lika med | `a == b` | `True` |
| Skilt från | `a != b` | `False` |
| Större än | `a > b` | `False` |
| Mindre än | `a < c` | `True` |
|Större än eller lika med| `a >= b`| `True`|
|Mindre än eller lika med| `a <= c`| `True`|

Det går även att jämföra flera variabler i en följd, t ex `a == b < c`, vilket returnar `True`.

## Logiska operatorer
Det finns tre inbyggda logiska operatorer i Python: `and`, `or` och `not`. Följande tilldelningar görs: `a = True`, `b = False`, `c = True` och `d = False`.

| Operator | Operation | Resultat|
| ------ | ------ | ------ |
| `and` | `a and c` | `True` |
| `and` | `a and b` | `False` |
| `or` | `a or b` | `True` |
| `or` | `b or d` | `False` |
| `not` | `not b` | `True` |
| `not` | `not a` | `False` |

Det går att tillämpa flera logiska operatorer i en följd, t ex `(a and not b) or (a and d)`, vilket returnerar `True`.

## Villkor
I Python prövas ett *villkor* med `if`-satser. Syntaxen är
```python
if <booleskt_uttryck_1>:
    <gör något om booleskt_uttryck_1 är True>
elif <booleskt_uttryck_2>:
    <Om inte booleskt_uttryck_1 var True, gör något annat om booleskt_uttryck_2 är True>
else:
    <Gör något annat om inget av de tidigare prövade booleska uttrycken var True>
```

Detta kan exemplifieras i följande program:
```python
my_number = 42
if my_number > 100:
    print("Talet är större än hundra.")
elif my_number >= 0:
    print("Talet är större än eller lika med noll")
else:
    print("Talet är negativt")
# Programmet skriver ut: Talet är större än eller lika med noll.
```

## Loopar
### `while`-loopar
I en loop kan kod processas flera gånger. Exempel:
```python
a  = 0
while a < 5:
    print(a, end=" ")
    a += 1
# Skriver ut 0 1 2 3 4
```

Det går att kontrollera hur loopen körs genom nyckelorden `break` (avbryter aktuell loop) och `continue` (startar om loopen från början). Exempel:

```python
a = 0
while True:
    if a == 5:
        a = 7
        continue
    if a == 9:
        break
    print(a, end=" ")
    a += 1
# Skriver ut: 0 1 2 3 4 7 8
```
### `for`-loopar
Se avsnitt Listor, underavsnitt Loopa genom listor. Nyckelorden `break` och `continue` fungerar på samma sätt i `for`-loopar som i `while`-loopar.
## Listor
### Åtkomst av element
Låt `lst = [10, 20, 30, 40, 50]`. Då gäller att `lst[0]` har värdet `10` och `lst[1]` har värdet `20` osv. Det gäller också att `lst[-1]` har värdet `50` och `lst[-2]` har värdet `40` osv.

Det går att komma åt delar av listan går det att göra
```python
lst[2:4]   # Resultat: [20, 30] (Elementen mellan två index)
lst[2:]    # Resultat: [20, 30, 40, 50] (Elementen fr o m index nr. 2)
lst[:4]    # Resultat: [10, 20, 30] (Elementen till index nr. 4 (men inte inklusive detta))
lst[1:4:2] # Resultat: [20, 40] (Vartannat element mellan två index)
lst[::-1]  # Resultat: [50, 40, 30, 20, 10] (Baklänges)
```

### Skapa listor
En lista kan skapas med den inbyggda funktionen `range`. T ex `long_list = list(range(100, 1000, 2))`. Detta kommer att skapa listan `[100, 102, 104,..., 998]`.

### Antal element i en lista
Antalet element i en lista erhålls med den inbyggda funktionen `len`. Exempel:
```python
lst = list(range(100, 1000, 2))
print(len(lst)) # Skriver ut antalet element: 450
```

### Kontrollera om ett element finns i en lista
Förekomsten av ett element i en lista kan kontrolleras enligt följande:
```python
long_list = list(range(100, 1000, 2))
500 in long_list # Returnerar True
501 in long_list # Returnerar False
```

### Loopa genom listor
En lista kan gås igenom element för element i en `for`-loop enligt fäljande:
```python
lst = list(range(5, 0, -1)) # Skapar listan [5, 4, 3, 2, 1]
for i in lst:
    print(i, end=" ")
# Matar ut: 5 4 3 2 1
```

### Lägga till och ta bort element från en lista
Följande exempel visar några tilläggs- och borttagningsoperationer:
```python
lst = [10, 20, 30, 40]
lst.append(50) # lst är nu [10, 20, 30, 40, 50]
lst.remove(30) # lst är nu [10, 20, 40, 50]
del(lst[1])    # lst är nu [10, 40, 50]
lst.pop()      # Returnerar 50, lst är nu [10, 40]
a = lst.pop()  # a är nu 40, lst är nu [10]
```

### Sortering av en lista
Följande exempel visar hur en lista kan sorteras
```python
lst = [5, 3, 10, -1, 8]
sorted(lst) # Returnerar [-1, 3, 5, 8, 10]; lst är fortfarande [5, 3, 10, -1, 8]
lst.sort()  # Returnerar inget, lst är ändrad till [-1, 3, 5, 8, 10]
lst.sort(reverse=True) # lst är nu [10, 8, 5, 3, -1]
```

## Funktioner
En funktion i är ett kodblock som kan anropas och processas som en separat del i programmet. Den kan, men behöver inte, returnera ett värde (tal, sträng, lista,...).

### Exempel på funktion utan returvärde
```python
def greet(name):
    print(f"Hej {name}!")
greet("Alice") # Funktionen körs, och skriver ut Hej Alice!
```

### Exempel på funktion med returvärde
```python
def divide(divisor, dividend):
    if dividend == 0:
        return("Odefinierat!")
    else:
        return divisor / dividend
a = divide(10, 5) # a är nu 2.0
a = divide(10, 0) # a är nu "Odefinierat!"
```

## Slumptal
Funktioner som har med slumptal att göra finns i en separat *modul*, nämligen `random`.

### Exempel på slumpmässigt heltal
```python
import random as rand
random_int = rand.randint(0, 99)
# random_int kommer nu att innehålla ett slumptal mellan, och inklusive, 0 och 99
```

### Exempel på slumpmässigt flyttal
```python
import random as rand
random_float = rand.random()
# random_float kommer nu att innehålla ett slumpmässigt flyttal mellan 0 och 1 (dock ej inklusive 1).
```

### Exempel på att blanda en lista
```python
import random as rand
lst = list(range(0, 10)) 
rand.shuffle(lst) # lst kommer nu att vara blandad
```

### Exempel på att plocka ut ett slumpmässigt tal från en lista
```python
import random as rand
lst = list(range(0, 10))
rand.choice(lst)
# Returnerar ett av talen i lst, taget på måfå. lst är oförändrad.
```
