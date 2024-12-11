# SCV distribuit
Cada equip té una còpia completa de tot el repositori, en lloc de l'última instantània del projecte.

Poden treballar de forma local sense necessitat de connectar-se a altres equips.

Poden crear instantànies de forma local i connectar-se al servidor únicament quan necessiten compartir el seu treball o obtenir el treball realitzat per altres companys.

## El sistema de control de versions git

### 1. Instalacio i comprobar versió
```
$ sudo apt install git 
$ git --version
git version 2.34.1
```

### 2. Consultar ajuda
```
$ git help -a
$ git <comando> --help
```

### 3. Configuració
Identitat de l’usuari, que es compon del nom i el correu electrònic:

```￼
$ git config --global user.name "Ana DAM"
$ git config --global user.email anacbagudo@gmail.com
```

Editor predeterminat per quan git necessiti que escrivim algun missatge (per exemple el missatge de cada commit). 

```
$ git config --global core.editor vim
```

Perquè utilitze l'eixida en colors significatius:

```
$ git config --global color.ui true
```
Per a vore tota la llista de valors:

```
$ git config --list
user.name=Ana DAM
user.email=anacbagudo@gmail.com
core.editor=nano
core.autocrlf=false
color.ui=true
```
## Començem a treballar
### 1. Creem un directori
I initialitzem el repositori, veiem que ens indica que no ni ha res pendent.
```
$ mkdir projproba
$ cd projproba/
$ git init
Inicializado repositorio Git vacío en /home/papichulo_programador/Documentos/1er DAM/projproba/.git/
$ git status
En la rama master

No hay commits todavía
```
### 2. Creació de contingut
```
$ touch prova1.txt
$ git status
En la rama master

No hay commits todavía

Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que será confirmado)
	prova1.txt

no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento
```
Ens mostra que el arxiu está "sense seguiment" el que significa que aquest fitxer no es troba sota el sistema de control de versions.

### 3. Fent el seguiment de l’arxiu
```
$git add prova1.txt 
$ git status
En la rama master

No hay commits todavía

Cambios a ser confirmados:
  (usa "git rm --cached <archivo>..." para sacar del área de stage)
	nuevos archivos: prova1.txt
```
Ara és un fitxer nou en el repositori i que té canvis per confirmar, está preparat.

### 4. Fent el commit
```
$ git commit -m "Afegint el prime commit"
[master (commit-raíz) aa6abb2] Afegint el prime commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 prova1.txt
```
Amb el paràmetre -m especifiquem el missatge associat a aquest commit.
Ara tornem a tindre el directori de treball net.

Per a vore un registre de tots els commits podem fer:
```
$ git log
$ git log --oneline
```

## Ejercici 1:
Prova a modificar el fitxer i observa els canvis en l'estat. En quin estat es trobarà ara l'arxiu? Què haurem de fer perquè els canvis es reflectisquen en el repositori? Investiga sobre el paràmetre -a de l'ordre git commit i intenta relacionar-lo amb aquest exercici.

Modifiquem el fitxer i al fer $ git status ens mostra:
```
En la rama master
Cambios no rastreados para el commit:
  (usa "git add <archivo>..." para actualizar lo que será confirmado)
  (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
	modificados:     prova1.txt

sin cambios agregados al commit (usa "git add" y/o "git commit -a")
```

Per a volcar les modificacions directament al repositori fem:
```
$ git commit -a -m "Fitxer modificat"
[master f15703d] Fitxer modificat
 1 file changed, 2 insertions(+)
```

## Exercici 2. 
Crea dos fitxers, anomenats tmp1.md i tmp2.md i afegeix-los dins del repositori, comprovant l’estat en cada pas, i verificant que estan en el repositori.

```
$ touch tmp1.md 
$ touch tmp2.md
$ git status
En la rama master
Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que será confirmado)
	tmp1.md
	tmp2.md

no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento)

$ git add .
$ git status
En la rama master
Cambios a ser confirmados:
  (usa "git restore --staged <archivo>..." para sacar del área de stage)
	nuevos archivos: tmp1.md
	nuevos archivos: tmp2.md

$ git commit -a -m "Dos fitxeres de prova"
[master acb1f30] Dos fitxeres de prova
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 tmp1.md
 create mode 100644 tmp2.md
```

## Esborrar arxius
### 1. Esborrar localment
```
$ rm tmp1.md 
$ git status
En la rama master
Cambios no rastreados para el commit:
  (usa "git add/rm <archivo>..." para actualizar a lo que se le va a hacer commit)
  (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
	borrados:        tmp1.md

sin cambios agregados al commit (usa "git add" y/o "git commit -a")

$ git add .
papichulo_programador@papichulo:~/Documentos/1er DAM/projproba$ git status
En la rama master
Cambios a ser confirmados:
  (usa "git restore --staged <archivo>..." para sacar del área de stage)
	borrados:        tmp1.md

$ git commit -m "Eliminasió de tmp1"
[master 0549678] Eliminasió de tmp1
 1 file changed, 0 insertions(+), 0 deletions(-)
 delete mode 100644 tmp1.md
 ```

### 1. Esborrar del repositori
```
$ git rm tmp2.md 
rm 'tmp2.md'

$ git status
En la rama master
Cambios a ser confirmados:
  (usa "git restore --staged <archivo>..." para sacar del área de stage)
	borrados:        tmp2.md

$ git commit -m "Emisinasion tmp2"
[master 476804d] Emisinasion tmp2
 1 file changed, 0 insertions(+), 0 deletions(-)
 delete mode 100644 tmp2.md
```
### 2. Esborrar sense seguiment
 ```
$ git clean -f
 ```
Esborra els fixers que no estiguen sota CV
 ```
$ git clean -f -d
 ```
Esborra els directoris buits

## Ejercicio 3
Crea un fitxer .gitignore de manera que s’ignoren tots els fitxers compilats de java. Afegeix-lo al repositori. 
Posteriorment, crea un fitxer font senzill en Java, compila’l, i prepara tot per confirmar-ho en un commit. Comprova 
si els fitxers compilats s’han afegit o no.`
```
$ git add .gitignore
$ git commit -m "Afegit .gitignore"
[master (commit-raíz) 725cc8b] Afegit .gitignore
 1 file changed, 3 insertions(+)
 create mode 100644 .gitignore

$ touch Hola.java
$ nano Hola.java
class Hello {
 public static void main(String[] args) {
 System.out.println("Hola Món!"); 
 }
}

$ git add *
Las siguientes rutas son ignoradas por uno de tus archivos .gitignore:
Hello.class
ayuda: Usa -f si realmente quieres agregarlos.
ayuda: Desactiva este mensaje ejecutando
ayuda: "git config advice.addIgnoredFile false"
papichulo_programador@papichulo:~/Documentos/1e

 ```
 