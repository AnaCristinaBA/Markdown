## Exercici 1. 
Clona el repositori projecteCompartit en el teu ordinador, però guarda'l amb el nom projecteCompartit2. Crea en ell un nou fitxer fitxer2.md amb el contingut “Fitxer creat des d'un altre lloc”, afig-lo al control de versions i envia'l al servidor (això podria fer-se també des d'un altre ordinador).
```
$ git clone ssh://papichulo_programador@192.168.1.144/home/papichulo_programador/projecteCompartit projecteCompartit2
Clonando en 'projecteCompartit2'...
The authenticity of host '192.168.1.144 (192.168.1.144)' can't be established.
ED25519 key fingerprint is SHA256:4i0fGFYvyOHAt+XJTOjqJp6KGMSarwdBA7kF7HNF4o8.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '192.168.1.144' (ED25519) to the list of known hosts.
papichulo_programador@192.168.1.144's password:

$ ls
 devtools   projecteCompartit2   TEMA1   TEMA2   TEMA3   TEMA4
```
```
$ git add fitxer2.md 
$ git commit -a -m "Afegit fitxer2"
[master (commit-raíz) 4541964] Afegit fitxer2
 1 file changed, 1 insertion(+)
 create mode 100644 fitxer2.md

$ git status
En la rama master
Tu rama está basada en 'origin/master', pero upstream ha desaparecido.
  (usa "git branch --unset-upstream" para arreglar)

nada para hacer commit, el árbol de trabajo está limpio

$ git push
papichulo_programador@192.168.1.144's password: 
Enumerando objetos: 3, listo.
Contando objetos: 100% (3/3), listo.
Escribiendo objetos: 100% (3/3), 252 bytes | 252.00 KiB/s, listo.
Total 3 (delta 0), reusados 0 (delta 0), pack-reusados 0
To ssh://192.168.1.144/home/papichulo_programador/projecteCompartit
 * [new branch]      master -> master
```



