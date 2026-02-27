# TP — Commandes Linux (pratique + utilité + exemple)

Règles :
- Quand une commande nécessite des droits admin, elle est précédée de `sudo`.

---

## 1) Navigation et fichiers (1–20)

1. `pwd` : afficher le répertoire courant  
   Exemple : `pwd`

2. `ls` : lister le contenu d’un dossier  
   Exemple : `ls`

3. `ls -l` : liste détaillée (droits, taille, propriétaire)  
   Exemple : `ls -l`

4. `ls -a` : afficher fichiers cachés  
   Exemple : `ls -a`

5. `ls -la` : détails + cachés  
   Exemple : `ls -la`

6. `cd` : changer de répertoire  
   Exemple : `cd /etc`

7. `cd ..` : remonter d’un niveau  
   Exemple : `cd ..`

8. `cd ~` : aller au dossier home  
   Exemple : `cd ~`

9. `mkdir` : créer un dossier  
   Exemple : `mkdir tp-linux`

10. `mkdir -p` : créer une arborescence  
   Exemple : `mkdir -p projet/src/controllers`

11. `rmdir` : supprimer un dossier vide  
   Exemple : `rmdir dossier_vide`

12. `touch` : créer un fichier vide (ou mettre à jour la date)  
   Exemple : `touch notes.txt`

13. `cp` : copier un fichier  
   Exemple : `cp notes.txt notes_backup.txt`

14. `cp -r` : copier un dossier  
   Exemple : `cp -r projet projet_copy`

15. `mv` : déplacer ou renommer  
   Exemple : `mv notes.txt cours.txt`

16. `rm` : supprimer un fichier  
   Exemple : `rm cours.txt`

17. `rm -r` : supprimer un dossier et son contenu  
   Exemple : `rm -r projet_copy`

18. `cat` : afficher le contenu d’un fichier  
   Exemple : `cat /etc/hosts`

19. `less` : lire un fichier page par page (q pour quitter)  
   Exemple : `less /etc/services`

20. `head` : afficher les premières lignes  
   Exemple : `head -n 5 /etc/passwd`

21. `nano` : editter fichier 
   Exemple ! `nano notes.txt`

---

## 2) Lecture, tri, texte (21–40)

21. `tail` : afficher les dernières lignes  
   Exemple : `tail -n 5 /etc/passwd`

22. `wc` : compter lignes/mots/caractères  
   Exemple : `wc -l /etc/passwd`

23. `sort` : trier des lignes  
   Exemple : `sort noms.txt`

24. `uniq` : supprimer doublons (souvent après sort)  
   Exemple : `sort noms.txt | uniq`

25. `cut` : extraire des colonnes  
   Exemple : `cut -d: -f1 /etc/passwd`

26. `tr` : remplacer/supprimer caractères  
   Exemple : `echo "Linux" | tr 'a-z' 'A-Z'`

27. `grep` : rechercher un motif dans du texte  
   Exemple : `grep "root" /etc/passwd`

28. `grep -n` : afficher numéro de ligne  
   Exemple : `grep -n "root" /etc/passwd`

29. `grep -i` : recherche insensible à la casse  
   Exemple : `grep -i "RoOt" /etc/passwd`

30. `grep -r` : recherche récursive dans un dossier  
   Exemple : `grep -r "TODO" .`

31. `awk` : traitement texte par colonnes  
   Exemple : `awk -F: '{print $1,$3}' /etc/passwd`

32. `sed` : remplacer du texte en flux  
   Exemple : `echo "bonjour" | sed 's/bonjour/hello/'`

33. `paste` : fusionner fichiers colonne par colonne  
   Exemple : `paste col1.txt col2.txt`

34. `join` : joindre deux fichiers (clé commune)  
   Exemple : `join -1 1 -2 1 a.txt b.txt`

35. `nl` : afficher un fichier numéroté  
   Exemple : `nl -ba notes.txt`

36. `tee` : écrire dans un fichier tout en affichant à l’écran  
   Exemple : `ls -la | tee liste.txt`

37. `xargs` : transformer une sortie en arguments  
   Exemple : `echo "a b c" | xargs -n1 echo`

38. `printf` : afficher formaté  
   Exemple : `printf "Nom:%s Age:%d\n" "Ali" 20`

39. `echo` : afficher du texte  
   Exemple : `echo "Hello Linux"`

40. `date` : afficher date et heure  
   Exemple : `date`

---

## 3) Redirections et pipelines (41–55)

41. `>` : rediriger en écrasant  
   Exemple : `ls > fichiers.txt`

42. `>>` : rediriger en ajoutant  
   Exemple : `echo "Fin" >> fichiers.txt`

43. `<` : utiliser un fichier comme entrée  
   Exemple : `wc -l < fichiers.txt`

