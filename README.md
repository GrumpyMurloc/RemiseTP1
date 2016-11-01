<span style="text-align: justify">
# **Analyse GitHub**


## **Préparation:**
#### **Choix projet**:
J'ai recherché un problème pas trop difficile sachant que le but de l'exercice était d'apprendre GitHub. Jai donc utiliser des *labels* tels que *easy* et *language* pour filtrer les issues. J'ai réussit à sélectionner deux *issues*. Malheureusement, le premier projet demandait de rejoindre un groupe *Slack* sur invitationseulement pour pouvoir modifier le projet. J'ai donc décidé de prendre le second projet.

#### **Profil GitHub:**
Mon identifiant GitHub est *GrumpyMurloc*. Mon profil peut être consulté [ici](https://github.com/GrumpyMurloc)

#### **Environement de développement:**
Utilisation de VMware Workstation pour créer un machine virtuelle Ubuntu
	
# **SlackWolf**:
	
*SlackWorlf* est un bot pour *Slack* permettant aux utilisateurs de participer à une partie de loup-garou (mafia). Le projet est écrit en PHP. Il ne semble pas y avoir de convention on d'instruction provenant du gestionnaire de projet. Cependant, le projet est répartit en différents dossiers, séparant les différentes classes selon leur type par exemple: le dossier formatter contient la classe *formatter* ainsi que tous les classes dérivées. 

> Repository: https://github.com/chrisgillis/slackwolf

> Issue: https://github.com/chrisgillis/slackwolf/issues/51

> Status: Testing


#### **Problème:**
Il pleut tout le temps. Il y a eu un push ajoutant une commande fournissant à l'utilisateur une fonction lui permettant d'obtenir la température du jour. Cependant cette commande transmet seulement la même température. Pour obtenir l'information durant la partie, l'utilisateur reçoit une description du jour (GameControler (ligne 479, 497, 517)). Cette description n'utilise pas la commande *!weather*, mais elle retourne simplement un texte qui a été modifié par le créateur de la commande. Donc, le problème est que l'utilisateur reçoit toujours la même température peut importe le jour. Pour règler ce problème, j'ai créer une nouvelle classe static *WeatherFormatter* qui retourne un *String* selon l'état et la température contennu dans la partie. Pour obtenir la température, une fonction *setWeather* sera appellé au début de chaque journé. Cette fonction retournera un nombre aléatoire entre 1 et 3 inclusivement et ceci permettera de déterminer la température.Cette chaine pourra être intégré au message se retrouvant dans le game controleur.  


#### **Préparation de l'environement:**
###### **Installation de PHP7**

	sudo apt-get install python-software-properties software-properties-common
	sudo LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php
	sudo apt-get update
	sudo apt-get install php7.0 php7.0-fpm php7.0-mysql -y
	
###### **Installation de composer**
[Composer](https://github.com/composer/composer)  est un programme qui aide au niveau de l'installation, la gestion et la déclaration de dépendance pour les 	projet PHP. 

	//Télécharge l'installer dans le répertoire courant
	sudo php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
	// Vérifie l'installer SHA-384
	sudo php -r "if (hash_file('SHA384', 'composer-setup.php') === 'e115a8dc7871f15d853148a7fbac7da27d6c0030b848d9b3dc09e2a0388afed865e6a3d6b3c0fad45c48e2b5fc1196ae') { echo 'Installer 	verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
	// Executer l'installer
	sudo php composer-setup.php
	// Retirer l'installer
	sudo php -r "unlink('composer-setup.php');"

###### **Installation de slack**
	https://slack.com/downloads/linux

###### **Installation du programme**

	// Il est à noté que le programme pouvait être installé de deux façon.
	// Le programme Slack doit être installé 
	// J'ai décidé d'utiliser la méthode source du programme.
	git clone http://github.com/chrisgillis/slackwolf
	cd slackwolf
	composer install

###### **Configuration Slack**	
	renommer le fichier .env.default pour .env
	obtenir un [token](https://slack.com/signin?redir=%2Fservices%2Fnew%2Fbot) slack
</span>
