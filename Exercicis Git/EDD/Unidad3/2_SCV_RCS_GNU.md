# SCV Local
## 1. Instalació
```
$ sudo apt install rcs rcs-blame
```

## 2. Preparació del directori de treball
```
$ ls -l
total 8
-rw-rw-r-- 1 papichulo_programador papichulo_programador  99 dic  5 20:24 projecte1
-rw-rw-r-- 1 papichulo_programador papichulo_programador 140 dic  5 20:28 projecte2
```

la cadena: rw-rw-r-- se divide en:

En cadenes de 3 caracteres:

    - Permisos del usuari
    - Permisos del grup
    - permisos de altres usuaris

## 3. Registrant contingut en el SCV
 L'hem de registrar (check-in) en el sistema de control de versions.
 
```
$ ci -u projecte1
projecte1,v  <--  projecte1
enter description, terminated with single '.' or end of file:
NOTE: This is NOT the log message!
>> Versió inicial  
>> Del projecte1
>> .
initial revision: 1.1
done
```
Podem vore que se ha creat un nou fitxer amb una "v" y ara els fitxers soles tenen permisos de lectura.
```
$ ls -l
total 12
-r--r--r-- 1 papichulo_programador papichulo_programador  99 dic  5 20:24 projecte1
-r--r--r-- 1 papichulo_programador papichulo_programador 323 dic  5 22:58 projecte1,v
-rw-rw-r-- 1 papichulo_programador papichulo_programador 140 dic  5 20:28 projecte2
```

## 4. Checkout
Per a rindre permisos de escriptura y realizar canvis fem: 
```
$ co -l projecte1
projecte1,v  -->  projecte1
revision 1.1 (locked)
done
```
Amb l'opció -l (de lock), en el co indiquem que es bloquege el fitxer, de manera que un altre usuari del sistema no el puga modificar mentre es fan els canvis.

Afeguim una nova línea al projecte1 i tornem a fer un check-in.
```
ci -u projecte1
projecte1,v  <--  projecte1
new revision: 1.2; previous revision: 1.1
enter log message, terminated with single '.' or end of file:
>> 
```
## 5. Revisa els ccanvis
Per a mostrar algunes dades del fitxer i les diferents versions 
```
rlog projecte1
```

Si volem saber quines diferències hi ha entre dues versions:
```
$ rcsdiff -r1.1 -r1.2 projecte1
```
