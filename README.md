# Partie 1 : collaboration sur un repository
Dans ce laboratoire, nous avons créer un repository dans lequel nous avons suivies les étapes du laboratoire gewstion de versions. nous avons décider de simuler ce laboratoire sur une seule machine expliquant pourquoi l'entièreté du laboratoire est fait par le meme compte (même compte mais deux utilisateurs différent). Après avoir cloner le repository avec la commande ``` git clone ... ``` nous avons ajouté le Dossier_A et le fichier texte textA.txt. pour synchroniser nous avons fait les commandes suivantes ``` git add --a ``` ``` git commit -m "commentaire" ``` ```git push origin main```. Par la suite, on crée une branche avec ```git branch nom_de_la_branche``` L'autre membre doit cloner a son tour la branche avec la commande ```git clone --branch nom_de_la_branche``` crée un dossier et un fichier texte, modifie le texte de l'autre étudiant et synchronise avec les commandes ultérieures. L'autre membre vérifie les modifications et merge dans la branche principale avec ```git checkout main``` ```git merge nom_de_la_branche``` ```git push origin main```

# Partie 2 : situations problématiques
Cette partie est séparé en deux situations.
## Situation 1
Voici les étapes que nous avons suivies pour résoudre la situation\
1 - Le membre A crée un nouveau repository sur GitHub\
2 - Il ouvre un terminal de command dans le dossier du projet\
3 - Il fait les commandes suivantes:\
	```git init```\
	```git remote add MembreA https://github.com/repositoryname```\
4 - Il ajoute le membre B comme collaborateur au repository\
5 - En option, le membre B peut créé sa propre branche\
