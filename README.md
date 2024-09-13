# practica-git-kas
Ejercicios de práctica tras finalizar el curso Git, Github y Source Tree

**- ¿Qué comando utilizaste en el paso 11? ¿Por qué?**

Utilicé el siguiente comando

```

git reset --HARD HEAD~1

```

El objetivo era volver al comite anterior (reset con HEAD~1) modificando el working copy (--hard).


**- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?**

Como mi working copy se ha modificado he tenido que aplicar los siguientes dos comandos:

```

git reflog

git reset --hard a6b1364

```

Primero un reflog para saber el hash del commit que había perdido. Después el mismo comando que para eliminar el commit
anterior pero indicando el commit  (hash) al que quiero volver.


**- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?**

Para hacer un merge y absorver la rama main, estando situado en la rama styled ejecuto el siguiente comando

```

git merge main

```

Como los commits siguen una lista y se ha realizado con fast forward, el fichero .md que teníamos actualizado
no causa conflicto al haber sido editado posteriormente.


**- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?**

Para hacer el merge de htmlify, hay que hacer un checkout a la rama styled y ejecutar el merge.
Como en el orden cronológico la rama htmlify con el fichero .md se creo posterior, aparecen conflictos con la rama.
Para subsanar conflictos,

```

nano git-nuestro.md

``` 

Y nos quedamos con la parte del .md que no tiene codigo html (nos quedamos con el fichero de styled)

Después volvemos a añadir el fichero al staging area y a ejecutar el merge.


**- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?**

Para hacer el merge, hemos ejecutado un checkout a la rama main y después un merge.
Como es fast forward y la rama main estaba alineada temporalmente (no había commits de esa rama) el puntero ha cambiado 
de main a styled absorviendolo. Los ficheros de forma automática han cambiado a como estaban en styled al encontrarse 
más avanzados evitando conflictos.


**- ¿Qué comando o comandos utilizaste en el paso 25?**

```

git log --graph --decorate --oneline

```

**- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?**

Sí, podría ser fast forward perfectamente ya que main absorbe title que solo tiene un commit posterior en la línea cronológica.
Se adelante el puntero de main a title absorbiendo los ficheros de title.

Para hacer el merge utilicé el siguiente comando

```

git merge --no-ff title

```

**- ¿Qué comando o comandos utilizaste en el paso 27?**

Para deshacer el merge utilice los siguientes comandos

```

git log
git reset --merge f4ad14c

```
Primero detecto el commit en el que estoy (tras el merge) y busco el hash del commit anterior al merge.
Ejecuto un reset --merge para no perder los cambios del working copy.


**- Qué comando o comandos utilizaste en el paso 28?**

Para descartar los cambios (deshacer merge) y volver al merge original, de main absorve title con fast forward, ejecuto
los siguientes comandos

```

git reflog

git reset --hard HEAD@{3}

````

He usado un HEAD@{3} porque es el que necesitaba al haber hecho algun commit y checkout intermedio


**- ¿Qué comando o comandos utilizaste en el paso 29?**


Para eliminar la rama title primero tengo que estar en la rama main y ejecutar el siguiente comando

```

git branch -d title

```

** ¿Qué comando o comandos utilizaste en el paso 30?**

Para rehacer el merge es la misma dinámica contestada en la pregunta 28 del README.md
