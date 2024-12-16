# Résolution de conflit entre git et Github  : 

## Résumé des étapes clés :
1.	**_git fetch origin_** : Récupère les dernières modifications de GitHub sans les appliquer.

2.	**_git merge origin/<nom_de_votre_branche>_** : Fusionne les modifications de GitHub avec votre branche locale.

3.	Résoudre manuellement les conflits dans les fichiers concernés. Ouvrir **_nano <fichier.md>_** puis apporter les modifications -> suppression des conflits

4.	**_git add <nom_du_fichier_conflit>_** : Ajoutez les fichiers modifiés.

5.	**_git commit -m "message"_** : Validez la résolution du conflit.

6.	**_git push origin <nom_de_votre_branche>_** : Poussez les modifications résolues sur GitHub.

7.	**git pull --rebase origin main** : pour la récupération des changements distant et placer ses propres changements localement après le changement distant

8.	**git rebase --continue** : réorganisation des commits et intégration des modifications d'une autre branche 

ok 
