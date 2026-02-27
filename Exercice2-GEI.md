# Exercice 2 — Recherche, processus et monitoring

## Objectif

Maîtriser :
grep, find, ps, top, kill, df, free, uname, history

---

## Partie A — Recherche

1. Créer un fichier notes.txt contenant 5 lignes dont le mot "Linux" apparaît 2 fois.

2. Rechercher le mot "Linux" avec :
grep

3. Afficher les lignes avec numéro :
grep -n

4. Rechercher tous les fichiers .txt dans le dossier courant avec :
find

---

## Partie B — Processus

1. Lancer une commande :
sleep 200 &

2. Vérifier les processus actifs avec :
ps aux | grep sleep

3. Identifier le PID.

4. Terminer le processus avec :
kill PID

---

## Partie C — Monitoring système

Exécuter les commandes suivantes :

df -h
free -m
uname -a
history | tail -n 5

Créer un fichier system_report.txt contenant les résultats.

---