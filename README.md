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


**- El merge del paso 14, ¿Causó algún conflicto? ¿Por qué?

Para hacer un merge y absorver la rama main, estando situado en la rama styled ejecuto el siguiente comando

```

git merge main

```

Como los commits siguen una lista y se ha realizado con fast forward, el fichero .md que teníamos actualizado
no causa conflicto al haber sido editado posteriormente.
