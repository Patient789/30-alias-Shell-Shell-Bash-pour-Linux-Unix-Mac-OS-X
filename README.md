# 30-alias-Shell-Shell-Bash-pour-Linux-Unix-Mac-OS-X
Un alias bash n'est rien d'autre que le raccourci des commandes. La commande alias permet à l'utilisateur de lancer n'importe quelle commande ou groupe de commandes (y compris les options et les noms de fichiers) en entrant un seul mot. Utilisez la commande alias pour afficher une liste de tous les alias définis

Un alias bash n'est rien d'autre que le raccourci des commandes. La commande alias permet à l'utilisateur de lancer n'importe quelle commande ou groupe de commandes (y compris les options et les noms de fichiers) en entrant un seul mot. Utilisez la commande alias pour afficher une liste de tous les alias définis. Vous pouvez ajouter des alias définis par l'utilisateur au fichier ~ / .bashrc . Vous pouvez réduire le temps de frappe avec ces alias, travailler intelligemment et augmenter la productivité à l'invite de commande.

Ce billet montre comment créer et utiliser des alias, y compris 30 exemples pratiques d'alias de shell bash.
30 Bash Shell Aliase utile pour les utilisateurs de Linux / Unix

En savoir plus sur l'alias bash
La syntaxe générale de la commande alias pour le shell bash est la suivante:

Comment lister les alias de bash
Tapez la commande alias suivante : 
alias

Exemples de sorties:

alias .. = 'cd ..'
alias amazonbackup = 's3backup'
alias apt-get = 'sudo apt-get'
...
Par défaut, la commande alias affiche une liste d'alias définis pour l'utilisateur actuel.

Comment définir ou créer un alias shell bash
Pour créer l'alias, utilisez la syntaxe suivante:

alias  nom = valeur
 alias  nom = 'commande' 
alias  nom = 'commande arg1 arg2' 
alias  nom = '/ chemin / vers / script' 
alias  nom = '/path/to/script.pl arg1'
Dans cet exemple, créez l'alias c pour la commande clear utilisée, qui efface l'écran, en tapant la commande suivante et en appuyant sur la touche ENTRÉE:

alias  c = 'effacer'
Ensuite, pour effacer l'écran, au lieu de taper clear, il vous suffira de taper la lettre 'c' et d'appuyer sur la touche [ENTER]:

c
Comment désactiver un alias bash temporairement
Un alias peut être désactivé temporairement en utilisant la syntaxe suivante:

## chemin / vers / full / commande 
/ usr / bin / clear 
## appelle un alias avec un backslash ##
\ c
## use / bin / ls commande et évite ls alias ## 
commande  ls
Comment supprimer / supprimer un alias bash
Vous devez utiliser la commande appelée unalias pour supprimer les alias . Sa syntaxe est la suivante:

alias unalias
 unalias foo
Dans cet exemple, supprimez l'alias c qui a été créé dans un exemple précédent:

Unalias c
Vous devez également supprimer l'alias du fichier ~ / .bashrc à l' aide d'un éditeur de texte (voir la section suivante).

Comment faire des alias de shell bash permanents
L'alias c reste actif uniquement pendant la session de connexion en cours. Une fois que vous avez déconnecté ou redémarré le système, l'alias c sera parti. Pour éviter ce problème, ajoutez un alias à votre fichier ~ / .bashrc , entrez:

vi ~ / .bashrc
L'alias c pour l'utilisateur courant peut être rendu permanent en entrant la ligne suivante:

alias  c = 'effacer'
Enregistrez et fermez le fichier. Les alias à l'échelle du système (c'est-à-dire les alias pour tous les utilisateurs) peuvent être placés dans le fichier / etc / bashrc. S'il vous plaît noter que la commande d'alias est construit dans divers shells, y compris ksh, tcsh / csh, cendres, bash et d'autres.

Une note sur l'accès privilégié
Vous pouvez ajouter du code comme suit dans ~ / .bashrc:

# si l'utilisateur n'est pas root, passez toutes les commandes via sudo # 
if  [  $ UID  -ne  0  ] ; puis 
    alias  reboot = 'sudo reboot' 
    alias  update = 'sudo apt-get mise à niveau' 
fi
Une note sur les alias spécifiques à un os
Vous pouvez ajouter du code comme suit dans ~ / .bashrc en utilisant l'instruction case :

### Obtenir le nom de l'OS via uname ### 
_myos = " $ (uname) "
 
