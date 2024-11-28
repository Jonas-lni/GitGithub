# Résolution de conflit entre git et Github  : 

## Résumé des étapes clés :
1.	git fetch origin : Récupère les dernières modifications de GitHub sans les appliquer.

2.	git merge origin/<nom_de_votre_branche> : Fusionne les modifications de GitHub avec votre branche locale.

3.	Résoudre manuellement les conflits dans les fichiers concernés.

4.	git add <nom_du_fichier_conflit> : Ajoutez les fichiers modifiés.

5.	git commit : Validez la résolution du conflit.

6.	git push origin <nom_de_votre_branche> : Poussez les modifications résolues sur GitHub.