44. `2>` : rediriger les erreurs  
   Exemple : `ls /inexistant 2> erreurs.txt`

45. `&>` : rediriger sortie + erreurs  
   Exemple : `commande &> log.txt`

46. `|` : pipeline (sortie vers entrée)  
   Exemple : `ps aux | grep ssh`

47. `nohup` : lancer une commande qui survit à la déconnexion  
   Exemple : `nohup sleep 1000 &`

48. `time` : mesurer le temps d’exécution  
   Exemple : `time ls`

49. `yes` : générer du texte répétitif (attention)  
   Exemple : `yes "ok" | head -n 3`

50. `sleep` : pause  
   Exemple : `sleep 2`

51. `true` : commande qui réussit toujours  
   Exemple : `true`

52. `false` : commande qui échoue toujours  
   Exemple : `false`

53. `exit` : sortir du shell  
   Exemple : `exit`

54. `history` : afficher historique des commandes  
   Exemple : `history | tail -n 10`

55. `clear` : nettoyer l’écran  
   Exemple : `clear`

---

## 4) Recherche fichiers/dossiers (56–65)

56. `find` : rechercher des fichiers  
   Exemple : `find . -name "*.txt"`

57. `find -type f` : seulement fichiers  
   Exemple : `find . -type f -name "*.js"`

58. `find -mtime` : modifiés récemment  
   Exemple : `find . -mtime -1`

59. `locate` : rechercher via base d’index (si disponible)  
   Exemple : `locate hosts`

60. `which` : chemin d’une commande  
   Exemple : `which php`

61. `whereis` : infos commande (binaire, man)  
   Exemple : `whereis bash`

62. `file` : type d’un fichier  
   Exemple : `file /bin/ls`

63. `stat` : détails fichier (dates, taille, inode)  
   Exemple : `stat notes.txt`

64. `du` : taille d’un dossier/fichier  
   Exemple : `du -sh .`

65. `tree` : afficher arborescence (si installé)  
   Exemple : `tree -L 2 .`

---

## 5) Permissions et propriétés (66–75)

66. `chmod` : changer permissions  
   Exemple : `chmod 644 notes.txt`

67. `chmod +x` : rendre exécutable  
   Exemple : `chmod +x script.sh`

68. `chown` : changer propriétaire  
   Exemple : `sudo chown user:user notes.txt`

69. `chgrp` : changer groupe  
   Exemple : `sudo chgrp developers notes.txt`

70. `umask` : masque par défaut des permissions  
   Exemple : `umask`

71. `id` : afficher UID/GID et groupes  
   Exemple : `id`

72. `groups` : afficher groupes  
   Exemple : `groups`

73. `whoami` : utilisateur courant  
   Exemple : `whoami`

74. `who` : utilisateurs connectés  
   Exemple : `who`

75. `passwd` : changer mot de passe  
   Exemple : `passwd`

---

## 6) Processus et services (76–85)

76. `ps` : afficher processus  
   Exemple : `ps aux | head`

77. `top` : monitor en temps réel  
   Exemple : `top`

78. `htop` : top amélioré (si installé)  
   Exemple : `htop`

79. `kill` : terminer un processus par PID  
   Exemple : `kill 1234`

80. `killall` : tuer par nom  
   Exemple : `killall firefox`

81. `nice` : priorité au lancement  
   Exemple : `nice -n 10 sleep 100`

82. `renice` : changer priorité d’un PID  
   Exemple : `sudo renice -n 5 -p 1234`

83. `systemctl status` : statut d’un service  
   Exemple : `sudo systemctl status ssh`

84. `systemctl start` : démarrer un service  
   Exemple : `sudo systemctl start ssh`

85. `systemctl stop` : arrêter un service  
   Exemple : `sudo systemctl stop ssh`

---

## 7) Réseau (86–95)

86. `ip a` : interfaces réseau  
   Exemple : `ip a`

87. `ip r` : routes  
   Exemple : `ip r`

88. `ping` : tester connectivité  
   Exemple : `ping -c 4 8.8.8.8`

89. `curl` : requête HTTP (API, page web)  
   Exemple : `curl -I https://example.com`

90. `wget` : télécharger un fichier  
   Exemple : `wget https://example.com/index.html`

91. `ss` : ports et connexions (remplace netstat)  
   Exemple : `ss -tulpn | head`

92. `hostname` : nom machine  
   Exemple : `hostname`

93. `nslookup` : résoudre DNS (si dispo)  
   Exemple : `nslookup example.com`

94. `dig` : DNS avancé (si dispo)  
   Exemple : `dig example.com`

95. `traceroute` : chemin réseau (si installé)  
   Exemple : `traceroute 8.8.8.8`

---

## 8) Disque, système, paquets (96–100)

96. `df -h` : espace disque  
   Exemple : `df -h`