### ajouter un alias selon os en utilisant $ _myos ### 
case  $ _myos  sous 
   Linux )  alias  foo = '/ chemin / vers / linux / bin / foo' ;; 
   FreeBSD | OpenBSD )  alias  foo = '/ chemin / vers / bsd / bin / foo'  ;; 
   SunOS )  alias  foo = '/ chemin / vers / sunos / bin / foo'  ;; 
   * )  ;; 
Esac
30 exemples d'alias de shell bash
Vous pouvez définir différents types d'alias comme suit pour gagner du temps et augmenter la productivité.

# 1: Contrôlez la sortie de la commande ls
La commande ls répertorie le contenu du répertoire et vous pouvez colorier la sortie:

## Colorise la sortie ls ## 
alias  ls = 'ls --color = auto'
 
## Utiliser un format de liste longue ## 
alias  ll = 'ls -la'
 
## Afficher les fichiers cachés ## 
alias l. = 'Ls -d. * --color = auto'
# 2: Contrôler le comportement de la commande cd
## se débarrasser de la commande introuvable ## 
alias cd .. = 'cd ..'
 
## un moyen rapide de sortir du répertoire courant ## 
alias .. = 'cd ..' 
alias ... = 'cd ../../../' 
alias .... = 'cd ../ ../../../ ' 
alias ..... = ' cd ../../../../ ' 
alias .4 = ' cd ../../../../ ' 
alias .5 = ' cd ../../../../ .. '
# 3: Contrôler la sortie de la commande grep
La commande grep est un utilitaire de ligne de commande permettant de rechercher des fichiers en texte brut pour des lignes correspondant à une expression régulière:

## Colorise la sortie de la commande grep pour la facilité d'utilisation (bon pour les fichiers journaux) ## 
alias  grep = 'grep --color = auto' 
alias  egrep = 'egrep --color = auto' 
alias  fgrep = 'fgrep --color = auto'
# 4: Démarrer la calculatrice avec le support mathématique
alias  bc = 'bc -l'
# 4: Générer sha1 digest
alias  sha1 = 'openssl sha1'
# 5: Créer des répertoires parents à la demande
La commande mkdir est utilisée pour créer un répertoire:

alias  mkdir = 'mkdir -pv'
# 6: Coloriser la sortie diff
Vous pouvez comparer les fichiers ligne par ligne en utilisant diff et utiliser un outil appelé colordiff pour colorier la sortie diff:

# install package colordiff :) 
alias  diff = 'colordiff'
# 7: Rendre la sortie de commande de montage jolie et format lisible par l'homme
alias  mount = 'mount | colonne -t'
# 8: raccourcis de commande pour gagner du temps
# raccourcis pratiques # 
alias  h = 'histoire' 
alias  j = 'jobs -l'
# 9: Créer un nouvel ensemble de commandes
alias  chemin = 'echo -e $ {PATH //: / \\ n}' 
alias  maintenant = 'date + "% T"' 
alias  nowtime = maintenant
 alias  nowdate = 'date + "% d-% m-% Y" '
# 10: Définir vim par défaut
alias  vi = vim 
alias  svi = 'sudo vi' 
alias  vis = 'vim' + set si "' 
alias  edit = ' vim '
# 11: Sortie de contrôle de l'outil de mise en réseau appelé ping
# Stop après l'envoi du compte ECHO_REQUEST paquets # 
alias  ping = 'ping -c 5' 
# Ne pas attendre intervalle 1 seconde, aller vite # 
alias  fastping = 'ping -c 100 -s.2'
# 12: Afficher les ports ouverts
Utilisez la commande netstat pour lister rapidement tous les ports TCP / UDP sur le serveur:

alias  ports = 'netstat -tulanp'
# 13: Serveurs endormis de réveil
Wake-on-LAN (WOL) est une norme de réseau Ethernet qui permet à un serveur d'être activé par un message réseau. Vous pouvez rapidement réactiver les périphériques nas et le serveur en utilisant les alias suivants:

## remplace mac avec votre serveur actuel adresse mac # 
alias  wakeupnas01 = '/ usr / bin / wakeonlan 00: 11: 32: 11: 15: FC' 
alias  wakeupnas02 = '/ usr / bin / wakeonlan 00: 11: 32: 11 FD ' 
alias  wakeupnas03 = ' / usr / bin / wakeonlan 00: 11: 32: 11: 15: FE '
# 14: Sortie du pare-feu de contrôle (iptables)
Netfilter est un pare-feu basé sur l'hôte pour les systèmes d'exploitation Linux. Il est inclus dans la distribution Linux et il est activé par défaut. Cette publication répertorie les solutions iptables les plus courantes requises par un nouvel utilisateur Linux pour sécuriser son système d'exploitation Linux contre les intrusions.

