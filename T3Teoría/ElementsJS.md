## Variables
es declaran amb "let"
```
let variable = valor;
```
Es pod usar el mode estrict: 'use strict';

- Poden començar per quasevol caracter pero no por un número
- Indicar nom amb CamelCase

## Funcionament JS
| Conversió de tipus |Tipus lògic| Typeof |
|--------------------|-----------|--------|
| 13 + 7 => 20 |let itemSeleccionat = false;|typeof(10) // 'number'
"13" + "7" => "137"|let mostrar = true;|typeof("hola") // 'string'|
"13" + 7 => "137"||typeof("hola") // 'string'
+"13" + 7 => 20||typeof(true) // 'boolean'
|||typeof(a) // 'undefined'
|||typeof(null) // 'object'
|||typeof({"nom": "Jose"}) // 'object'

## Acceder i inizialitzar
|Accedir a elements|inicializar arrays|JSON|declalció constants
|---------------|-----------|-----|-----|
Consulta: var avui = dies_setmana[1];|ex_vector2 = [];|let dies_setmana = ["dilluns", "dimarts", "dimecres",...]|const PI = 3.1416;
Assignació: ex_vector[1] = "cadena3";|ex_vector3 = new Array();|let ex_vector = ["cadena1", num1, "cadena2", ["cadena1_vector1"]];





