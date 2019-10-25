# doc-eval

SPECIFICATIONS FONCTIONELLES 

 POUR LES  VISITEURS DU SITE, l'appli doit :


    • afficher la liste d’hotel selectionnable (ou accessible) au niveau du back (page d'accueil ou home)
    • afficher la liste d’hotel correspondant à une ville par le simple clic sur celle ci
    • afficher le pointer vers la catégorie ou produit survolée avec la souris (pour clic)
    • afficher la liste d’hotel d'une ville  cliqué
    • afficher sous chaque hotel des icones signifiant s'ils sont selectionnés, en promotion ou disponible
    • lorsqu'on clic sur une photo, afficher les informations détaillées sur l’hotel correspondant




POUR LES ADMINISTRATEURS DU SITE, l'appli permet :


    • considérant ici, qu'ils ont déjà un compte, il faut proposer un formulaire d'authentification (côté front uniquement)
    • une fois authentifié, il doit le rester tant qu'il ne se déconnecte pas (stockage dans le local storage)
    • de changer la photo d'un hotel par l'accès à l'explorateur de fichiers côté front :
        
    • l'admin peut acceder naturellement aux infos d'un hotel mais en plus, il peut les modifier, ce qui met à jour le back...
    • les photos des hotels seront stockés dans un dossier respectant ce chemin : "user.home" + /ecom/hotel
    • les photos des ville seront dans : "user.home" + /ecom/ville
    • vous ne devez pas accepter les photos de plus de 2.5MB (back)





    • considérant ici, qu'ils ont déjà un compte, il faut proposer un formulaire d'authentification (côté front uniquement) "la création d'un compte utilisateur inexistant pourra faire l'objet d'un 3ème sprint (à gérer en base côté back]"
    • une fois authentifié, il doit le rester tant qu'il ne se déconnecte pas (stockage dans le local storage)
    • permettre de créer reservation dans le local storage, composé d'un ou plusieurs hotel
    • afficher le contenu d'une reservation (id,liste des hotels, quantité, prix(qté*prix produit), combien reservation et combien de personne )
    • prévoir un bouton pour supprimer un ou plusieurs éléments de notre dans votre reservation
    • revenir à tout moment sur la liste des hotel pour ajouter dans la reservation en cours


SPECIFICATIONS TECHNIQUES / CONCEPTION
    • Spring au niveau du back (java 8, api Rest) 
    • Vous pourrez dans un premier temps utiliser une bdd virtuelle mais il faudra in fine utiliser un sgbd type mysql ou mariadb une fois arrivé à la phase commande. 
    • Comme à notre habitude, ne réinvontons pas la roue aussi utiliser Spring data pour gérer vos entités Jpa une fois crées puis spring data rest pour la gestion des web services associés 
    • De même, laisser de côté spring security que vous devrez naturellement gérer en fin de dev 
    • Angular 8 pour le front (bootstrap3, jquery) 
    • Intégration continue avec Git d'un workflow par équipe, 2 repos (back & front) 
    • Gestion des photos : elles ne seront pas stocké en base pour ne pas alourdir celle-ci, chaque produit aura un attribut qui pointe sur le fichier correspondant (chemin) 
    • Pour des raisons de sécurité, ne pas stocker les photos dans le rep static, l'accès sera définitivement verrouillé une fois spring security activé ! 
    • la gestion de l'authentification se fera côté front avec des données fictives locales (tableau avec noms des utilisateurs et leurs rôles : USER et(ou) ADMIN) "3ème Sprint : il faudra le gérer côté back" 
    • L'utilisateur ou token (user + roles) sera stocké en local storage afin de permettre la 			navigation sans déconnexion 
    • "3ème sprint : Mise en oeuvre d'https au niveau du back (changer application.properties, keytool...) 
    • "3ème sprint : JWT pour la phase d'authentification / utiliser keyclock" 