## raccourci pour iptables et le passer via sudo # 
alias  ipt = 'sudo / sbin / iptables'
 
# afficher toutes les règles # 
alias  iptlist = 'sudo / sbin / iptables -L -n -v -ligne-numéros' 
alias  iptlistin = 'sudo / sbin / iptables -L INPUT -n -v -ligne 
-ligne alias  iptlistout = 'sudo / sbin / iptables -L OUTPUT -n -v --ligne-numéros' 
alias  iptlistfw = 'sudo / sbin / iptables -L FORWARD -n -v -ligne-numéros' 
alias  pare-feu = iptlist
# 15: Déboguer les problèmes du serveur web / cdn avec curl
# obtenir les en-têtes du serveur web # 
alias  header = 'curl -I'
 
# savoir si le serveur distant supporte gzip / mod_deflate ou pas # 
alias  headerc = 'curl -I --compress'
# 16: Ajouter des filets de sécurité
# ne supprime pas / ou ne vous demande pas si vous supprimez plus de 3 fichiers à la fois # 
alias  rm = 'rm -I --preserve-root'
 
# confirmation # 
alias  mv = 'mv -i' 
alias  cp = 'cp -i' 
alias  ln = 'ln -i'
 
# Parenting changeant les perms sur / # 
alias  chown = 'chown --preserve-root' 
alias  chmod = 'chmod --preserve-root' 
alias  chgrp = 'chgrp --preserve-root'
# 17: Mettre à jour le serveur Debian Linux
La commande apt-get est utilisée pour installer des paquets sur internet (ftp ou http). Vous pouvez également mettre à niveau tous les paquets en une seule opération:

# distribution spécifique - Debian / Ubuntu et amis # 
# install avec apt-get 
alias apt-get = "sudo apt-get" 
alias  updatey = "sudo apt-get --yes"
 
# mise à jour sur une commande 
alias  update = 'sudo apt-get update && sudo apt-get upgrade'
# 18: Mise à jour du serveur RHEL / CentOS / Fedora Linux
La commande yum est un outil de gestion de paquets pour RHEL / CentOS / Fedora Linux et ses amis:

## distrp specifc RHEL / CentOS ## 
alias  update = 'yum update' 
alias  updatey = 'yum -y update'
# 19: Tune sudo et su
# devenir racine # 
alias  root = 'sudo -i' 
alias  su = 'sudo -i'
# 20: Passe stopper / redémarrer via sudo
La commande shutdown amène le système Linux / Unix à l'arrêt:

# reboot / halt / poweroff 
alias  reboot = 'sudo / sbin / reboot' 
alias  poweroff = 'sudo / sbin / poweroff' 
alias  halt = 'sudo / sbin / halt' 
alias  shutdown = 'sudo / sbin / shutdown'
# 21: Contrôler les serveurs web
# aussi le passer via sudo pour que celui qui est admin puisse le recharger sans vous appeler # 
alias  nginxreload = 'sudo / usr / local / nginx / sbin / nginx -s reload' 
alias  nginxtest = 'sudo / usr / local / nginx / sbin / nginx -t ' 
alias  lightyload = ' sudo /etc/init.d/lighttpd reload ' 
alias  lightytest = ' sudo / usr / sbin / lighttpd -f /etc/lighttpd/lighttpd.conf -t ' 
alias  httpdreload = ' sudo / usr / sbin / apachectl -k gracieux ' 
alias  httpdtest = ' sudo / usr / sbin / apachectl -t && / usr / sbin / apachectl -t -D DUMP_VHOSTS '
# 22: Alias ​​dans nos trucs de sauvegarde
# si cron échoue ou si vous voulez une sauvegarde à la demande, exécutez simplement ces commandes # 
# passez à nouveau par sudo pour que celui qui est dans le groupe admin puisse démarrer le travail # 
# Scripts de 
sauvegarde alias  backup = 'sudo / home / scripts / admin / scripts /backup/wrapper.backup.sh --type local --taget / raid1 / 
alias de  sauvegarde nasbackup = 'sudo /home/scripts/admin/scripts/backup/wrapper.backup.sh --type nas --target nas01' 
alias  s3backup = 'sudo /home/scripts/admin/scripts/backup/wrapper.backup.sh --type nas --target nas01 --auth /home/scripts/admin/.authdata/amazon.keys' 
alias  rsnapshothourly ='sudo /home/scripts/admin/scripts/backup/wrapper.rsnapshot.sh --type distant --target nas03 --auth /home/scripts/admin/.authdata/ssh.keys --config / home / scripts / admin / scripts / backup / config / adsl.conf ' 
alias  rsnapshotdaily = ' sudo /home/scripts/admin/scripts/backup/wrapper.rsnapshot.sh --type distant --target nas03 --auth / home / scripts / admin /.authdata/ssh.keys --config /home/scripts/admin/scripts/backup/config/adsl.conf ' 
alias  rsnapshotweekly = ' sudo /home/scripts/admin/scripts/backup/wrapper.rsnapshot.sh - tapez remote --target nas03 --auth /home/scripts/admin/.authdata/ssh.keys --config /home/scripts/admin/scripts/backup/config/adsl.conf ' 
alias  rsnapshotmonthly ='sudo /home/scripts/admin/scripts/backup/wrapper.rsnapshot.sh --type distant --target nas03 --auth /home/scripts/admin/.authdata/ssh.keys --config / home / scripts / admin / scripts / backup / config / adsl.conf ' 
alias  amazonbackup = s3backup
# 23: Spécifique au bureau - lire des fichiers avi / mp3 à la demande
## lire les fichiers vidéo dans un répertoire courant ## 
# cd ~ / Download / movie-name 
# playavi ou vlc 
alias  playavi = 'mplayer * .avi' 
alias  vlc = 'vlc * .avi'
 
