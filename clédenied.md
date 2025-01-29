git@github.com : Permission refusée (clé publique). fatal : Impossible de lire depuis le dépôt distant. Veuillez vous assurer que vous disposez des droits d'accès appropriés et que le dépôt existe.
Le message d'erreur Permission denied (publickey)indique que la clé SSH utilisée pour se connecter à GitHub n'est pas reconnue ou n'est pas correctement configurée. Voici les étapes à suivre pour résoudre ce problème :

1- Vérifiez si vous avez une clé SSH :

- Tout d’abord, vérifiez si vous disposez déjà d’une clé SSH en exécutant la commande suivante dans votre terminal :

	ls -al ~/.ssh

Recherchez les fichiers nommés **id_rsaet id_rsa.pub** (ou similaires). S'ils existent, vous disposez déjà d'une clé SSH.

2- Générer une nouvelle clé SSH (si nécessaire) :

- Si vous n'avez pas de clé SSH, générez-en une à l'aide de la commande suivante :

	ssh-keygen -t ed25519 -C "your_email@example.com"

- Suivez les instructions pour enregistrer la clé à l’emplacement par défaut et définir une phrase secrète (facultatif).

3- Ajoutez votre clé SSH à l'agent SSH :

- Démarrez l’agent SSH en arrière-plan :

	eval "$(ssh-agent -s)"

- Ajoutez votre clé SSH à l’agent :

	ssh-add ~/.ssh/id_ed25519

4- Ajoutez votre clé SSH à votre compte GitHub :

- Copiez la clé SSH dans votre presse-papiers :

	cat ~/.ssh/id_ed25519.pub

- Accédez aux **paramètres des clés SSH et GPG de GitHub** et cliquez sur « Nouvelle clé SSH ».

- Collez la clé SSH dans le champ « Clé » et donnez-lui un titre descriptif.

- Cliquez sur « Ajouter une clé SSH ».

5- Testez votre connexion SSH à GitHub :

- Exécutez la commande suivante pour tester votre connexion SSH :

	ssh -T git@github.com

- Vous devriez voir un message de réussite tel que « Bonjour ! Vous vous êtes authentifié avec succès, mais GitHub ne fournit pas d'accès au shell. »

6- Vérifiez votre URL distante :

- Assurez-vous que l'URL distante de votre référentiel utilise le format SSH. Vous pouvez le vérifier avec :

	git remote -v

- Si l'URL distante n'utilise pas SSH, vous pouvez la définir avec :



	git remote set-url origin git@github.com:<username>/<repository>.git

En suivant ces étapes, Permission denied (publickey)vous devriez résoudre le problème et pouvoir transférer les fichiers vers votre référentiel.
