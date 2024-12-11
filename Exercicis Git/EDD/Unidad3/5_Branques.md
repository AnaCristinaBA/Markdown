Una branca és una bifurcació del codi principal que ens permet seguir un camí de desenvolupament diferent, i bé descartar els canvis realitzats o fusionar-los amb la branca principal.

## Crear una branca
### 1. Inicialitzem el repositori
```
$ cd Projecte2
$ git init
Inicializado repositorio Git vacío en /home/papichulo_programador/Documentos/1erDAM/EDD/TEMA3/Projecte2/.git/
```
### 2. Creem contingut
```
$ git add fit1.txt 
$ git commit -a -m "Afeguim fit1"
[master (commit-raíz) 481cdc2] Afeguim fit1
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 fit1.txt

$ echo "Línea de prova 1" > fit1.txt 

 git commit -a -m "Modificat fit1"
[master d1d00c2] Modificat fit1
 1 file changed, 1 insertion(+)

$ git log --oneline 
d1d00c2 (HEAD -> master) Modificat fit1
481cdc2 Afeguim fit1
```
### 3. Creació de la branca de proves
```
$ git branch proves
$ git branch
* master
  proves
```
### 4. Treballar amb ella
```
$ git checkout proves
Cambiado a rama 'proves'
$ git branch
  master
* proves

$ touch pro1.md
$ git add pro1.md 
$ git commit -m "Afegit pro1"
[proves 14d93e4] Afegit pro1
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 pro1.md

$ git log --oneline 
14d93e4 (HEAD -> proves) Afegit pro1
d1d00c2 (master) Modificat fit1
481cdc2 Afeguim fit1
```
### 5. Saltant entre branques
```
$ git checkout master
```
### 6. Accions amb les branques
1. Combinar branques
```
$ git merge proves
Actualizando d1d00c2..14d93e4
Fast-forward
 pro1.md | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 pro1.md
```
2. Descartant els canvis d'una branca
Creem varios fitxers
```
$ git log --oneline 
8450456 (HEAD -> proves) Afegit fitxer per a descartar3
2df450e Afegit fitxer per a descartar2
3ede619 Afegit fitxer per a descartar
14d93e4 (master) Afegit pro1
d1d00c2 Modificat fit1
481cdc2 Afeguim fit1

$ git reset --hard 14d93e4

HEAD is now at 14d93e4 Afegit pro1
```
3. Eliminar una branca
- Eliminar una branca fusionada
```
$ git branch -d proves
- Eliminada la rama proves (era 14d93e4).
```
Eliminar una branca sense fusionar
```
$ git branch -D proves
```