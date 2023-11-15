# SHELL

Le terme "Shell" peut faire référence à deux concepts distincts : le shell en tant qu'interface utilisateur en ligne de commande et le shell comme un langage de programmation de script. Voici un résumé de ces deux aspects :

* Shell comme interface utilisateur en ligne de commande :
 * Définition : Le shell est une interface en ligne de commande qui permet à l'utilisateur d'interagir avec le système d'exploitation en saisissant des commandes.

 * Commandes de base :

  * cd : Changer de répertoire.
  * ls : Lister le contenu d'un répertoire.
  * mkdir : Créer un nouveau répertoire.
  * cp : Copier des fichiers ou des répertoires.
  * mv : Déplacer ou renommer des fichiers ou des répertoires.
  * rm : Supprimer des fichiers ou des répertoires.
  * echo : Afficher du texte à la sortie standard.
  * cat : Afficher le contenu d'un fichier.

 * Opérations avancées :

  * Redirection (>, >>) : Rediriger la sortie vers un fichier.
  * Pipe (|) : Passer la sortie d'une commande comme entrée à une autre.
  * Variables d'environnement : Stocker des informations utiles au système.
  * Alias : Créer des raccourcis pour des commandes fréquemment utilisées.

### General
* What does RTFM mean?
* What is a Shebang

### What is the Shell
* What is the shell
* What is the difference between a terminal and a shell
* What is the shell prompt
* How to use the history (the basics)

### Navigation
* What do the commands or built-ins cd, pwd, ls do
* How to navigate the filesystem
* What are the . and .. directories
* What is the working directory, how to print it and how to change it
* What is the root directory
* What is the home directory, and how to go there
* What is the difference between the root directory and the home directory of the user root
* What are the characteristics of hidden files and how to list them
* What does the command cd - do

### Looking Around
* What do the commands ls, less, file do
* How do you use options and arguments with commands
* Understand the ls long format and how to display it
* A Guided Tour
* What does the ln command do
* What do you find in the most common/important directories
* What is a symbolic link
* What is a hard link
* What is the difference between a hard link and a symbolic link

### Manipulating Files
* What do the commands cp, mv, rm, mkdir do
* What are wildcards and how do they work
* How to use wildcards

### Working with Commands
* What do type, which, help, man commands do
* What are the different kinds of commands
* What is an alias
* When do you use the command help instead of man

### Reading Man Pages
* How to read a man page
* What are man page sections
* What are the section numbers for User commands, System calls and Library functions

### Keyboard Shortcuts for Bash
* Common shortcuts for Bash

### LTS
* What does LTS mean?


### General
* Allowed editors: vi, vim, emacs
* All your scripts will be tested on Ubuntu 20.04 LTS
* All your scripts should be exactly two lines long ($ wc -l file should print 2)
* All your files should end with a new line (why?)
* The first line of all your files should be exactly #!/bin/bash
* A README.md file at the root of the repo, containing a description of the repository
* A README.md file, at the root of the folder of this project, describing what each script is doing
* You are not allowed to use backticks, &&, || or ;
* All your scripts must be executable. To make your file executable, use the chmod command: chmod u+x file. Later, we’ll learn more about how to utilize this command.
