
Quan el codi creix es te que compilar els fitxers un a un.
Es creen determiants scrips que compilan per a facilitar y automatizar tasques.

## Ús de ant:
Tenim que crear un fitxer build.xml que esprcifiquem com es compilará el projecte.
Per exemple:
```
<project name="saludaAnt">
    <target name="clean">
        <delete dir="build" />
    </target>

    <target name="compile" depends="clean">
        <mkdir dir="build" />
        <javac includeantruntime="false" 
        srcdir="src/com/ieseljust/edd" destdir="build" />
    </target>

    <target name="run" depends="compile">
        <property name="arg0" value=""/>
        <java classpath="build" classname="com.ieseljust.edd.Hola">
            <arg value="${arg0}"/>
        </java>
    </target>
</projec
```
```
$ tree
.
├── build
│   └── com
│       └── ieseljust
│           └── edd
│               ├── Calcula.class
│               └── Calculadora.class
├── build.xml
└── src
    └── com
        └── ieseljust
            └── edd
                ├── Calculadora.java
                └── Calcula.java
```
## Ús de maven:
Define 3 posibles cicles de vida diferents. Ni han fases definides.


