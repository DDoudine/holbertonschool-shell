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
mathieu@ubuntu:/tmp/h$ tail -1 0-iam_betty | wc -c
9
mathieu@ubuntu:/tmp/h$
```


### 1. Who am I
Write a script that prints the effective username of the current user.

```bash
mathieu@ubuntu:/tmp/h$ ./1-who_am_i
mathieu
mathieu@ubuntu:/tmp/h$ 
```


### 2. Groups
Write a script that prints all the groups the current user is part of.

```bash
mathieu@ubuntu:/tmp/h$ ./2-groups
mathieu adm cdrom sudo dip plugdev lpadmin sambashare
mathieu@ubuntu:/tmp/h$ 
```


### 3. New owner
Write a script that changes the owner of the file hello to the user betty.

```bash
mathieu@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 mathieu mathieu 30 Sep 20 14:23 3-new_owner
-rw-rw-r-- 1 mathieu mathieu  0 Sep 20 14:18 hello
mathieu@ubuntu:/tmp/h$ sudo ./3-new_owner 
mathieu@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 mathieu mathieu 30 Sep 20 14:23 3-new_owner
-rw-rw-r-- 1 betty  mathieu  0 Sep 20 14:18 hello
mathieu@ubuntu:/tmp/h$
```


### 4. Empty!
Write a script that creates an empty file called hello.

### 5. Execute
Write a script that adds execute permission to the owner of the file hello.

The file hello will be in the working directory

```bash
mathieu@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 mathieu mathieu 28 Sep 20 14:26 5-execute
-rw-rw-r-- 1 mathieu mathieu 23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ ./hello
bash: ./hello: Permission denied
mathieu@ubuntu:/tmp/h$ ./5-execute 
mathieu@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 mathieu mathieu 28 Sep 20 14:26 5-execute
-rwxrw-r-- 1 mathieu mathieu 23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ 
```

### 6. Multiple permissions
Write a script that adds execute permission to the owner and the group owner, and read permission to other users, to the file hello.

The file hello will be in the working directory

```bash
mathieu@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 mathieu mathieu 36 Sep 20 14:31 6-multiple_permissions
-rw-r----- 1 mathieu mathieu 23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ ./6-multiple_permissions 
mathieu@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 mathieu mathieu 36 Sep 20 14:31 6-multiple_permissions
-rwxr-xr-- 1 mathieu mathieu 23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ 
```

### 7. Everybody!
Write a script that adds execution permission to the owner, the group owner and the other users, to the file hello

The file hello will be in the working directory
You are not allowed to use commas for this script

```bash
mathieu@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 mathieu mathieu 28 Sep 20 14:35 7-everybody
-rw-r----- 1 mathieu mathieu 23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ ./7-everybody 
mathieu@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 mathieu mathieu 28 Sep 20 14:35 7-everybody
-rwxr-x--x 1 mathieu mathieu 23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ 
```

### 8. James Bond
Write a script that sets the permission to the file hello as follows:

Owner: no permission at all
Group: no permission at all
Other users: all the permissions
The file hello will be in the working directory You are not allowed to use commas for this script

```bash
mathieu@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 mathieu mathieu 28 Sep 20 14:40 8-James_Bond
-rwxr-x--x 1 mathieu mathieu 23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ ./8-James_Bond 
mathieu@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 mathieu mathieu 28 Sep 20 14:40 8-James_Bond
-------rwx 1 mathieu mathieu 23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ 
```

### 9. John Doe
Write a script that sets the mode of the file hello to this:

The file hello will be in the working directory
You are not allowed to use commas for this script

```bash
-rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello
```

### 10. Look in the mirror
Write a script that sets the mode of the file hello the same as olleh’s mode.

The file hello will be in the working directory
The file olleh will be in the working directory

```bash
mathieu@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 mathieu mathieu 42 Sep 20 14:45 10-mirror_permissions
-rwxr-x-wx 1 mathieu mathieu 23 Sep 20 14:25 hello
-rw-rw-r-- 1 mathieu mathieu  0 Sep 20 14:43 olleh
mathieu@ubuntu:/tmp/h$ ./10-mirror_permissions 
mathieu@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 mathieu mathieu 42 Sep 20 14:45 10-mirror_permissions
-rw-rw-r-- 1 mathieu mathieu 23 Sep 20 14:25 hello
-rw-rw-r-- 1 mathieu mathieu  0 Sep 20 14:43 olleh
mathieu@ubuntu:/tmp/h$ 
```

### 11. Directories
Create a script that adds execute permission to all subdirectories of the current directory for the owner, the group owner and all other users. Regular files should not be changed.

```bash
mathieu@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 mathieu mathieu   24 Sep 20 14:53 11-directories_permissions
drwx------ 2 mathieu mathieu 4096 Sep 20 14:49 dir0
drwx------ 2 mathieu mathieu 4096 Sep 20 14:49 dir1
drwx------ 2 mathieu mathieu 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 mathieu mathieu   23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ ./11-directories_permissions 
mathieu@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 mathieu mathieu   24 Sep 20 14:53 11-directories_permissions
drwx--x--x 2 mathieu mathieu 4096 Sep 20 14:49 dir0
drwx--x--x 2 mathieu mathieu 4096 Sep 20 14:49 dir1
drwx--x--x 2 mathieu mathieu 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 mathieu mathieu   23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$
```

### 12. More directories
Create a script that creates a directory called my_dir with permissions 751 in the working directory.

```bash
mathieu@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 mathieu mathieu   39 Sep 20 14:59 12-directory_permissions
drwx--x--x 2 mathieu mathieu 4096 Sep 20 14:49 dir0
drwx--x--x 2 mathieu mathieu 4096 Sep 20 14:49 dir1
drwx--x--x 2 mathieu mathieu 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 mathieu mathieu   23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ ./12-directory_permission s
mathieu@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 mathieu mathieu   39 Sep 20 14:59 12-directory_permissions
drwx--x--x 2 mathieu mathieu 4096 Sep 20 14:49 dir0
drwx--x--x 2 mathieu mathieu 4096 Sep 20 14:49 dir1
drwx--x--x 2 mathieu mathieu 4096 Sep 20 14:49 dir2
drwxr-x--x 2 mathieu mathieu 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 mathieu mathieu   23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ 
```

### 13. Change group
Write a script that changes the group owner to school for the file hello

The file hello will be in the working directory

```bash
mathieu@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 mathieu mathieu   34 Sep 20 15:03 13-change_group
drwx--x--x 2 mathieu mathieu 4096 Sep 20 14:49 dir0
drwx--x--x 2 mathieu mathieu 4096 Sep 20 14:49 dir1
drwx--x--x 2 mathieu mathieu 4096 Sep 20 14:49 dir2
drwxr-x--x 2 mathieu mathieu 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 mathieu mathieu   23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ sudo ./13-change_group 
mathieu@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 mathieu mathieu      34 Sep 20 15:03 13-change_group
drwx--x--x 2 mathieu mathieu    4096 Sep 20 14:49 dir0
drwx--x--x 2 mathieu mathieu    4096 Sep 20 14:49 dir1
drwx--x--x 2 mathieu mathieu    4096 Sep 20 14:49 dir2
drwxr-x--x 2 mathieu mathieu    4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 mathieu mathieu   23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ 
```

### 14. Owner and group
Write a script that changes the owner to vincent and the group owner to staff for all the files and directories in the working directory.

```bash
mathieu@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 mathieu mathieu   36 Sep 20 15:06 14-change_owner_and_group
drwx--x--x 2 mathieu mathieu 4096 Sep 20 14:49 dir0
drwx--x--x 2 mathieu mathieu 4096 Sep 20 14:49 dir1
drwx--x--x 2 mathieu mathieu 4096 Sep 20 14:49 dir2
drwxr-x--x 2 mathieu mathieu 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 mathieu mathieu   23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ sudo ./14-change_owner_and_group 
mathieu@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 vincent staff   36 Sep 20 15:06 14-change_owner_and_group
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir0
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir1
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir2
drwxr-x--x 2 vincent staff 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 vincent staff   23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ 
```

### 15. Symbolic links
Write a script that changes the owner and the group owner of _hello to vincent and staff respectively.

The file _hello is in the working directory
The file _hello is a symbolic link

```bash
mathieu@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 mathieu mathieu   44 Sep 20 15:12 15-symbolic_link_permissions
-rw-rw-r-- 1 mathieu mathieu   23 Sep 20 14:25 hello
lrwxrwxrwx 1 mathieu mathieu    5 Sep 20 15:10 _hello -> hello
mathieu@ubuntu:/tmp/h$ sudo ./15-symbolic_link_permissions 
mathieu@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 mathieu mathieu      44 Sep 20 15:12 15-symbolic_link_permissions
-rw-rw-r-- 1 mathieu mathieu      23 Sep 20 14:25 hello
lrwxrwxrwx 1 vincent  staff    5 Sep 20 15:10 _hello -> hello
mathieu@ubuntu:/tmp/h$ 
```

### 16. If only
Write a script that changes the owner of the file hello to vincent only if it is owned by the user guillaume.

The file hello will be in the working directory

```bash
mathieu@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 mathieu    mathieu      47 Sep 20 15:18 16-if_only 
-rw-rw-r-- 1 guillaume mathieu      23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ sudo ./16-if_only 
mathieu@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 mathieu mathieu      47 Sep 20 15:18 16-if_only 
-rw-rw-r-- 1 vincent  mathieu      23 Sep 20 14:25 hello
mathieu@ubuntu:/tmp/h$ 
```
