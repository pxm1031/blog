CHULETA DE GIT
==============


Para crear un repositorio
-------------------------

1. En la carpeta crear el directorio git escribiendo:
2. Creamos el primer archivo:
3. Podemos ver el status de git con:
4. Si lo creemos conveniente podemos añadirlo para el próximo commit:
5. O bien podemos añadir los archivos nuevos o modificados, borrar los 
eliminados y cambiar los renombrados
6. Hacemos commit:
7. Una vez creado el repositorio remoto en github, por ejemplo añadirlo
como remoto a nuestro git local:
8. La primera vez que hagamos push a un remoto hay que añadir la opción
-u luego no hará falta:

~~~
git init
vim README.md
git status
git add .
git add -u
git commit -m "primeros archivos"
git remote add origin https://github.com/pxm1031/...
git push -u origin main
~~~ 