# lire tous les fichiers musicaux du répertoire courant # 
alias  playwave = 'pour i in * .wav; fais mplayer "$ i"; fait ' 
alias  playogg = ' pour i dans * .ogg; fais mplayer "$ i"; fait ' 
alias  playmp3 = ' pour i dans * .mp3; fais mplayer "$ i"; terminé'
 
# lire les fichiers depuis les périphériques nas # 
alias  nplaywave = 'for i in /nas/multimedia/wave/*.wav; fais mplayer "$ i"; fait ' 
alias  nplayogg = ' pour i dans /nas/multimedia/ogg/*.ogg; fais mplayer "$ i"; fait ' 
alias  nplaymp3 = ' pour i dans /nas/multimedia/mp3/*.mp3; fais mplayer "$ i"; terminé'
 
# shuffle mp3 / ogg etc par défaut # 
alias  music = 'mplayer --shuffle *'
# 24: Définir les interfaces par défaut pour les commandes liées à l'administration de sys
vnstat est un moniteur de trafic réseau basé sur la console . dnstop est un outil de console pour analyser le trafic DNS. Les commandes tcptrack et iftop affichent des informations sur les connexions TCP / UDP qu'il voit sur une interface réseau et affichent l'utilisation de la bande passante sur une interface par l'hôte respectivement.

## Tous nos serveurs eth1 sont connectés aux Internets via vlan / routeur etc ## 
alias  dnstop = 'dnstop -l 5 eth1' 
alias  vnstat = 'vnstat -i eth1' 
alias  iftop = 'iftop -i eth1' 
alias  tcpdump = 'tcpdump -i eth1' 
alias  ethtool = 'ethtool eth1'
 
# travail sur wlan0 par défaut # 
# Seulement utile pour ordinateur portable car tous les serveurs sont sans 
alias d'  interface sans fil iwconfig = 'iwconfig wlan0'
# 25: Obtenir rapidement la mémoire système, l'utilisation du processeur et les informations de la mémoire gpu
## passe les options pour libérer ## 
alias  meminfo = 'free -m -l -t'
 
## obtiennent le processus supérieur mangeant la mémoire 
alias  psmem = 'ps auxf | sort -nr -k 4 ' 
pseudonyme  psmem10 = ' ps auxf | trier -nr -k 4 | tête -10 '
 
## obtenir le processus supérieur mangeant cpu ## 
alias  pscpu = 'ps auxf | sort -nr -k 3 ' 
alias  pscpu10 = ' ps auxf | trier -nr -k 3 | tête -10 '
 
## Obtenir le serveur cpu info ## 
alias  cpuinfo = 'lscpu'
 
## ancien système use / proc / cpuinfo ## 
## alias cpuinfo = 'less / proc / cpuinfo' ##
 
## obtient le RAM GPU sur le bureau / portable ## 
alias  gpumeminfo = 'grep -i - couleur de la mémoire /var/log/Xorg.0.log'
# 26: Contrôler le routeur domestique
La commande curl peut être utilisée pour redémarrer les routeurs Linksys .

# Redémarrez mon routeur / passerelle Linksys WAG160N / WAG54 / WAG320 / WAG120N à partir de * nix. 
alias  rebootlinksys = "curl -u 'admin: mon-super-mot de passe' 'http://192.168.1.2/setup.cgi?todo=reboot'"
 
