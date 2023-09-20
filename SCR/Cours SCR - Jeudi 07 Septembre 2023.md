### Exercice 1 :
On a : 

1)
```
559be7117000-559be7118000 r-xp 00001000 103:02 22945923 /home/matth/Documents/Info/SCR/src/executable
```

```
main    =       0x559be7117179
```

559be7117000-559be7118000 est un **Intervale** et comme 0x559be7117179 est compris 
entre xxx7000 et xxx8000 alors le main est :

```
559be7117000-559be7118000 r-xp 00001000 103:02 22945923 /home/matth/Documents/Info/SCR/src/executable
```

Contenue dans le code

2)
```
7fffa72ee000-7fffa730f000 rw-p 00000000 00:00 0                          [stack]
```

```
&argc   =       0x7fffa730ccec
&i      =       0x7fffa730ccfc
```

Contenue dans la Pile == Stack

3)
```
559be711a000-559be711c000 rw-p 00003000 103:02 22945923 /home/matth/Documents/Info/SCR/src/executable
```

```
&j      =       0x559be711b000  
t       =       0x559be711a060
```

Contenue dans le Data (Car pas le droit d'execution)

4)
```
559be7e3e000-559be7e5f000 rw-p 00000000 00:00 0                          [heap]
```

```
m       =       0x559be7e3e2a0
```

Contenue dans le tas == Heap

### Exercice 1.Bis