97. `free -m` : mémoire RAM  
   Exemple : `free -m`

98. `uname -a` : infos noyau/système  
   Exemple : `uname -a`

99. `apt update` : mettre à jour index paquets (Ubuntu/Debian)  
   Exemple : `sudo apt update`

100. `apt install` : installer paquet  
   Exemple : `sudo apt install tree`


# Commandes Linux essentielles pour le développement

---

## 1) Git (Contrôle de version)

101. `git init` : initialiser un dépôt Git  
Exemple :
git init

102. `git clone` : cloner un dépôt distant  
Exemple :
git clone https://github.com/user/projet.git

103. `git status` : voir l’état des fichiers  
Exemple :
git status

104. `git add` : ajouter fichiers au staging  
Exemple :
git add .

105. `git commit` : enregistrer les modifications  
Exemple :
git commit -m "Initial commit"

106. `git log` : historique des commits  
Exemple :
git log

107. `git branch` : voir les branches  
Exemple :
git branch

108. `git checkout` : changer de branche  
Exemple :
git checkout main

109. `git pull` : récupérer mises à jour  
Exemple :
git pull origin main

110. `git push` : envoyer vers dépôt distant  
Exemple :
git push origin main

---

## 2) Node.js / JavaScript

111. `node -v` : vérifier version Node  
Exemple :
node -v

112. `npm -v` : version npm  
Exemple :
npm -v

113. `npm init` : initialiser projet Node  
Exemple :
npm init -y

114. `npm install` : installer dépendances  
Exemple :
npm install

115. `npm install package` : installer paquet  
Exemple :
npm install express

116. `npm run` : exécuter script défini  
Exemple :
npm run dev

117. `npx` : exécuter paquet temporaire  
Exemple :
npx create-react-app app

---

## 3) PHP / Laravel

118. `php -v` : version PHP  
Exemple :
php -v

119. `php artisan serve` : lancer serveur Laravel  
Exemple :
php artisan serve

120. `php artisan migrate` : exécuter migrations  
Exemple :
php artisan migrate

121. `composer install` : installer dépendances PHP  
Exemple :
composer install

122. `composer update` : mettre à jour dépendances  
Exemple :
composer update

---

## 4) Docker

123. `docker --version` : version Docker  
Exemple :
docker --version

124. `docker ps` : conteneurs actifs  
Exemple :
docker ps

125. `docker ps -a` : tous les conteneurs  
Exemple :
docker ps -a

126. `docker images` : images disponibles  
Exemple :
docker images

127. `docker build` : construire une image  
Exemple :
docker build -t monapp .

128. `docker run` : lancer conteneur  
Exemple :
docker run -p 8080:80 monapp

129. `docker stop` : arrêter conteneur  
Exemple :
docker stop container_id

---

## 5) Logs et Debug

130. `tail -f` : suivre un log en temps réel  
Exemple :
tail -f storage/logs/laravel.log

131. `watch` : exécuter une commande en boucle  
Exemple :
watch -n 2 ls

132. `lsof` : voir fichiers ouverts (ports)  
Exemple :
lsof -i :8000

133. `strace` : tracer appels système  
Exemple :
strace ls

---

## 6) Environnement et variables

134. `env` : afficher variables d’environnement  
Exemple :
env

135. `export` : définir variable  
Exemple :
export APP_ENV=local

136. `printenv` : afficher variable  
Exemple :
printenv APP_ENV

---

## 7) Archives et sauvegardes

137. `tar -cvf` : créer archive  
Exemple :
tar -cvf backup.tar projet/

138. `tar -xvf` : extraire archive  
Exemple :
tar -xvf backup.tar

139. `zip` : compresser  
Exemple :
zip projet.zip fichier.txt

140. `unzip` : décompresser  
Exemple :
unzip projet.zip

---

## 8) Compilation et build

141. `gcc` : compiler programme C  
Exemple :
gcc main.c -o main

142. `make` : lancer compilation via Makefile  
Exemple :
make

143. `cmake` : générer configuration build  
Exemple :
cmake .

---

## 9) SSH et déploiement

144. `ssh` : connexion serveur distant  
Exemple :
ssh user@192.168.1.10

145. `scp` : copier fichier vers serveur  
Exemple :
scp fichier.txt user@server:/home/user/

146. `rsync` : synchroniser fichiers  
Exemple :
rsync -av projet/ user@server:/var/www/

---

## 10) Outils développeur divers

147. `code .` : ouvrir VS Code  
Exemple :
code .

148. `chmod +x script.sh` : rendre script exécutable  
Exemple :
chmod +x deploy.sh

149. `bash script.sh` : exécuter script  
Exemple :
bash deploy.sh

150. `alias` : créer raccourci commande  
Exemple :
alias ll='ls -la'