# Reboot base de tomate Asus NT16 pont sans fil 
alias  reboottomato = "admin@192.168.1.1 ssh / sbin / reboot"
# 27 Reprendre wget par défaut
Le GNU Wget est un utilitaire gratuit pour le téléchargement non-interactif de fichiers à partir du Web. Il prend en charge les protocoles HTTP, HTTPS et FTP, et il peut également reprendre les téléchargements:

## celui-ci sauvé par butt tant de fois ## 
alias  wget = 'wget -c'
# 28 Utiliser un navigateur différent pour tester le site Web
## celui-ci sauvé par butt tant de fois ## 
alias  ff4 = '/ opt / firefox4 / firefox' 
alias  ff13 = '/ opt / firefox13 / firefox' 
alias  chrome = '/ opt / google / chrome / chrome' 
alias  opera = '/ opt / opéra / opéra'
 
#default ff 
alias  ff = ff13
 
navigateur par défaut #my 
alias  navigateur = chrome
# 29: Une note sur l'alias ssh
Ne créez pas d'alias ssh, utilisez plutôt les fichiers de configuration du client SSSS ~ / .ssh / config. Il offre plus d'option. Un exemple:

Serveur hôte10
  Nom d'hôte 1.2.3.4
  IdentityFile ~ / backups / .ssh / id_dsa
  utilisateur foobar
  Port 30000
  ForwardX11Trusted oui
  TCPKeepAlive oui
Vous pouvez maintenant vous connecter à peer1 en utilisant la syntaxe suivante:
$ ssh server10

# 30: C'est à toi de partager ...
## set d'autres valeurs par défaut ## 
alias  df = 'df -H' 
alias  du = 'du -ch'
 
# top est au sommet, tout comme vi est 
alias  vim top = 'atop'
 
## nfsrestart - doit être root ## 
## rafraîchir nfs mount / cache etc pour Apache ## 
alias  nfsrestart = 'synchroniser && sleep 2 && /etc/init.d/httpd stop && umount netapp2: / exports / http && sleep 2 && mount -o rw, synchronisation, rsize = 32768, wsize = 32768, intr, dur, proto = tcp, fsc natapp2: / exports / http / var / www / html && /etc/init.d/httpd start '
 
## état du serveur Memcached ## 
alias  mcdstats = '/ usr / bin / memcached-outil 10.10.27.11:11211 stats' 
alias  mcdshow = '/ usr / bin / memcached-outil 10.10.27.11:11211 affichage'
 
## vider rapidement le serveur memcached ## 
alias  flushmcd = 'echo "flush_all" | nc 10.10.27.11 11211 '
 
## Supprimer les actifs rapidement d'Akamai / Amazon cdn ## 
alias  cdndel = '/ home / scripts / admin / cdn / purge_cdn_cache --profile akamai' 
alias  amzcdndel = '/ home / scripts / admin / cdn / purge_cdn_cache --profile amazon'
 
## fournir la liste des urls via un fichier ou un 
alias  stdin cdnmdel = '/ home / scripts / admin / cdn / purge_cdn_cache --profil akamai --stdin' 
alias  amzcdnmdel = '/ home / scripts / admin / cdn / purge_cdn_cache --profil amazon --stdin '
Conclusion
Ce post résume plusieurs types d'utilisation des alias * nix bash:

Définition des options par défaut pour une commande (par exemple, définissez eth0 comme option par défaut pour la commande ethtool via alias ethtool='ethtool eth0').
Corriger les fautes de frappe (cd .. agira comme cd .. via alias cd..='cd ..').
Réduire la quantité de frappe.
Définir le chemin par défaut d'une commande qui existe dans plusieurs versions sur un système (par exemple, GNU / grep se trouve dans / usr / local / bin / grep et Unix grep se trouve dans / bin / grep Pour utiliser l'utilisation GNU grep alias grep='/usr/local/bin/grep').
Ajout des filets de sécurité à Unix en rendant les commandes interactives en définissant les options par défaut. (par exemple, commandes rm, mv et autres).
Compatibilité en créant des commandes pour des systèmes d'exploitation plus anciens tels que MS-DOS ou d'autres systèmes d'exploitation de type Unix (par exemple, alias del = rm).
J'ai partagé mes alias que j'ai utilisés au cours des années pour réduire le besoin de typage de ligne de commande répétitif. Si vous connaissez et utilisez d'autres alias bash / ksh / csh qui peuvent réduire la frappe, partagez ci-dessous dans les commentaires.
