# SHELL, PERMISSIONS

## Résumé:

Les permissions dans un système de fichiers dictent les actions qu'un utilisateur peut effectuer sur un fichier ou un répertoire. Ces actions incluent la lecture, l'écriture et l'exécution. Les utilisateurs sont catégorisés en trois groupes : le propriétaire du fichier, le groupe associé, et les autres utilisateurs.

La commande chmod (change mode) est couramment utilisée pour modifier les permissions d'un fichier. Elle permet de spécifier les autorisations pour chaque catégorie d'utilisateurs en utilisant des chiffres ou des symboles.

La combinaison du Shell et de la gestion des permissions offre un niveau élevé de contrôle et de sécurité. Les administrateurs système peuvent restreindre l'accès aux fichiers sensibles, tandis que les développeurs peuvent assurer la confidentialité et l'intégrité de leurs codes sources.

En résumé, le Shell et les permissions sont des éléments fondamentaux dans l'administration système et le développement, garantissant une utilisation efficace des fichiers et renforçant la sécurité des systèmes d'exploitation.


### Permissions de Lecture, Écriture et Exécution :

* Permission de Lecture (r) :

  * Autorise un utilisateur à lire le contenu d'un fichier ou à lister les fichiers dans un répertoire.
  * Permet l'accès aux données sans possibilité de les modifier.

* Permission d'Écriture (w) :

  * Autorise un utilisateur à modifier le contenu d'un fichier ou à créer de nouveaux fichiers dans un répertoire.
  * Offre la capacité de manipuler et de mettre à jour les données.

* Permission d'Exécution (x) :

  * Autorise un utilisateur à exécuter un fichier comme un programme.
  * Nécessaire pour lancer des scripts ou des programmes exécutables.

 ### Commandes de Gestion des Permissions :

* chmod :

  * Modifie les permissions d'un fichier ou d'un répertoire.
  * Utilisé pour définir qui peut lire, écrire, ou exécuter un fichier.
  * Exemple : chmod +x mon_script.sh permet à l'utilisateur d'exécuter le script.

* chown :

  * Modifie le propriétaire d'un fichier ou d'un répertoire.
  * Utile pour changer l'utilisateur associé à un fichier.
  * Exemple : chown nouvel_utilisateur fichier.txt attribue le fichier à un nouvel utilisateur.

* chgrp :

  * Modifie le groupe associé à un fichier ou à un répertoire.
  * Permet de changer le groupe auquel appartient un fichier.
  * Exemple : chgrp nouveau_groupe dossier assigne le dossier à un nouveau groupe.

