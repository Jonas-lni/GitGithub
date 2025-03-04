# GII ET GITHUB 
## I- Connecter un git à github avec le service ssh d'un serveur distant: 

Afin de pouvoir faire ce TP, il est nécessaire de créer un utilisateur ssh, en suivant les étapes suivantes :

**1- création d'un user ssh :**
	
		ssh root@ip-serveur
	
mot de passe qu'on trouve dans le site web de l'hébergeur (il est émis automatiquement après chaque réinitilaisation - réecriture d'image)
	
Génerer et copier les clés SSH avec les deux commandes suivantes: 
		
		ssh-keygen -t ed25519 (suivant suivant suivant)
	
les clés se trouvent dans les sous fichiers suivant ~/.ssh/id_rsa.pub et ~/.ssh/id_rsa
	
		ssh-copy-id username@IP-adress
		
**2- connecter le service ssh à Github :**
	
Nous devons d'abord récuperer la clé **id_rsa.pub** et la copier dans "paramétres -> **SSH and GPG key** -> _New SSH key_ -> _nomination, copier la clé puis Add SSH key_
	
Pour vérifier que vous avez correctement ajouté votre clé **SSH** à **GitHub**, ouvrez un terminal sur votre ordinateur et tapez la commande suivante **ssh -T git@github.com**
			
Si tout est configuré correctement, vous devriez voir un message comme celui-ci : **Hi your_username! You've successfully authenticated, but GitHub does not provide shell access**
	
Après avoir créer une répositorie dans Github, on saisit les commandes suivantes pour configurer un README.md : 

	echo "# kabylie" >> README.md
	
	git init
	
	git add README.md
	
	git commit -m "first commit"
	
	git branch -M main
	
	git remote add origin git@github.com:Jonas-lni/kabylie.git
	
	git push -u origin main
	
Lorsqu'on fait un commit : **git commit -m "first commit"**  ça ne marchera pas parceque depuis 2013 _l'authentification a été supprimée_ alors on poursuit les étapes suivantes sur la ligne de commande du serveur ssh bien sûr :
	
jonas@ubuntu:~/.git$ git commit -m "first message"
			
Author identity unknown

 Please tell me who you are.

		Run

	git config --global user.email "you@example.com"
  			
	git config --global user.name "Your Name"

to set your account's default identity.
			
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'jonas@ubuntu.(none)')
			
	jonas@ubuntu:~/.git$ **git config --global jonas.ighm@gmail.com** (ça mparche sans erreur)
	
	jonas@ubuntu:~/.git$ **git config --global jonas-lni**  (une erreur est soulignée au-dessous)

       error: key does not contain a section: jonas-lni
	
	**git branch -M main** ( sans erreur)

jonas@ubuntu:~/.git$ **git remote add origin git@github.com:Jonas-lni/kabylie.git** (sans erreur)

	 **git push -u origin main**
	
	error: src refspec main does not match any

	error: failed to push some refs to 'github.com:Jonas-lni/kabylie.git'


## II- Installation de gh (GitHub CLI) sur Linux:
La commande **gh** fait référence à l'outil **GitHub CLI** (GitHub Command Line Interface), qui est un utilitaire en ligne de commande permettant d'interagir avec GitHub directement depuis le terminal. Elle offre un moyen de gérer vos dépôts GitHub, de créer des issues, de créer des pull requests et bien plus encore, sans avoir besoin de passer par l'interface web de GitHub.
Si vous n'avez pas encore installé gh sur votre machine Linux, voici comment procéder :
Pour les distributions basées sur Debian (comme Ubuntu) :
	
		sudo apt update
	
		sudo apt install gh
	
Se connecter à **GitHub** : Pour vous authentifier avec votre compte GitHub, vous pouvez utiliser :
	
		gh auth login 







			

 

