Hacer un hola mundo con java Script y Node.js

Hacemos un fichero de java script:
```
if (process.argv.length == 3)
    console.log("Hola " + process.argv[2]);
   else
    console.log("Hola Node.js");
```
En la terminal:
```
$ node hola.js
Hola Node.js

$ node hola.js Joamuran
Hola Joamuran
```
