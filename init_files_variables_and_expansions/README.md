# SHELL, INIT FILES, VARIABLES AND EXPANSIONS

## Résumé:

### Init files
Lorsqu'un shell démarre, il lit et exécute des commandes à partir de fichiers de configuration appelés "init files". Ces fichiers renferment des variables d'environnement, des fonctions, et des commandes qui s'activent à chaque ouverture d'une nouvelle session de shell. Parmi les fichiers d'initialisation les plus couramment utilisés, on trouve ~/.bashrc, spécifique à Bash et activé pour chaque session interactive, ~/.bash_profile, également spécifique à Bash et exécuté lors de la connexion, ainsi que /etc/profile, qui contient des paramètres d'environnement système appliqués à tous les utilisateurs au moment de la connexion.

### Variables

Les variables sont des emplacements de mémoire utilisés pour stocker des données dans un programme. Elles sont caractérisées par un nom et un type, et peuvent être modifiées au cours de l'exécution du programme. Les variables facilitent le stockage et la manipulation des informations, rendant les programmes plus flexibles et dynamiques.

### Expansions

Les expansions dans le shell permettent de substituer la valeur d'une variable ou d'effectuer des opérations sur celle-ci. Plusieurs types d'expansions existent, notamment :

1. Substitution de commande : Exécute une commande et utilise sa sortie en remplacement de l'expansion, avec l'utilisation de backticks (`) ou $( ).

2. Expansion arithmétique : Permet d'effectuer des opérations mathématiques sur des variables, utilisant la syntaxe $(( )).

3. Expansion de chemin d'accès : Étend la valeur d'une variable pour correspondre à un motif de chemin d'accès de fichier, utilisant les caractères *, ?, et [].

4. Expansion d'accolades : Génère une séquence de valeurs en spécifiant une plage de valeurs à l'intérieur d'accolades {}.

Ces expansions sont des outils essentiels pour automatiser des tâches, rendant les scripts plus dynamiques et flexibles. Elles permettent aux scripts de s'adapter à des conditions changeantes sans nécessiter d'intervention manuelle.


## Resources:
* [Expansions](https://linuxcommand.org/lc3_lts0080.php)
* [Shell Arithmetic](https://www.gnu.org/software/bash/manual/html_node/Shell-Arithmetic.html)
* [Variables](https://tldp.org/LDP/Bash-Beginners-Guide/html/sect_03_02.html)
* [Shell Initialization Files](https://tldp.org/LDP/Bash-Beginners-Guide/html/sect_03_01.html)
* [The Alias Command](https://www.linfo.org/alias.html)
* [Technical Writing](https://s3.eu-west-3.amazonaws.com/hbtn.intranet/uploads/misc/2021/6/9112669886fd446a2aa3113c31319d1f468dc160.pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIA4MYA5JM5DUTZGMZG%2F20231115%2Feu-west-3%2Fs3%2Faws4_request&X-Amz-Date=20231115T202145Z&X-Amz-Expires=86400&X-Amz-SignedHeaders=host&X-Amz-Signature=6afdfaf414f7e235173f6e70bf5830f6bd3488305e926679a1bf23197086f26f)

## Requirements:

* Allowed editors: vi, vim, emacs
* All your scripts will be tested on Ubuntu 20.04 LTS
* All your scripts should be exactly two lines long ($ wc -l file should print 2)
* All your files should end with a new line (why?)
* The first line of all your files should be exactly #!/bin/bash
* A README.md file, at the root of the folder of the project, describing what each script is doing
* You are not allowed to use &&, || or ;
* You are not allowed to use bc, sed or awk
* All your files must be executable

## TASKS:

### 0. <o>
Create a script that creates an alias.

Name: ls
Value: rm *

```bash
mathieu@ubuntu:/tmp/0x03$ ls
0-alias  file1  file2
mathieu:/tmp/0x03$ source ./0-alias 
mathieu@ubuntu:/tmp/0x03$ ls
mathieu@ubuntu:/tmp/0x03$ \ls
mathieu@ubuntu:/tmp/0x03$ 

```

### 1. Hello you
Create a script that prints hello user, where user is the current Linux user.

```bash
mathieu@ubuntu:/tmp/0x03$ id
uid=1000(mathieu) gid=1000(mathieu) groups=1000(mathieu),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),113(lpadmin),128(sambashare)
mathieu@ubuntu:/tmp/0x03$ ./1-hello_you 
hello mathieu
mathieu@ubuntu:/tmp/0x03$ 
```

### 2. The path to success is to take massive, determined action
Add /action to the PATH. /action should be the last directory the shell looks into when looking for a program.

```bash
mathieu@ubuntu:/tmp/0x03$ echo $PATH
/home/mathieu/bin:/home/julien/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
mathieu@ubuntu:/tmp/0x03$ source ./2-path 
mathieu@ubuntu:/tmp/0x03$ echo $PATH
/home/mathieu/bin:/home/mathieu/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/action
mathieu@ubuntu:/tmp/0x03$ 
```

### 3. If the path be beautiful, let us not ask where it leads
Create a script that counts the number of directories in the PATH.

```bash
mathieu@ubuntu:/tmp/0x03$ echo $PATH
/home/mathieu/bin:/home/mathieu/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
mathieu@ubuntu:/tmp/0x03$ . ./3-paths 
11
mathieu@ubuntu:/tmp/0x03$ PATH=/home/mathieu/bin:/home/mathieu/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:::::/hello
mathieu@ubuntu:/tmp/0x03$ . ./3-paths 
12
mathieu@ubuntu:/tmp/0x03$ 
```

### 4. Global variables
Create a script that lists environment variables.

```bash
mathieu@ubuntu:/tmp/0x03$ source ./4-global_variables
CC=gcc
CDPATH=.:~:/usr/local:/usr:/
CFLAGS=-O2 -fomit-frame-pointer
COLORTERM=gnome-terminal
CXXFLAGS=-O2 -fomit-frame-pointer
DISPLAY=:0
DOMAIN=hq.garrels.be
e=
TOR=vi
FCEDIT=vi
FIGNORE=.o:~
G_BROKEN_FILENAMES=1
GDK_USE_XFT=1
GDMSESSION=Default
GNOME_DESKTOP_SESSION_ID=Default
GTK_RC_FILES=/etc/gtk/gtkrc:/nethome/franky/.gtkrc-1.2-gnome2
GWMCOLOR=darkgreen
GWMTERM=xterm
HISTFILESIZE=5000
history_control=ignoredups
HISTSIZE=2000
HOME=/nethome/franky
HOSTNAME=octarine.hq.garrels.be
INPUTRC=/etc/inputrc
IRCNAME=franky
JAVA_HOME=/usr/java/j2sdk1.4.0
LANG=en_US
LDFLAGS=-s
LD_LIBRARY_PATH=/usr/lib/mozilla:/usr/lib/mozilla/plugins
LESSCHARSET=latin1
LESS=-edfMQ
LESSOPEN=|/usr/bin/lesspipe.sh %s
LEX=flex
LOCAL_MACHINE=octarine
LOGNAME=franky
[...]
mathieu@ubuntu:/tmp/0x03$ 
```

### 5. Local variables
Create a script that lists all local variables and environment variables, and functions.

```bash
mathieu@ubuntu:/tmp/0x03$ . ./5-local_variables
BASH=/bin/bash
BASHOPTS=checkwinsize:cmdhist:complete_fullquote:expand_aliases:extglob:extquote:force_fignore:histappend:interactive_comments:progcomp:promptvars:sourcepath
BASH_ALIASES=()
BASH_ARGC=()
BASH_ARGV=()
BASH_CMDS=()
BASH_COMPLETION_COMPAT_DIR=/etc/bash_completion.d
BASH_LINENO=()
BASH_REMATCH=()
BASH_SOURCE=()
BASH_VERSINFO=([0]="4" [1]="3" [2]="46" [3]="1" [4]="release" [5]="x86_64-pc-linux-gnu")
BASH_VERSION='4.3.46(1)-release'
CLUTTER_IM_MODULE=xim
COLUMNS=133
COMPIZ_CONFIG_PROFILE=ubuntu
COMP_WORDBREAKS=$' \t\n"\'><=;|&(:'
DBUS_SESSION_BUS_ADDRESS=unix:abstract=/tmp/dbus-Fg27Lr20bq
DEFAULTS_PATH=/usr/share/gconf/ubuntu.default.path
DESKTOP_SESSION=ubuntu
[...]
mathieu@ubuntu:/tmp/0x03$ 
```

### 6. Local variable
Create a script that creates a new local variable.

Name: BEST
Value: School

### 7. Global variable
Create a script that creates a new global variable.

Name: BEST
Value: School

### 8. Every addition to true knowledge is an addition to human power
Write a script that prints the result of the addition of 128 with the value stored in the environment variable TRUEKNOWLEDGE, followed by a new line.

```bash
mathieu@production-503e7013:~$ export TRUEKNOWLEDGE=1209
mathieu@production-503e7013:~$ ./8-true_knowledge | cat -e
1337$
mathieu@production-503e7013:~$
```

### 9. Divide and rule
Write a script that prints the result of POWER divided by DIVIDE, followed by a new line.

POWER and DIVIDE are environment variables

```bash
mathieu@production-503e7013:~$ export POWER=42784
mathieu@production-503e7013:~$ export DIVIDE=32
mathieu@production-503e7013:~$ ./9-divide_and_rule | cat -e
1337$
mathieu@production-503e7013:~$
```

### 10. Love is anterior to life, posterior to death, initial of creation, and the exponent of breath
Write a script that displays the result of BREATH to the power LOVE

BREATH and LOVE are environment variables
The script should display the result, followed by a new line

```bash
mathieu@production-503e7013:~/$ export BREATH=4
mathieu@production-503e7013:~/$ export LOVE=3
mathieu@production-503e7013:~/$ ./10-love_exponent_breath
64
mathieu@production-503e7013:~/$
```

### 11. There are 10 types of people in the world -- Those who understand binary, and those who don't
Write a script that converts a number from base 2 to base 10.

The number in base 2 is stored in the environment variable BINARY
The script should display the number in base 10, followed by a new line

```bash
mathieu@production-503e7013:~/$ export BINARY=10100111001
mathieu@production-503e7013:~/$ ./11-binary_to_decimal
1337
mathieu@production-503e7013:~/$
```

### 12. Combination
Create a script that prints all possible combinations of two letters, except oo.

Letters are lower cases, from a to z
One combination per line
The output should be alpha ordered, starting with aa
Do not print oo
Your script file should contain maximum 64 characters

```bash
mathieu@ubuntu:/tmp/0x03$ echo $((26 ** 2 -1))
675
mathieu@ubuntu:/tmp/0x03$ ./12-combinations | wc -l
675
mathieu@ubuntu:/tmp/0x03$ 
mathieu@ubuntu:/tmp/0x03$ ./12-combinations | tail -303 | head -10
oi
oj
ok
ol
om
on
op
oq
or
os
mathieu@ubuntu:/tmp/0x03$ 
```

### 13. Floats
Write a script that prints a number with two decimal places, followed by a new line.

The number will be stored in the environment variable NUM.

```bash
ubuntu@ip-172-31-63-244:~/0x03$ export NUM=0
ubuntu@ip-172-31-63-244:~/0x03$ ./13-print_float
0.00
ubuntu@ip-172-31-63-244:~/0x03$ export NUM=98
ubuntu@ip-172-31-63-244:~/0x03$ ./13-print_float
98.00
ubuntu@ip-172-31-63-244:~/0x03$ export NUM=3.14159265359
ubuntu@ip-172-31-63-244:~/0x03$ ./13-print_float
3.14
ubuntu@ip-172-31-63-244:~/0x03$
```

### 14. Decimal to Hexadecimal
Write a script that converts a number from base 10 to base 16.

The number in base 10 is stored in the environment variable DECIMAL
The script should display the number in base 16, followed by a new line

```bash
mathieu@production-503e7013:~/$ export DECIMAL=16
mathieu@production-503e7013:~/$ ./14-decimal_to_hexadecimal
10
mathieu@production-503e7013:~/$ export DECIMAL=1337
mathieu@production-503e7013:~/$ ./14-decimal_to_hexadecimal | cat -e
539$
mathieu@production-503e7013:~/$ export DECIMAL=15
mathieu@production-503e7013:~/$ ./14-decimal_to_hexadecimal | cat -e
f$
mathieu@production-503e7013:~/$
```
