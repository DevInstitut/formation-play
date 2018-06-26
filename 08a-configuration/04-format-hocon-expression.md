# HOCON - Expression

```bash
# L'expression

cle1.cle2.cle3 : 23

# est équivalente à 

cle1 {
  
  cle2 : {
    
    cle3 : 23
  
  }

}
```

```
# Les expressions 

a.x : 42, a.y : 43
a b c : 42
true : 42
3.14 : 42

# sont équivalents à :

a { x : 42, y : 43 }
"a b c" : 42
"true" : 42
"3.14" : 42

```