## Resources:
* [Permissions](https://linuxcommand.org/lc3_lts0090.php)

## Requirements:
* Allowed editors: vi, vim, emacs
* All your scripts will be tested on Ubuntu 20.04 LTS
* All your scripts should be exactly two lines long ($ wc -l file should print 2)
* All your files should end with a new line (why?)
* The first line of all your files should be exactly #!/bin/bash
* A README.md file, at the root of the folder of the project, describing what each script is doing
* You are not allowed to use backticks, &&, || or ;
* All your files must be executable

## TASKS: 

### 0. My name is Betty
Create a script that switches the current user to the user betty.

You should use exactly 8 characters for your command (+1 character for the new line)
You can assume that the user betty will exist when we will run your script

```bash
amandine@ubuntu:/tmp/h$ tail -1 0-iam_betty | wc -c
9
amandine@ubuntu:/tmp/h$
```


### 1. Who am I
Write a script that prints the effective username of the current user.

```bash
amandine@ubuntu:/tmp/h$ ./1-who_am_i
amandine
amandine@ubuntu:/tmp/h$ 
```


### 2. Groups
Write a script that prints all the groups the current user is part of.

```bash
amandine@ubuntu:/tmp/h$ ./2-groups
amandine adm cdrom sudo dip plugdev lpadmin sambashare
amandine@ubuntu:/tmp/h$ 
```


### 3. New owner
Write a script that changes the owner of the file hello to the user betty.

```bash
amandine@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 amandine amandine 3-new_owner
-rw-rw-r-- 1 amandine amandine hello
amandine@ubuntu:/tmp/h$ sudo ./3-new_owner 
amandine@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 amandine amandine 3-new_owner
-rw-rw-r-- 1 betty  amandine  hello
amandine@ubuntu:/tmp/h$
```


### 4. Empty!
Write a script that creates an empty file called hello.

### 5. Execute
Write a script that adds execute permission to the owner of the file hello.

The file hello will be in the working directory

```bash
amandine@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 amandine amandine 5-execute
-rw-rw-r-- 1 amandine amandine hello
amandine@ubuntu:/tmp/h$ ./hello
bash: ./hello: Permission denied
amandine@ubuntu:/tmp/h$ ./5-execute 
amandine@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 amandine amandine 5-execute
-rwxrw-r-- 1 amandine amandine hello
amandine@ubuntu:/tmp/h$ 
```

### 6. Multiple permissions
Write a script that adds execute permission to the owner and the group owner, and read permission to other users, to the file hello.

The file hello will be in the working directory

```bash
amandine@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 amandine amandine 6-multiple_permissions
-rw-r----- 1 amandine amandine hello
amandine@ubuntu:/tmp/h$ ./6-multiple_permissions 
amandine@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 amandine amandine 6-multiple_permissions
-rwxr-xr-- 1 amandine amandine hello
amandine@ubuntu:/tmp/h$ 
```

### 7. Everybody!
Write a script that adds execution permission to the owner, the group owner and the other users, to the file hello

The file hello will be in the working directory
You are not allowed to use commas for this script

```bash
amandine@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 amandine amandine 7-everybody
-rw-r----- 1 amandine amandine hello
amandine@ubuntu:/tmp/h$ ./7-everybody 
amandine@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 amandine amandine 7-everybody
-rwxr-x--x 1 amandine amandine hello
amandine@ubuntu:/tmp/h$ 
```

### 8. James Bond
Write a script that sets the permission to the file hello as follows:

Owner: no permission at all
Group: no permission at all
Other users: all the permissions
The file hello will be in the working directory You are not allowed to use commas for this script

```bash
amandine@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 amandine amandine 8-James_Bond
-rwxr-x--x 1 amandine amandine hello
amandine@ubuntu:/tmp/h$ ./8-James_Bond 
amandine@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 amandine amandine 8-James_Bond
-------rwx 1 amandine amandine hello
amandine@ubuntu:/tmp/h$ 
```

### 9. John Doe
Write a script that sets the mode of the file hello to this:

The file hello will be in the working directory
You are not allowed to use commas for this script

```bash
-rwxr-x-wx 1 amandine amandine hello
```

### 10. Look in the mirror
Write a script that sets the mode of the file hello the same as olleh’s mode.

The file hello will be in the working directory
The file olleh will be in the working directory

```bash
amandine@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 amandine amandine 10-mirror_permissions
-rwxr-x-wx 1 amandine amandine hello
-rw-rw-r-- 1 amandine amandine  olleh
amandine@ubuntu:/tmp/h$ ./10-mirror_permissions 
amandine@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 amandine amandine 10-mirror_permissions
-rw-rw-r-- 1 amandine amandine hello
-rw-rw-r-- 1 amandine amandine olleh
amandine@ubuntu:/tmp/h$ 
```

### 11. Directories
Create a script that adds execute permission to all subdirectories of the current directory for the owner, the group owner and all other users. Regular files should not be changed.

```bash
amandine@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 amandine amandine   11-directories_permissions
drwx------ 2 amandine amandine   dir0
drwx------ 2 amandine amandine   dir1
drwx------ 2 amandine amandine   dir2
-rw-rw-r-- 1 amandine amandine   hello
amandine@ubuntu:/tmp/h$ ./11-directories_permissions 
amandine@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 amandine amandine  11-directories_permissions
drwx--x--x 2 amandine amandine  dir0
drwx--x--x 2 amandine amandine  dir1
drwx--x--x 2 amandine amandine  dir2
-rw-rw-r-- 1 amandine amandine  hello
amandine@ubuntu:/tmp/h$
```

### 12. More directories
Create a script that creates a directory called my_dir with permissions 751 in the working directory.

```bash
amandine@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 amandine amandine  12-directory_permissions
drwx--x--x 2 amandine amandine  dir0
drwx--x--x 2 amandine amandine  dir1
drwx--x--x 2 amandine amandine  dir2
-rw-rw-r-- 1 amandine amandine  hello
amandine@ubuntu:/tmp/h$ ./12-directory_permission s
amandine@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 amandine amandine  12-directory_permissions
drwx--x--x 2 amandine amandine  dir0
drwx--x--x 2 amandine amandine  dir1
drwx--x--x 2 amandine amandine  dir2
drwxr-x--x 2 amandine amandine  my_dir
-rw-rw-r-- 1 amandine amandine  hello
amandine@ubuntu:/tmp/h$ 
```

### 13. Change group
Write a script that changes the group owner to school for the file hello

The file hello will be in the working directory

```bash
amandine@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 amandine amandine   13-change_group
drwx--x--x 2 amandine amandine   dir0
drwx--x--x 2 amandine amandine   dir1
drwx--x--x 2 amandine amandine   dir2
drwxr-x--x 2 amandine amandine   my_dir
-rw-rw-r-- 1 amandine amandine   hello
amandine@ubuntu:/tmp/h$ sudo ./13-change_group 
amandine@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 amandine amandine   13-change_group
drwx--x--x 2 amandine amandine   dir0
drwx--x--x 2 amandine amandine   dir1
drwx--x--x 2 amandine amandine   dir2
drwxr-x--x 2 amandine amandine   my_dir
-rw-rw-r-- 1 amandine amandine   hello
amandine@ubuntu:/tmp/h$ 
```

### 14. Owner and group
Write a script that changes the owner to amandine and the group owner to amandine for all the files and directories in the working directory.

```bash
amandine@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 amandine amandine   14-change_owner_and_group
drwx--x--x 2 amandine amandine   dir0
drwx--x--x 2 amandine amandine   dir1
drwx--x--x 2 amandine amandine   dir2
drwxr-x--x 2 amandine amandine   my_dir
-rw-rw-r-- 1 amandine amandine   hello
amandine@ubuntu:/tmp/h$ sudo ./14-change_owner_and_group 
amandine@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 amandine amandine   14-change_owner_and_group
drwx--x--x 2 amandine amandine   dir0
drwx--x--x 2 amandine amandine   dir1
drwx--x--x 2 amandine amandine   dir2
drwxr-x--x 2 amandine amandine   my_dir
-rw-rw-r-- 1 amandine amandine   hello
amandine@ubuntu:/tmp/h$ 
```

### 15. Symbolic links
Write a script that changes the owner and the group owner of _hello to amandine and amandine respectively.

The file _hello is in the working directory
The file _hello is a symbolic link

```bash
amandine@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 amandine amandine    15-symbolic_link_permissions
-rw-rw-r-- 1 amandine amandine    hello
lrwxrwxrwx 1 amandine amandine    _hello -> hello
amandine@ubuntu:/tmp/h$ sudo ./15-symbolic_link_permissions 
amandine@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 amandine amandine       15-symbolic_link_permissions
-rw-rw-r-- 1 amandine amandine       hello
lrwxrwxrwx 1 amandine  amandine      _hello -> hello
amandine@ubuntu:/tmp/h$ 
```

### 16. If only
Write a script that changes the owner of the file hello to amandine only if it is owned by the user guillaume.

The file hello will be in the working directory

```bash
amandine@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 amandine    amandine      16-if_only 
-rw-rw-r-- 1 guillaume amandine      hello
amandine@ubuntu:/tmp/h$ sudo ./16-if_only 
amandine@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 amandine amandine      16-if_only 
-rw-rw-r-- 1 amandine  amandine      hello
amandine@ubuntu:/tmp/h$ 
```
