pam_rps
==========

## Instruction d'installation sous Centos 6.X

###Pré-requis

Avoir suivi les instructions à la page https://github.com/humboldtux/check_user

### Récupérez les sources

Clonez le dépôt

``` sh
git clone https://github.com/humboldtux/pam_rps
```

### Compilation

``` sh
cd pam_rps/src/
gcc -fPIC -c pam_rps.c
gcc -shared -o pam_rps.so pam_rps.o -lpam
```

Un module check_user a été créé dans le dossier courant. Vous pouvez copier dans le dossiers des modules de votre système:
``` sh
mv pam_rps.so /lib64/security/
```

Ainsi que la page de manuel:
``` sh
cp pam_rps.8.in  /usr/share/man/man8
```