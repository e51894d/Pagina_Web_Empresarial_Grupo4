# SIMULACIÓN Y SOLUCIÓN DE UN CONFLICTO EN GIT
    - Alejandro Borrego 
    - Abel Perálvarez 


Hemos realizado un conflcito: creando una rama y editando desde la rama y el main una misma de línea, forzando un conflicto al intentar hacer merge de ambos.

1. Ambos hemos partido desde el main. Hemos creado una rama, y modificado una linea concreta  <h1> Decora tu hogar con nosotros </h1>  por   <h1>Ejemplos conflicto git</h1>
2. Por otro lado, desde el main hemos cambiado esa misma linea. Cada uno ha hecho un commit y pull desde el main y su rama. 
3. Por últimos hemos intentado fusionar ambos (merge) generando un conflicto. 

```html
<<<<<<< HEAD
<h1>Ejemplo de conflicto</h1>
=======
<h1>Pepino</h1>
>>>>>>> rama-conflicto

#Conflicto
    CONFLICT (content): Merge conflict in gitentornos/inicio.html
    Automatic merge failed; fix conflicts and then commit the result.

# Como lo hemos resuelto:
    1.Eliminamos una de las dos versiones
    2.git add gitentornos/inicio.html
    3. y un commit final
        git commit -m "Conflicto resuelto entre main y rama-conflicto"
        git push origin main




# Recapitulación de comandos utilizados
    //creamos la rama 
    git checkout -b rama-conflicto  

    //Modificamos archivo y commit
    git add gitentornos/inicio.html
    git commit -m "Cambio en título desde rama-conflicto"
    git push origin rama-conflicto


    //Por otro lado, desde el main edita el archivo 
    git checkout main
    git pull origin main
    git add gitentornos/inicio.html
    git commit -m "Cambio desde main"
    git push origin main


    //Por ultimo intento hacer un merge 
    git checkout main
    git pull origin main
    git merge rama-conflicto

#Conflicto:
    PS C:\Users\Alejandro\Desktop\Temporal\Pagina_Web_Empresarial_Grupo4-1> git merge rama-conflicto
    error: Merging is not possible because you have unmerged files.
    hint: Fix them up in the work tree, and then use 'git add/rm <file>'
    hint: as appropriate to mark resolution and make a commit.
    fatal: Exiting because of an unresolved conflict.










    # TERMINAL del conflicto

PS C:\Users\Alejandro\Desktop\Temporal\Pagina_Web_Empresarial_Grupo4-1> git checkout rama-conflicto
branch 'rama-conflicto' set up to track 'origin/rama-conflicto'.
Switched to a new branch 'rama-conflicto'
PS C:\Users\Alejandro\Desktop\Temporal\Pagina_Web_Empresarial_Grupo4-1> git add gitentornos/inicio.html
>> git push origin rama-conflicto
>>
[rama-conflicto 4af642b] Cambio en título desde rama-conflicto
 1 file changed, 105 insertions(+)
 create mode 100644 gitentornos/inicio.html
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 6 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 1.65 KiB | 1.65 MiB/s, done.
Total 4 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/e51894d/Pagina_Web_Empresarial_Grupo4.git
   2a1738c..4af642b  rama-conflicto -> rama-conflicto
PS C:\Users\Alejandro\Desktop\Temporal\Pagina_Web_Empresarial_Grupo4-1> git checkout main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
PS C:\Users\Alejandro\Desktop\Temporal\Pagina_Web_Empresarial_Grupo4-1> git pull origin main
remote: Enumerating objects: 7, done.
remote: Counting objects: 100% (7/7), done.
remote: Compressing objects: 100% (1/1), done.
remote: Total 4 (delta 2), reused 4 (delta 2), pack-reused 0 (from 0)
Unpacking objects: 100% (4/4), 333 bytes | 9.00 KiB/s, done.
From https://github.com/e51894d/Pagina_Web_Empresarial_Grupo4
 * branch            main       -> FETCH_HEAD
   eff2ebb..c461501  main       -> origin/main
Auto-merging gitentornos/inicio.html
CONFLICT (content): Merge conflict in gitentornos/inicio.html
Automatic merge failed; fix conflicts and then commit the result.
PS C:\Users\Alejandro\Desktop\Temporal\Pagina_Web_Empresarial_Grupo4-1> git merge rama-conflicto
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.
PS C:\Users\Alejandro\Desktop\Temporal\Pagina_Web_Empresarial_Grupo4-1> git add gitentornos/inicio.html
PS C:\Users\Alejandro\Desktop\Temporal\Pagina_Web_Empresarial_Grupo4-1> 
PS C:\Users\Alejandro\Desktop\Temporal\Pagina_Web_Empresarial_Grupo4-1> 
PS C:\Users\Alejandro\Desktop\Temporal\Pagina_Web_Empresarial_Grupo4-1> git commit -m "Conflicto resuelto entre main y rama-conflicto"
[main be122c4] Conflicto resuelto entre main y rama-conflicto
PS C:\Users\Alejandro\Desktop\Temporal\Pagina_Web_Empresarial_Grupo4-1> git push origin main
Enumerating objects: 14, done.       
Counting objects: 100% (14/14), done.
Delta compression using up to 6 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (8/8), 726 bytes | 726.00 KiB/s, done.
Total 8 (delta 4), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (4/4), completed with 2 local objects.
To https://github.com/e51894d/Pagina_Web_Empresarial_Grupo4.git
   c461501..be122c4  main -> main