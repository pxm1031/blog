CÓMO TRABAJAR CON MULTIPLES CUENTAS EN GITHUB
=============================================

Primero debemos generar una key SSH para la segunda cuenta de GitHub:

    ssh-keygen

**ALERTA:** Se debe ir con cuidado de no borrar la clave existente 
(localizada en ~/.ssh), por lo tanto cuando se nos solicite dónde
guardar el archivo se debe guardar cómo `id_rsa-LOQUESEA`. Por ejemplo
yo lo guarde como `id_rsa-iridio`.




Después (no sé exactamente para qué), se ejecuta:

    eval $(ssh-agent -s)

Se debe añadir la identidad con:

    ssh-add ~/.ssh/id_rsa-LOQUESEA




Ahora se debe crear un archivo `config`, que distinguirá un usuario de
otro

    touch ~/.ssh/config
    vi config

Dentro del archivo copiamos lo siguiente (adaptándolo):

```
#Default GitHub
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa

Host github-COMPANY
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa-LOQUESEA
```



Ahora creamos (o modificamos), nuestro remoto. En mi caso modifico:

    git remote set-url origin git@github-LOQUESEA:USUARIO/REPO.git

**IMPORTANTE:** Además de lo obvio de cambiar LOQUESEA, USUARIO y REPO
por los nombres adecuados hay que hacer coincididr el nombre del host
con el del archivo ~/.ssh/config, es decir que es git@github-LOQUESEA
y no git@github.com-LOQUESEA o git@github.com.
