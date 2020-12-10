# Objetivos del repositorio

Aprender a usar git y github de manera correcta

Empecemos descargando Git 
|------------ |
[Descargar Git Windows](https://git-scm.com/download/win)|
[Descargar Git Mac](https://git-scm.com/download/mac)|
[Descargar Git Linux/Unix](https://git-scm.com/download/linux)|

## GITHUB COMANDOS BASICOS
```
git --version   //Saber con que version de git estoy trabajando.
git help        //Tener conocimiento sobre los diferentes comandos que puedo ejecutar en git
```


## CONFIGURAR GIT
```
0.- git config --global -e					//Veremos nuestra informacion de git 	
1.- git config --global user.name "Eduardo Bedolla"		//De esta manera le otorgamos un nombre de usuario
2.- git config --global user.email "bedo99.cf@gmail.com"	//De esta manera le otorgamos un correo de usuario
```


## CREAR ALIAS PARA NUESTROS COMANDOS 
```
0.- git config --global alias.NombreDeNuestroAlias "Comando a ejecutar"
```

## INICIAR REPOSITORIO

```
0.- git init			//Inicializamos un Repositorio Local.
1.- git status			//Visualizamos los archivos que sufrieron alguna modificación o no, desde el ultimo commit.
 1.1 git status -s
 1.2 git status -s -b
2.- git add .			//Agregamos todos los archivos al repositorio.
3.- git commit -m "Mensaje"	//Tomar una fotografia o snapshot de como se encuentra nuestro proyecto en ese momento
```


## TECNICA SALVACION

```
0.- git checkout -- .			//Reconstruye todo nuestro proyecto a como estaba desde el ultimo commit o Archivo
 0.1 git checkout -- NombreArchivo
1.- git config core.autocrlf true	//Si ejecutamos un git add y nos arroja un error crlf
2.- git diff				//Nos muestra los cambios que hubo en los archivos si no nos acordamos
 2.2 git diff --staged
```

## HISTORIAL

```
0.- git log	//Visualizamos un historial de todos los commits que se han realizado del mas actual al mas viejo
1.- git log --oneline
2.- git log --oneline --decorate --all --graph
3.- git reflog	//HISTORIAL MAS COMPLETO Y ESTE NO SE MODIFICA PARA NADA
```

## STAGE

```
    <AGREGAR AL STAGE DE FORMA INDEPENDIENTE>

0.- git add Nombredelarchivo		//Por archivo unico
1.- git add *.png			//Por extension de archivo
2.- git add css/			//Por Carpetas

    git add -A				//Agregar al stage los archivos faltantes

    git reset Nombredelarchivo		//Quitar un archivo si por error lo agregamos al stage
    git reset *.png
    git reset css/

    Y POR ULITMO HACEMOS EL COMMIT CON UN MENSAJE PERSONALIZADO


      	    COMMITS


    <ACTUALIZAR MENSAJE COMMIT>

0.- git commit --amend -m "Escribir mensaje Nuevo" //Actualizamos el mensaje de nuestro ultimo commit

    <REVERTIR COMMIT>

0.- git reset --soft "HEAD^" y Despues ejecutamos git commit -am "Escribir mensaje nuevo" //Esto para agregar cambios en el mismo commit
```


## VIAJAR EN EL TIEMPO, RESETS Y REFL0G

```
0.- git reset --mixed "indexCommit"
//Volvemos a un punto/commit del pasado y 
esto hara que quitemos del stage los commits que habiamos realizado con posterioridad a este,
conservando los cambios.


1.- git reset --hard "indexCommit"
//Volvemos a un punto/commit del pasado, 
pero esto borra todo lo que se hizo con posterioridad a este.

2.- git reflog
//Git siempre mantiene un registro de todo lo que sucede en el repositorio, por lo que hace 
un historial de todo y este no se puede afectar para nada. 
Nos serviria para avanzar ahora a un punto tanto del pasado como del futuro y Solo debemos de hacer
lo mismo que en la viñeta (1.-)
```


## BORRAR Y RENOMBRAR ARCHIVOS

```
0.- git mv "Nombre del Archivo" "Nombre Nuevo" //Con esto renombramos el archivo y despues lo 
ejecutamos en un commit para que quede guardado en el registro.

1.- git rm "Nombre del Archivo" //Con esto borramos el archivo y despues lo 
ejecutamos en un commit para que quede guardado en el registro.
```


## RAMAS,UNIONES,TAGS Y CONFLICTOS

```
0.- git branch NombreDeLaRama		//Creacion de una Rama
1.- git checkout NombreDeLaRama		//Movernos a una Rama
2.- git checkout -b NombreDeLaRama	//Para crear y movernos a ella automaticamente

    <UNIONES>

0.- git merge NombreDeLaRamaAUnir	//Debemos posicionarnos en la rama que a la que deseamos unir los cambios y aplicamos el comando

    <ELIMINACION RAMA>

0.- git branch -d NombreDeLaRama	//Eliminar una Rama

    <TAGS>

0.- git tag NombreTag
1.- git tag -d NombreTag
2.- git tag -a NombreTag -m DescripcionTag
3.- git tag -a NombreTagPasado "indexCommit" -m DescripcionTag
```


## STASH Y REBASE

