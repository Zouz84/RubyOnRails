# RUBY ON RAILS !


Si vous avez toujours voulu tout savoir sur Ruby On Rails, passez votre chemin, il existe de biens meilleurs README ailleurs, [ici](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) par exemple.
Si vous vous en tamponnez le coquillard, alors voici quelques termes à connaître.

## Site statique ou dynamique ? 
Un *site statique* est composé de pages fixes, qui ne changeront pas quelque soit l'utilisateur. Un site dynamique sera présenté de façon différente selon l'interaction avec le visiteur. Les informations présentées ne sont pas les mêmes selon les requêtes de l'internaute. Par exemple twitter / facebook sont des sites dynamiques car leur contenu change (nouveaux tweets, commentaires, like...) alors qu'un site de restaurant qui présente juste l'adresse, le menu, des photos du restau est un site statique. Dès qu'il y a un compte utilisateur, possibilité de commenter, ou de poster des choses par exemple, c'est un site dynamique.

## Most Valuable Controller (MVC) :basketball:

*Model View Controller* : C'est un modèle utilisé par Rails ou par d'autres languages comme PHP pour montrer une application web. On peut l'expliquer grâce à une image. Voici le chemin de la requête : l'utilisateur va sur le site, en fonction de ce qu'il demande au site, comment il se connecte dessus, le site va aller sur le routeur et va demander une fonction, une méthode du controlleur. Le controlleur reconnait la méthode, demande au modèle les informations nécessaire dans la database. Le model renvoit ces informations au controlleur, qui fait le lien avec la view, c'est à dire que le controlleur envoit les informations récupérer à la view, qui va construire la page, la mettre en forme (en HTML et ruby, avec ces informations et renvoyer ce message au controlleur, qui renvoit ça sur le site et à l'utilisateur.

![alt text](https://github.com/Nymze/Ruby_on_Rails/blob/master/MVC.png "MVC 1")

## Chacun sa route
> Sur ma route, oui, il y a eu du move, oui... 

Les routes permettent d’interpréter les URL et d’orienter vers les bonnes actions des controlleurs. La configuration se trouve dans le fichier config/routes.rb.
En quelques mots, l'utilisateur qui se balade sur votre site envoie des requêtes qui sont adressées au controlleur. Ce derneir a besoin de savoir quelle methode utiliser. Le *routeur* va donc regarder le verbe HTTP utilisé (Get, Post, Put ou delete) aini que l'URL demandé, et va le croiser avec la bonne action à effectuer par le controlleur.

La configuration d'une route se présente comme suit:
'resources :photos'
Biensûr il est possible de déclarer plusieurs routes en même temps:
'resources :photos, :books, :videos'



## La base de donnée

la base de données, dans laquelle le model va chercher et trier les données qui l'intéresse pour le renvoyer au controlleur (dans le schéma MVC). Contient tout un tas d'informations. Par exemple tous les comptes linkedins des moussaillons qui s'inscrivent à The Hacking Project (whaaat t'as jamais entendu parler de THP? Leur méthode va t'impressionner, va vite voir ce qu'il s'y passe en suivant ce [lien](https://www.thehackingproject.org/modalites).)

## GET/POST

*get*: pour les moins bilingues d'entre nous: "Obtenir".
*Post*: qu'on peut comprendre comme "puts" ou plus simplement "poster".
Si l'on veut accéder à toutes les photos, par exemples, le controlleur va renvoyer la liste de tous les articles grâce à la méthode get. Des fois il va remplir un formulaire (par ex nouvel utilisateur, nom, email ect) le formulaire va envoyer un truc et ça c'est *post*, quand tu soumets le formulaire, c'est une autre méthode dans ton controller, tu vas lui dire, attention là on est en train de poster un truc.

## Le concept de migration
Ce qu'on appelle "migration" sur ruby on rails permet de modifier la structure de la base de données. C'est à dire ajouter, supprimer ou modifier une table ou une colonne. Lorsque l'on souhaite modifier le nom d'une colonne par exemple, il faut effectuer une migration pour l'enregistrer.Mais Rails nous permet d'effectuer cette migration facilement. Sans cela il faudrait se taper tout le SQL à la main, ce qui est compliqué, surtout quand on ne sait pas ce qu'est le SQL... Malin.


## Les relations entre les models et les BDD
les modèles font le lien entre la base de données et le controlleur, donc notre application au final. Ils permettent de selectionner dans la base de données les informations qui nous intéressent pour les transmettre au controlleur et les mettre en forme dans la view, donc les mettre en forme sur le front-end.

## CRUD
Create, read, update, destroy = Ce n'est pas la définition du street art, mais comment faire pour intéragir de manière simple avec notre base de donnée par le biais du front-end parce qu'avec la console c'est super mais c'est pas comme ça que les users vont l'utiliser, c'est via notre site. 
Pour avoir son CRUD : resources :articles sur le controller puis rails routes sur la commande et on a le CRUD complet sur le model Articles

