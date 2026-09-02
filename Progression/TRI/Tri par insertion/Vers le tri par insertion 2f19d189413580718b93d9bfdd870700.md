# Vers le tri par insertion

<aside>
💡

**Principe de l'algorithme**

Pour toutes les valeurs, en commençant par la deuxième :

- Tant qu'on trouve à gauche une valeur supérieure et qu'on n'est pas revenu à la première valeur, on échange ces deux valeurs.
</aside>

Pour tester son code :

```python
>>> maliste = [7, 5, 2, 8, 1, 4]
>>> tri_insertion(maliste)
>>> maliste
[1, 2, 4, 5, 7, 8]
```

```python
def tri_insertion(lst):
    '''trie en place la liste lst donnée en paramètre'''
```

```python
def tri_insertion(lst):
    '''trie en place la liste lst donnée en paramètre'''
    for i in range(..., ...):                 
        ... = ...                                    
        while ... > ... and ... > ... :      
            ..., ... = ..., ...      
            ... = ...                              
```

```python
def tri_insertion(lst):
    '''trie en place la liste lst donnée en paramètre'''
    for i in range(..., len(lst)):                 
        k = ...                                    
        while k > ... and lst[...] > lst[...] :      
            lst[...], lst[...] = lst[...], lst[...]      
            k = ...                               
```

```python
def tri_insertion(lst):
    '''trie en place la liste lst donnée en paramètre'''
    for i in range(1, len(lst)):                 
        k = ...                                    
        while k > ... and lst[k-1] > lst[k] :      
            lst[k], lst[k-1] = lst[...], lst[...]      
            k = ...      
```

```python
def tri_insertion(lst):
    '''trie en place la liste lst donnée en paramètre'''
    for i in range(..., ...):                 
        ... = ...                                    
        while ...... and ...... :      
            lst[...], lst[...] = lst[...], lst[...]        
            ... = ...   
```

[Aide tri Insertion](Vers%20le%20tri%20par%20insertion/Aide%20tri%20Insertion%202fa9d189413580ef8e4ee928a0b39296.md)