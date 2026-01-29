# Introduction à Linux - Cours Complet pour Débutants

## Table des matières

1. [Qu'est-ce que Linux ?](#1-quest-ce-que-linux)
2. [Les distributions Linux](#2-les-distributions-linux)
3. [Installation et démarrage](#3-installation-et-démarrage)
4. [L'interface Linux](#4-linterface-linux)
5. [La ligne de commande (Terminal)](#5-la-ligne-de-commande-terminal)
6. [Le système de fichiers](#6-le-système-de-fichiers)
7. [Commandes de base](#7-commandes-de-base)
8. [Gestion des fichiers et répertoires](#8-gestion-des-fichiers-et-répertoires)
9. [Permissions et droits d'accès](#9-permissions-et-droits-daccès)
10. [Gestion des utilisateurs](#10-gestion-des-utilisateurs)
11. [Gestion des processus](#11-gestion-des-processus)
12. [Installation de logiciels](#12-installation-de-logiciels)
13. [Commandes avancées utiles](#13-commandes-avancées-utiles)
14. [Exercices pratiques](#14-exercices-pratiques)

---

## 1. Qu'est-ce que Linux ?

### 1.1 Définition

**Linux** est un système d'exploitation open source, gratuit et libre, créé par Linus Torvalds en 1991. C'est une alternative aux systèmes propriétaires comme Windows et macOS.

### 1.2 Caractéristiques principales

- **Open Source** : Le code source est accessible et modifiable
- **Gratuit** : Aucun coût de licence
- **Sécurisé** : Moins vulnérable aux virus et malwares
- **Stable** : Peut fonctionner pendant des mois sans redémarrage
- **Flexible** : Personnalisable selon vos besoins
- **Multiutilisateur** : Plusieurs utilisateurs peuvent travailler simultanément
- **Puissant** : Utilisé par 90% des serveurs web mondiaux

### 1.3 Différences avec Windows

| Caractéristique | Linux | Windows |
|-----------------|-------|---------|
| Coût | Gratuit | Payant |
| Code source | Ouvert | Fermé |
| Personnalisation | Très élevée | Limitée |
| Sécurité | Très élevée | Moyenne |
| Ligne de commande | Essentielle | Optionnelle |
| Installation logiciels | Gestionnaire de paquets | Fichiers .exe |

---

## 2. Les distributions Linux

### 2.1 Qu'est-ce qu'une distribution ?

Une **distribution Linux** (ou "distro") est un système d'exploitation complet basé sur le noyau Linux, avec des logiciels préinstallés et une interface graphique.

### 2.2 Principales distributions pour débutants

#### **Ubuntu**
- La plus populaire et conviviale
- Grande communauté et documentation
- Idéale pour débuter

#### **Linux Mint**
- Basée sur Ubuntu
- Interface similaire à Windows
- Très facile à prendre en main

#### **Fedora**
- Technologies récentes
- Stable et sécurisée
- Sponsorisée par Red Hat

#### **Debian**
- Très stable
- Base de nombreuses autres distributions
- Excellente pour les serveurs

### 2.3 Distributions pour utilisateurs avancés

- **Arch Linux** : Configuration manuelle complète
- **Gentoo** : Compilation depuis les sources
- **Kali Linux** : Spécialisée en cybersécurité

---

## 3. Installation et démarrage

### 3.1 Méthodes d'installation

#### A. Installation complète
Remplace complètement votre système actuel

#### B. Dual-boot
Permet de choisir entre Linux et Windows au démarrage

#### C. Machine virtuelle
Exécute Linux à l'intérieur de votre système actuel (VirtualBox, VMware)

#### D. Live USB
Teste Linux sans installation depuis une clé USB

### 3.2 Prérequis matériels minimaux

- **Processeur** : 1 GHz ou plus
- **RAM** : 2 GB minimum (4 GB recommandé)
- **Disque dur** : 20 GB minimum
- **Carte graphique** : Compatible VGA

### 3.3 Étapes d'installation (Ubuntu)

1. Télécharger l'image ISO depuis ubuntu.com
2. Créer une clé USB bootable (avec Rufus, Etcher, etc.)
3. Démarrer depuis la clé USB
4. Choisir la langue
5. Sélectionner le type d'installation
6. Partitionner le disque
7. Créer votre compte utilisateur
8. Attendre la fin de l'installation
9. Redémarrer l'ordinateur

---

## 4. L'interface Linux

### 4.1 Environnements de bureau

#### **GNOME**
- Moderne et épuré
- Interface à la macOS
- Par défaut sur Ubuntu

#### **KDE Plasma**
- Très personnalisable
- Interface à la Windows
- Riche en fonctionnalités

#### **XFCE**
- Léger et rapide
- Idéal pour vieux ordinateurs
- Simple et efficace

#### **Cinnamon**
- Par défaut sur Linux Mint
- Interface traditionnelle
- Facile à utiliser

### 4.2 Composants de l'interface

- **Barre supérieure/inférieure** : Accès aux applications et paramètres
- **Menu d'applications** : Lance vos programmes
- **Gestionnaire de fichiers** : Explore vos documents
- **Terminal** : Interface en ligne de commande
- **Zones de travail** : Bureaux virtuels multiples

---

## 5. La ligne de commande (Terminal)

### 5.1 Pourquoi utiliser le terminal ?

- **Rapidité** : Exécution plus rapide des tâches
- **Puissance** : Accès à toutes les fonctionnalités
- **Automatisation** : Création de scripts
- **Contrôle** : Gestion précise du système
- **Administration** : Gestion de serveurs distants

### 5.2 Ouvrir le terminal

- **Raccourci clavier** : `Ctrl + Alt + T`
- **Menu applications** : Chercher "Terminal"
- **Clic droit** : Sur le bureau → "Ouvrir un terminal"

### 5.3 Structure d'une commande

```bash
commande [options] [arguments]
```

**Exemple** :
```bash
ls -la /home/utilisateur
```
- `ls` : la commande (lister)
- `-la` : les options (format long + fichiers cachés)
- `/home/utilisateur` : l'argument (chemin)

### 5.4 Le prompt

```bash
utilisateur@nomdelamachine:~$
```

Signification :
- `utilisateur` : nom de l'utilisateur connecté
- `nomdelamachine` : nom de l'ordinateur
- `~` : répertoire courant (~ = répertoire personnel)
- `$` : utilisateur normal (`#` pour root/administrateur)

---

## 6. Le système de fichiers

### 6.1 Structure hiérarchique

Linux organise tout en arborescence, avec `/` comme racine.

```
/
├── bin/        # Programmes essentiels
├── boot/       # Fichiers de démarrage
├── dev/        # Périphériques (devices)
├── etc/        # Fichiers de configuration
├── home/       # Répertoires personnels des utilisateurs
│   └── utilisateur/
├── lib/        # Bibliothèques partagées
├── media/      # Points de montage (clé USB, CD)
├── mnt/        # Montages temporaires
├── opt/        # Applications optionnelles
├── proc/       # Informations système virtuelles
├── root/       # Répertoire de l'administrateur
├── sbin/       # Programmes système
├── tmp/        # Fichiers temporaires
├── usr/        # Applications utilisateur
└── var/        # Données variables (logs, cache)
```

### 6.2 Répertoires importants expliqués

#### **/home**
Contient les répertoires personnels de tous les utilisateurs
- `/home/florent/` : Vos documents, images, téléchargements, etc.

#### **/etc**
Fichiers de configuration du système et des applications

#### **/var/log**
Fichiers journaux (logs) du système

#### **/tmp**
Fichiers temporaires (effacés au redémarrage)

#### **/usr/bin**
Programmes installés par l'utilisateur

### 6.3 Chemins absolus vs relatifs

#### **Chemin absolu**
Commence par `/`, part de la racine
```bash
/home/utilisateur/Documents/fichier.txt
```

#### **Chemin relatif**
Par rapport au répertoire courant
```bash
Documents/fichier.txt
./Documents/fichier.txt
../Images/photo.jpg  # .. = répertoire parent
```

### 6.4 Répertoires spéciaux

- `.` : Répertoire courant
- `..` : Répertoire parent
- `~` : Répertoire personnel (/home/utilisateur)
- `/` : Racine du système

---

## 7. Commandes de base

### 7.1 Navigation dans les répertoires

#### **pwd** - Afficher le répertoire courant
```bash
pwd
# Résultat : /home/utilisateur
```

#### **cd** - Changer de répertoire
```bash
cd /home/utilisateur/Documents    # Chemin absolu
cd Documents                       # Chemin relatif
cd ..                             # Remonter d'un niveau
cd ~                              # Aller au répertoire personnel
cd -                              # Revenir au répertoire précédent
cd                                # Raccourci vers ~
```

#### **ls** - Lister le contenu
```bash
ls                    # Liste simple
ls -l                 # Format long (détails)
ls -a                 # Affiche les fichiers cachés
ls -la                # Combine les deux
ls -lh                # Taille lisible (human-readable)
ls -lt                # Trie par date de modification
ls -lS                # Trie par taille
ls Documents/         # Liste un répertoire spécifique
```

### 7.2 Obtenir de l'aide

#### **man** - Manuel
```bash
man ls                # Affiche le manuel de la commande ls
man cp                # Manuel de la commande cp
```
Navigation dans man :
- `Espace` : Page suivante
- `b` : Page précédente
- `/mot` : Rechercher "mot"
- `q` : Quitter

#### **--help** - Aide rapide
```bash
ls --help
cp --help
```

#### **apropos** - Rechercher une commande
```bash
apropos copy          # Trouve toutes les commandes liées à "copy"
```

### 7.3 Afficher du contenu

#### **cat** - Afficher le contenu d'un fichier
```bash
cat fichier.txt
cat fichier1.txt fichier2.txt    # Affiche plusieurs fichiers
```

#### **less** - Afficher avec pagination
```bash
less fichier.txt
```
Navigation :
- `Espace` : Page suivante
- `b` : Page précédente
- `q` : Quitter
- `/mot` : Rechercher

#### **head** - Afficher le début
```bash
head fichier.txt           # 10 premières lignes
head -n 5 fichier.txt      # 5 premières lignes
```

#### **tail** - Afficher la fin
```bash
tail fichier.txt           # 10 dernières lignes
tail -n 20 fichier.txt     # 20 dernières lignes
tail -f fichier.log        # Suit les modifications en temps réel
```

### 7.4 Informations système

#### **whoami** - Qui suis-je ?
```bash
whoami
# Résultat : utilisateur
```

#### **hostname** - Nom de la machine
```bash
hostname
# Résultat : mon-ordinateur
```

#### **date** - Date et heure
```bash
date
# Résultat : jeu. 30 janv. 2025 10:30:45 EAT
```

#### **uptime** - Temps depuis le dernier démarrage
```bash
uptime
# Résultat : 10:30:45 up 5 days, 2:15, 1 user
```

#### **df** - Espace disque
```bash
df -h                  # Format lisible
# Montre l'espace utilisé et disponible
```

#### **du** - Taille des fichiers/répertoires
```bash
du -sh Documents/      # Taille totale du répertoire
du -sh *               # Taille de chaque élément
```

#### **free** - Mémoire RAM
```bash
free -h                # Format lisible
```

---

## 8. Gestion des fichiers et répertoires

### 8.1 Créer

#### **touch** - Créer un fichier vide
```bash
touch fichier.txt
touch fichier1.txt fichier2.txt fichier3.txt    # Plusieurs fichiers
```

#### **mkdir** - Créer un répertoire
```bash
mkdir nouveau_dossier
mkdir -p parent/enfant/petit-enfant    # Crée toute l'arborescence
mkdir dossier1 dossier2 dossier3       # Plusieurs répertoires
```

### 8.2 Copier

#### **cp** - Copier fichiers/répertoires
```bash
cp source.txt destination.txt                    # Copie simple
cp fichier.txt /home/utilisateur/Documents/      # Copie vers un répertoire
cp -r dossier/ nouveau_dossier/                  # Copie récursive (répertoires)
cp -i fichier.txt destination.txt                # Mode interactif (demande confirmation)
cp -v fichier.txt destination.txt                # Mode verbeux (affiche les actions)
```

### 8.3 Déplacer/Renommer

#### **mv** - Déplacer ou renommer
```bash
mv ancien.txt nouveau.txt                        # Renommer
mv fichier.txt /home/utilisateur/Documents/      # Déplacer
mv fichier1.txt fichier2.txt dossier/            # Déplacer plusieurs fichiers
mv -i source.txt destination.txt                 # Mode interactif
```

### 8.4 Supprimer

#### **rm** - Supprimer fichiers
```bash
rm fichier.txt                    # Supprimer un fichier
rm fichier1.txt fichier2.txt      # Supprimer plusieurs fichiers
rm -i fichier.txt                 # Mode interactif
rm -r dossier/                    # Supprimer un répertoire et son contenu
rm -rf dossier/                   # Force sans confirmation (DANGEREUX!)
```

⚠️ **ATTENTION** : `rm -rf` est irréversible ! Pas de corbeille.

#### **rmdir** - Supprimer répertoire vide
```bash
rmdir dossier_vide/
```

### 8.5 Rechercher

#### **find** - Rechercher fichiers/répertoires
```bash
find /home -name "*.txt"                    # Tous les .txt dans /home
find . -name "fichier.txt"                  # Cherche fichier.txt ici
find /home -type f -name "*.pdf"            # Seulement les fichiers PDF
find /home -type d -name "Documents"        # Seulement les répertoires
find . -mtime -7                            # Modifiés dans les 7 derniers jours
find . -size +10M                           # Fichiers > 10 MB
```

#### **locate** - Recherche rapide (base de données)
```bash
locate fichier.txt
sudo updatedb           # Mettre à jour la base de données
```

#### **grep** - Rechercher du texte dans des fichiers
```bash
grep "mot" fichier.txt                      # Cherche "mot" dans fichier.txt
grep -r "mot" /home                         # Recherche récursive
grep -i "mot" fichier.txt                   # Insensible à la casse
grep -n "mot" fichier.txt                   # Affiche les numéros de ligne
grep -v "mot" fichier.txt                   # Lignes qui ne contiennent PAS "mot"
```

### 8.6 Wildcards (caractères génériques)

```bash
*           # N'importe quelle chaîne
?           # Un seul caractère
[abc]       # Un parmi a, b, ou c
[a-z]       # N'importe quelle lettre minuscule
[0-9]       # N'importe quel chiffre
```

**Exemples** :
```bash
ls *.txt                # Tous les fichiers .txt
ls fichier?.txt         # fichier1.txt, fichier2.txt, etc.
ls [aA]*.txt           # Commence par a ou A
rm temp*               # Supprime tous les fichiers commençant par "temp"
```

---

## 9. Permissions et droits d'accès

### 9.1 Concept des permissions

Linux est un système multiutilisateur. Chaque fichier a :
- Un **propriétaire** (owner)
- Un **groupe** (group)
- Des **permissions** pour le propriétaire, le groupe, et les autres

### 9.2 Afficher les permissions

```bash
ls -l fichier.txt
```

Résultat :
```
-rw-r--r-- 1 utilisateur groupe 1024 Jan 30 10:00 fichier.txt
```

Décortiquons :
```
- rw- r-- r--
│ │   │   │
│ │   │   └─ Permissions pour les autres (others)
│ │   └───── Permissions pour le groupe
│ └───────── Permissions pour le propriétaire
└─────────── Type (- = fichier, d = répertoire, l = lien)
```

### 9.3 Types de permissions

- **r** (read) = 4 : Lecture
- **w** (write) = 2 : Écriture
- **x** (execute) = 1 : Exécution

**Pour un fichier** :
- `r` : Lire le contenu
- `w` : Modifier le contenu
- `x` : Exécuter le fichier

**Pour un répertoire** :
- `r` : Lister le contenu
- `w` : Créer/supprimer des fichiers dedans
- `x` : Entrer dans le répertoire

### 9.4 Notation octale

```
rwx = 4+2+1 = 7
rw- = 4+2+0 = 6
r-x = 4+0+1 = 5
r-- = 4+0+0 = 4
-wx = 0+2+1 = 3
-w- = 0+2+0 = 2
--x = 0+0+1 = 1
--- = 0+0+0 = 0
```

**Exemples courants** :
- `755` = `rwxr-xr-x` : Propriétaire tout, autres lecture/exécution
- `644` = `rw-r--r--` : Propriétaire lecture/écriture, autres lecture
- `700` = `rwx------` : Seul le propriétaire a accès
- `777` = `rwxrwxrwx` : Tous les droits pour tous (DANGEREUX!)

### 9.5 Modifier les permissions

#### **chmod** - Change permissions
```bash
chmod 755 script.sh                    # Notation octale
chmod u+x script.sh                    # Ajoute exécution pour user
chmod g-w fichier.txt                  # Retire écriture pour group
chmod o+r fichier.txt                  # Ajoute lecture pour others
chmod a+x script.sh                    # Ajoute exécution pour all
chmod -R 755 dossier/                  # Récursif sur tout le répertoire
```

Lettres :
- `u` : user (propriétaire)
- `g` : group (groupe)
- `o` : others (autres)
- `a` : all (tous)

Opérateurs :
- `+` : Ajouter
- `-` : Retirer
- `=` : Définir exactement

### 9.6 Changer le propriétaire

#### **chown** - Change owner
```bash
sudo chown utilisateur fichier.txt                # Change le propriétaire
sudo chown utilisateur:groupe fichier.txt         # Change propriétaire et groupe
sudo chown -R utilisateur:groupe dossier/         # Récursif
```

#### **chgrp** - Change group
```bash
sudo chgrp groupe fichier.txt
sudo chgrp -R groupe dossier/
```

---

## 10. Gestion des utilisateurs

### 10.1 Informations utilisateur

```bash
whoami                    # Mon nom d'utilisateur
id                        # Informations complètes (UID, GID, groupes)
groups                    # Mes groupes
users                     # Utilisateurs connectés
who                       # Qui est connecté ?
w                         # Qui fait quoi ?
```

### 10.2 Sudo - Privilèges administrateur

`sudo` (SuperUser DO) permet d'exécuter des commandes avec les droits root.

```bash
sudo apt update                    # Mettre à jour les paquets
sudo apt install firefox           # Installer un logiciel
sudo systemctl restart apache2     # Redémarrer un service
```

**Première utilisation** :
- Demande votre mot de passe
- Mémorise pendant 15 minutes
- Soyez prudent : vous avez tous les pouvoirs !

### 10.3 Créer/Supprimer des utilisateurs

#### Créer un utilisateur
```bash
sudo adduser nouvel_utilisateur
# Suivez les instructions
```

#### Supprimer un utilisateur
```bash
sudo deluser utilisateur                    # Garde le répertoire personnel
sudo deluser --remove-home utilisateur      # Supprime tout
```

### 10.4 Changer de mot de passe

```bash
passwd                             # Change votre mot de passe
sudo passwd utilisateur            # Change le mot de passe d'un autre
```

---

## 11. Gestion des processus

### 11.1 Qu'est-ce qu'un processus ?

Un **processus** est un programme en cours d'exécution. Chaque processus a :
- Un **PID** (Process ID) : identifiant unique
- Un utilisateur propriétaire
- Une utilisation CPU et mémoire

### 11.2 Afficher les processus

#### **ps** - Process Status
```bash
ps                        # Vos processus dans ce terminal
ps -aux                   # Tous les processus de tous les utilisateurs
ps -ef                    # Format complet
ps -u utilisateur         # Processus d'un utilisateur spécifique
```

#### **top** - Surveillance en temps réel
```bash
top
```
Affiche en temps réel :
- Utilisation CPU
- Utilisation mémoire
- Processus actifs

Commandes dans top :
- `q` : Quitter
- `k` : Tuer un processus (demande le PID)
- `M` : Trier par mémoire
- `P` : Trier par CPU

#### **htop** - Version améliorée de top
```bash
sudo apt install htop    # Installation
htop                     # Lancement
```
Plus visuel et interactif que top.

### 11.3 Tuer des processus

#### **kill** - Envoyer un signal
```bash
kill PID                  # Signal TERM (termine proprement)
kill -9 PID               # Signal KILL (force brutal)
kill -15 PID              # Signal TERM (équivalent à kill)
```

#### **killall** - Tuer par nom
```bash
killall firefox           # Tue tous les processus firefox
killall -9 programme      # Force
```

#### **pkill** - Tuer par pattern
```bash
pkill firefox             # Tue les processus contenant "firefox"
```

### 11.4 Processus en arrière-plan

```bash
programme &               # Lance en arrière-plan
jobs                      # Liste les jobs en arrière-plan
fg                        # Ramène au premier plan
bg                        # Continue en arrière-plan
Ctrl+Z                    # Suspend le processus
Ctrl+C                    # Interrompt le processus
```

---

## 12. Installation de logiciels

### 12.1 Gestionnaires de paquets

#### Ubuntu/Debian : **APT**
```bash
sudo apt update                    # Met à jour la liste des paquets
sudo apt upgrade                   # Met à jour tous les paquets installés
sudo apt install firefox           # Installe un paquet
sudo apt remove firefox            # Désinstalle (garde les configs)
sudo apt purge firefox             # Désinstalle complètement
sudo apt autoremove                # Supprime les dépendances inutiles
sudo apt search firefox            # Recherche un paquet
sudo apt show firefox              # Infos sur un paquet
```

#### Fedora/RedHat : **DNF/YUM**
```bash
sudo dnf install firefox
sudo dnf remove firefox
sudo dnf update
```

#### Arch : **Pacman**
```bash
sudo pacman -S firefox
sudo pacman -R firefox
sudo pacman -Syu                   # Mise à jour complète
```

### 12.2 Snap packages
```bash
sudo snap install vlc
sudo snap list
sudo snap remove vlc
```

### 12.3 Flatpak
```bash
flatpak install flathub org.gimp.GIMP
flatpak list
flatpak uninstall org.gimp.GIMP
```

### 12.4 Installer depuis les sources

```bash
# 1. Télécharger l'archive
wget https://example.com/programme.tar.gz

# 2. Extraire
tar -xzvf programme.tar.gz

# 3. Entrer dans le répertoire
cd programme/

# 4. Compiler et installer
./configure
make
sudo make install
```

---

## 13. Commandes avancées utiles

### 13.1 Redirections et Pipes

#### Redirection de sortie
```bash
ls > liste.txt                     # Écrit dans fichier (écrase)
ls >> liste.txt                    # Ajoute à la fin du fichier
ls 2> erreurs.txt                  # Redirige les erreurs
ls > tout.txt 2>&1                 # Redirige tout
```

#### Pipes (|)
```bash
ls | grep ".txt"                   # Liste uniquement les .txt
ps aux | grep firefox              # Trouve les processus firefox
cat fichier.txt | wc -l            # Compte les lignes
history | grep "apt"               # Cherche dans l'historique
```

### 13.2 Historique des commandes

```bash
history                            # Affiche l'historique
!123                               # Exécute la commande #123
!!                                 # Exécute la dernière commande
!apt                               # Exécute la dernière commande apt
Ctrl+R                             # Recherche dans l'historique
```

### 13.3 Alias

Créer des raccourcis pour vos commandes :

```bash
alias ll='ls -la'
alias update='sudo apt update && sudo apt upgrade'
alias ..='cd ..'
```

Pour les rendre permanents, ajoutez-les dans `~/.bashrc` :
```bash
nano ~/.bashrc
# Ajoutez vos alias à la fin
source ~/.bashrc                   # Recharge la configuration
```

### 13.4 Archives et compression

#### **tar** - Créer/Extraire archives
```bash
# Créer une archive
tar -cvf archive.tar dossier/          # Archiver
tar -czvf archive.tar.gz dossier/      # Archiver + compresser (gzip)
tar -cjvf archive.tar.bz2 dossier/     # Archiver + compresser (bzip2)

# Extraire une archive
tar -xvf archive.tar                   # Extraire
tar -xzvf archive.tar.gz               # Extraire .tar.gz
tar -xjvf archive.tar.bz2              # Extraire .tar.bz2
tar -xvf archive.tar -C /destination   # Extraire vers un dossier spécifique

# Lister le contenu
tar -tvf archive.tar
```

Options :
- `c` : create (créer)
- `x` : extract (extraire)
- `v` : verbose (verbeux)
- `f` : file (fichier)
- `z` : gzip
- `j` : bzip2

#### **zip/unzip**
```bash
zip archive.zip fichier1 fichier2      # Créer zip
zip -r archive.zip dossier/            # Zip récursif
unzip archive.zip                      # Extraire
unzip -l archive.zip                   # Lister le contenu
```

### 13.5 Réseau

#### **ping** - Tester la connectivité
```bash
ping google.com                        # Teste la connexion
ping -c 4 google.com                   # 4 paquets seulement
```

#### **wget** - Télécharger
```bash
wget https://example.com/fichier.zip
wget -c https://example.com/gros.iso   # Continue le téléchargement
```

#### **curl** - Transfert de données
```bash
curl https://api.example.com
curl -O https://example.com/fichier.zip    # Télécharge
```

#### **ifconfig / ip** - Configuration réseau
```bash
ifconfig                               # Affiche les interfaces (ancien)
ip addr show                           # Affiche les interfaces (moderne)
ip route show                          # Affiche les routes
```

### 13.6 Monitoring système

#### **dmesg** - Messages du noyau
```bash
dmesg | less                           # Affiche les logs du kernel
dmesg | grep -i error                  # Cherche les erreurs
```

#### **journalctl** - Logs système
```bash
journalctl -xe                         # Dernières entrées avec explication
journalctl -f                          # Suit les logs en temps réel
journalctl -u ssh                      # Logs d'un service spécifique
```

#### **systemctl** - Gestion des services
```bash
sudo systemctl start apache2           # Démarre un service
sudo systemctl stop apache2            # Arrête un service
sudo systemctl restart apache2         # Redémarre un service
sudo systemctl status apache2          # État du service
sudo systemctl enable apache2          # Active au démarrage
sudo systemctl disable apache2         # Désactive au démarrage
```

---

## 14. Exercices pratiques

### Exercice 1 : Navigation et création
1. Ouvrez un terminal
2. Affichez votre répertoire courant
3. Allez dans votre répertoire personnel
4. Créez un dossier nommé "linux_exercices"
5. Entrez dans ce dossier
6. Créez trois fichiers : fichier1.txt, fichier2.txt, fichier3.txt
7. Listez le contenu pour vérifier

**Solution** :
```bash
pwd
cd ~
mkdir linux_exercices
cd linux_exercices
touch fichier1.txt fichier2.txt fichier3.txt
ls -l
```

### Exercice 2 : Manipulation de fichiers
1. Dans linux_exercices, créez un sous-dossier "archives"
2. Copiez fichier1.txt dans archives/
3. Renommez fichier2.txt en document.txt
4. Déplacez document.txt dans archives/
5. Supprimez fichier3.txt
6. Vérifiez le contenu de archives/

**Solution** :
```bash
mkdir archives
cp fichier1.txt archives/
mv fichier2.txt document.txt
mv document.txt archives/
rm fichier3.txt
ls -l archives/
```

### Exercice 3 : Contenu de fichiers
1. Créez un fichier info.txt
2. Écrivez "Bonjour Linux" dedans (utilisez echo et >)
3. Affichez son contenu avec cat
4. Ajoutez "Deuxième ligne" (utilisez echo et >>)
5. Affichez le contenu complet
6. Comptez le nombre de lignes (utilisez wc -l)

**Solution** :
```bash
touch info.txt
echo "Bonjour Linux" > info.txt
cat info.txt
echo "Deuxième ligne" >> info.txt
cat info.txt
wc -l info.txt
```

### Exercice 4 : Permissions
1. Créez un fichier script.sh
2. Écrivez dedans : `#!/bin/bash` puis `echo "Mon premier script"`
3. Essayez de l'exécuter avec `./script.sh`
4. Rendez-le exécutable
5. Exécutez-le à nouveau
6. Vérifiez ses permissions avec ls -l

**Solution** :
```bash
touch script.sh
echo "#!/bin/bash" > script.sh
echo "echo \"Mon premier script\"" >> script.sh
./script.sh                          # Erreur : permission denied
chmod +x script.sh                   # ou chmod 755 script.sh
./script.sh                          # Fonctionne !
ls -l script.sh
```

### Exercice 5 : Recherche
1. Créez plusieurs fichiers : test1.txt, test2.doc, document.txt, notes.txt
2. Trouvez tous les fichiers .txt dans le répertoire courant
3. Cherchez les fichiers contenant "test" dans leur nom
4. Créez un fichier avec du texte et cherchez un mot dedans

**Solution** :
```bash
touch test1.txt test2.doc document.txt notes.txt
find . -name "*.txt"
find . -name "*test*"
echo "Linux est un système d'exploitation" > texte.txt
grep "système" texte.txt
```

### Exercice 6 : Compression
1. Créez un dossier "projet" avec quelques fichiers dedans
2. Créez une archive tar.gz du dossier
3. Supprimez le dossier original
4. Extrayez l'archive
5. Vérifiez que les fichiers sont revenus

**Solution** :
```bash
mkdir projet
touch projet/fichier1.txt projet/fichier2.txt
tar -czvf projet.tar.gz projet/
rm -r projet/
tar -xzvf projet.tar.gz
ls -l projet/
```

### Exercice 7 : Processus et système
1. Affichez tous les processus en cours
2. Trouvez votre propre PID
3. Affichez l'espace disque disponible
4. Affichez la mémoire disponible
5. Affichez depuis combien de temps le système tourne

**Solution** :
```bash
ps aux
echo $$                              # Votre PID shell
df -h
free -h
uptime
```

### Exercice 8 : Challenge final
Créez une structure complète :
```
~/projet_final/
├── code/
│   ├── script1.sh (exécutable)
│   └── script2.sh (exécutable)
├── docs/
│   ├── readme.txt
│   └── manuel.txt
└── data/
    └── infos.txt
```

1. Créez toute cette structure
2. Mettez du contenu dans chaque fichier .txt
3. Rendez les scripts exécutables
4. Créez une archive de tout le projet
5. Déplacez l'archive dans ~/Desktop ou ~/Bureau

**Solution** :
```bash
cd ~
mkdir -p projet_final/{code,docs,data}
touch projet_final/code/{script1.sh,script2.sh}
touch projet_final/docs/{readme.txt,manuel.txt}
touch projet_final/data/infos.txt
echo "# Projet Final" > projet_final/docs/readme.txt
echo "echo 'Script 1'" > projet_final/code/script1.sh
echo "echo 'Script 2'" > projet_final/code/script2.sh
chmod +x projet_final/code/*.sh
tar -czvf projet_final.tar.gz projet_final/
mv projet_final.tar.gz ~/Desktop/  # ou ~/Bureau/
```

---

## Conclusion

### Ce que vous avez appris

✅ Les concepts de base de Linux
✅ Navigation dans le système de fichiers
✅ Gestion de fichiers et répertoires
✅ Permissions et droits d'accès
✅ Commandes essentielles du terminal
✅ Gestion des processus
✅ Installation de logiciels
✅ Commandes avancées

### Pour aller plus loin

1. **Shell scripting** : Automatisez vos tâches
2. **Administration système** : Services, réseau, sécurité
3. **Éditeurs de texte** : vim, emacs, nano
4. **Expressions régulières** : Recherches avancées
5. **Gestion de versions** : Git
6. **Conteneurisation** : Docker
7. **Serveurs** : Apache, Nginx, bases de données

### Ressources utiles

- **Documentation officielle** : https://ubuntu.com/server/docs
- **Linux Journey** : https://linuxjourney.com
- **Explain Shell** : https://explainshell.com (explique les commandes)
- **Forums** : Ask Ubuntu, LinuxQuestions.org
- **Man pages** : Votre meilleure ressource locale

### Conseils finaux

1. **Pratiquez régulièrement** : La ligne de commande s'apprend par la pratique
2. **Lisez les man pages** : Elles contiennent tout ce dont vous avez besoin
3. **N'ayez pas peur d'expérimenter** : Les machines virtuelles sont idéales pour cela
4. **Posez des questions** : La communauté Linux est très accueillante
5. **Gardez un système de backup** : Avant de faire des modifications importantes
6. **Utilisez sudo avec précaution** : Vous avez tous les pouvoirs !

---

## Glossaire

- **CLI** : Command Line Interface (Interface en ligne de commande)
- **GUI** : Graphical User Interface (Interface graphique)
- **Root** : Superutilisateur avec tous les privilèges
- **Shell** : Interpréteur de commandes (bash, zsh, etc.)
- **Kernel** : Noyau du système d'exploitation
- **Distribution** : Variante de Linux avec ses propres choix logiciels
- **Repository** : Dépôt de paquets logiciels
- **Package** : Paquet logiciel installable
- **PID** : Process ID (Identifiant de processus)
- **UID** : User ID (Identifiant utilisateur)
- **GID** : Group ID (Identifiant de groupe)

---

**Bonne chance dans votre apprentissage de Linux ! 🐧**