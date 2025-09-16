Laboratoire 1 - Gestion de version\
16 septembre 2025\
Par Jérémy Ouellet et Simon-Olivier Bolduc\
Remis à M. Mickaël Brassard

# Partie 1 : collaboration sur un repository
Dans ce laboratoire, nous avons créé un repository dans lequel nous avons suivies les étapes du laboratoire gewstion de versions. nous avons décider de simuler ce laboratoire sur une seule machine expliquant pourquoi l'entièreté du laboratoire est fait par le même compte (même compte mais deux utilisateurs différent). Après avoir cloner le repository avec la commande ``` git clone ... ``` nous avons ajouté le Dossier_A et le fichier texte textA.txt. pour synchroniser nous avons fait les commandes suivantes ``` git add --a ``` ``` git commit -m "commentaire" ``` ```git push origin main```. Par la suite, on crée une branche avec ```git branch nom_de_la_branche``` L'autre membre doit cloner a son tour la branche avec la commande ```git clone --branch nom_de_la_branche``` crée un dossier et un fichier texte, modifie le texte de l'autre étudiant et synchronise avec les commandes ultérieures. L'autre membre vérifie les modifications et merge dans la branche principale avec ```git checkout main``` ```git merge nom_de_la_branche``` ```git push origin main```

# Partie 2 : situations problématiques
Cette partie est séparée en deux situations.
## Situation 1
Voici les étapes que nous avons suivies pour résoudre la situation\
1 - Le membre A crée un nouveau repository sur GitHub\
2 - Il ouvre un terminal de command dans le dossier du projet\
3 - Il fait les commandes suivantes:\
	``` git init ````
	``` git remote add MembreA https://github.com/repositoryname ```
4 - Il ajoute le membre B comme collaborateur au repository\
5 - En option, le membre B peut créer sa propre branche\
## Situation 2
1 - Après les étapes 1 à 8 soit le commit de l'erreur du membre B, le membre A crée un issue pour signaler l'erreur injecté dans le commit du membre B\
2 -  L'issue créée doit contenir une description de l'erreur commise qui permet au membre B de localiser l'erreur. (Exemple: Nom du dossier en erreur, ligne de code erronée, etc)\
3 - Le membre B regarde le message et répond au issue en mentionnant le tag du commit problématique et le tag de la dernière version acceptable. Le tag est habituellement dans ce format: f38fa76\
4 - Avec l'information donnée par le membre B, le membre A utilise ensuite l'historique des commits de la branche principale pour revenir à la dernière version non-erronée\
5 - Pour cela, il fait les commandes suivantes:\
	``` git init ```
 	``` git reset --hard [tag du dernier bon commit] ```
6 - Le dossier local du membre A est ainsi revenu à la version non-erronée et le issue peut être taggé comme fermé\
7 - Comme dernier commentaire du issue, le membre A peut noter les changements non-erronés qui ont été supprimé par le reset du repo et qui doivent être refait\
8 - Le membre B peut maintenant refaire les changements dans son repo local et faire un commit\
9 - Une façon pour le membre B de synchroniser le tout avec le repo distant serait de créer une nouvelle branche et repartir de celle-ci pour le reste du projet. Il ferait donc les mêmes commandes qui ont été faites dans la Partie 1 du laboratoire
10 - Il existe une alternative à la commande git reset -hard qui consiste à refaire un commit qui est l'opposé du commit erroné. C'est le git revert. Il suffit de connaître le tag du commit problématique et de taper la commande ```git revert "tagCommit"``` et un nouveau commit sera créé annulant le commit erroné. Cela est particulièrement utile car il ne supprime pas les commits non-erronés qui ont suivis le commit problématique. 

## Git command Cheat Sheet
En résumé, voici les commandes git utilisées lors du laboratoire et/ou qui pourraient être utile dans le futur:
``` git init ``` Initialise un directory existant comme repo git.
``` git clone [url]``` Clone un repository distant en format local.
``` git add [file] ``` Ajoute un fichier au prochain commit.
``` git reset [file] ``` Annule la modification d'un fichier sans enelver les changements fonctionnels du directory.
``` git reset --hard [commit] ``` Annule toutes les modifications jusqu'au commit spécifié
``` git diff ``` Montre la différence dans ce qui a changé depuis le dernier commit.
``` git branch ``` Montre toutes les branches du repo actif.
``` git branch [branch name] ``` Crée une nouvelle branche au commit actif.
``` git checkout [branch name] ``` Change de branche active.
``` git merge [branch] ``` "Merge" la branche spécifiée avec la branche active.
``` git log ``` Montre tous les commits de la branche active.
``` git commit -m [commentaire] ``` Fait un commit en laissant un commentaire qui apparait dans l'historique. 
``` git push [alias] [branche]```  Transmet les commits de la branche active à la branche spécifiée du repo distant.
``` git pull ``` Récupère et "merge" les commits de la branche distante.


