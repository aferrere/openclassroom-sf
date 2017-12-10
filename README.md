openclassroom-sf
================
Symfony2 - Semaine 2 - Créer un CoreBundle

Retour au cours
Présentation

Bienvenue dans cet exercice qui sera corrigé par vos pairs !

Le but de l’exercice est de mettre en pratique toutes les compétences acquises jusque maintenant. Il doit vous permettre de bien les assimiler et de vous assurer de les maîtriser.

 
Le CoreBundle

Dans une application Symfony2, il est très courant de créer un CoreBundle (ou tout autre nom qui vous fait plaisir). 
Le rôle d’un tel bundle est de faire le lien entre tous les autres bundles utilisés, les vôtres comme ceux que vous avez pu télécharger grâce à Composer.

Prenons l’exemple de notre application, nous avons déjà un bundle de plateforme d’annonce ; imaginons qu’on y ajoute un bundle de forum, lieu d’échange entre les utilisateurs. 
Dans ce cas, où pouvons-nous mettre la page profil d’un utilisateur affichant à la fois le nombre de candidatures effectuées et le nombre de messages postés sur le forum ? 
Cette page ne peut pas être dans notre PlatformBundle car notre bundle ne connait rien du forum, impossible pour lui d’accéder au nombre de messages postés. 
La situation est la même depuis le ForumBundle, qui ne connait rien de nos annonces.

La solution est donc d’utiliser un CoreBundle qui vient faire la glue entre tous les autres bundles utilisés. Vous l’aurez compris, ce bundle n’est nullement réutilisable entre vos projets : 
c’est le seul qui est vraiment spécifique à votre application.

 
Votre mission
1. Créer le CoreBundle

Votre mission est donc dans un premier temps de créer ce CoreBundle. Vous pouvez utiliser la console ou alors le faire entièrement
à la main, les deux options sont possibles et je vous laisse le choix.

Dans un deuxième temps, vous devrez créer quelques éléments dans ce nouveau bundle.

 
2. Déplacer notre layout général

Vous l’aurez compris, notre CoreBundle étant la glue de notre site, il est assez logique d’y placer notre layout général.
Je vous invite donc à déplacer notre layout (app/Resources/views/layout.html.twig) dans le nouveau CoreBundle.

Bien entendu, n’oubliez pas d’adapter le code des autres vues afin de mettre à jour le nom de la vue qu’elles héritent.
Notre vue layout a changé de place, elle a donc changé de nom.

 
3. Créer la page d’accueil

En effet, je ne sais pas si vous vous en êtes rendu compte, mais pour l’instant notre site n’a pas de page d’accueil.
Essayez d’accéder à l’URL “/” et vous aurez une belle erreur 404. C’est parce que nous avons définit toutes nos pages en “/platform/…”.

Disons que le site que nous créons pourra contenir bien plus que l’aspect plateforme d’annonces.
La page d’accueil que vous devez créer n’affichera que les 3 dernières annonces.
A vous donc de créer la route, le contrôleur et la vue ; tout cela dans le nouveau CoreBundle.

 
4. Créer une page de contact

Notre site manque cruellement d’une page de contact. Malheureusement nous ne savons pas encore faire de formulaire,
il est donc impossible de faire une vraie page pour le moment. Pas d’inquiétude, vous devez créer une page de contact qui ajoute simplement un message flash du type
“La page de contact n’est pas encore disponible” et redirige vers la page d’accueil.

N’oubliez pas d’afficher ces messages flash sur la page d’accueil si ce n’est pas déjà le cas.

Exemple de message flash sur la page d’accueil

Exemple de message flash sur la page d’accueil

 
Fichiers à envoyer

Vous devez envoyer un fichier zip contenant les répertoires app, src et web ; ainsi que les fichiers composer.json et composer.lock qui se trouvent à la racine.

Faite attention à ne pas inclure le contenu des répertoires app/cache et app/logs dans le zip, car ceux-ci sont lourds et ne servent à rien dans notre cas :
vos correcteurs regénèreront le cache à la première exécution de votre code.

Surtout, n’incluez pas le répertoire vendor, car celui-ci peut faire près de 40Mo ! Il contient toutes vos dépendances, mais inutile de l’inclure
car grâce aux fichiers composer.json et composer.lock, vos correcteurs pourront télécharger automatiquement vos dépendances !

Vue des dossiers à exclure de votre fichier zip

Vue des dossiers à exclure de votre fichier .zip

 

Si vous avez des doutes sur comment compresser vos fichiers (c'est-à-dire, créer un dossier .zip), visionnez les vidéos indiquées dans la partie « Sélection du travail ».
