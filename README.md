# Git

## 1.2 Découvrir la plateforme

* La plateforme Github est un dépôt, elle permet d'avoir son projet accessible en ligne pour tous ceux qui participent au développement du projet ou pour tout le monde si le projet est open-source.

 ### commandes de git
 
 * _git init_ initialise un dossier pour faire du versioning avec git 
 *  _git status_ permet de voir l'état du dossier actuel, les changements effectués et s'ils ont été mis en staging
 *  _git add nom_du_fichier_ ajoute un fichier au staging pour qu'il puisse être commit
 *  _git commit -m "message du commit"_ validation du changement avec un message décrivant le changement effectué
 *  _git diff_ permet de visualiser les changements effectués par rapport au dernier commit
 *  _git config --global user.username_ pour définir son nom d'utilisateur pour git
 *  _git clone url_ pour cloner un repo distant en local
 *  _git checkout_ pour naviguer à travers les versions ou les branches
 *  _git remote_ pour voir la liste des serveurs distants ou en ajouter un
 *  _git log_ voir l'historique des commits
 *  _git pull "remote" "branch"_ pour récupérer les commits depuis le repo distant
 *  _git push "remote" "branch"_ pour envoyer les commits jusqu'au repo distant
 *  _git revert HEAD_ fait un nouveau commit qui annule le commit précédent
 *  _git reset "commit" --hard_ Supprime l'historique jusqu'à un commit et modifie le dossier de travail en conséquence. /!\ à ne surtout pas utiliser pour revenir à un commit précédent le dernier pull. /!\ 

### Résolution de conflit

Si on veut push nos commits mais que le repo distant à eu des commits d'autres personnes entre temps, l'opération va échouer.
On va devoir pull la dernière version du repo et si des changements ont eu lieu au même endroit sur le repo distant et en local, il va y avoir un conflit à résoudre.
La première façon de résoudre le conflit est le merge, qui va créer un commit de merge en plus de notre commit qui a créer le conflit.
La deuxième façon est de faire un rebase, qui va placer notre dernier commit en Head et qui va comprendre la résolution du conflit, ne créant pas de commit supplémentaire.
Dans les deux cas, on résout le conflit en modifiant manuellement le ou les fichiers à l'origine du conflit.
La différence sera visible dans l'historique des commits, le rebase ne gardant aucune trace de cette différence de commits.
