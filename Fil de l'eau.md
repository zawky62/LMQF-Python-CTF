**Accessibilité Externe**

Erreur sur la liason entre apache et pyramid
résolu en modifiant le fichier /etc/apache2/sites-available/000-default.conf

_en rajoutant_

    ServerName example.com.com
    
    ProxyPreserveHost On
    ProxyPass / http://localhost:6543/
    ProxyPassReverse / http://localhost:6543/


Executant les commandes suivantes :

> sudo a2enmod proxy
> sudo a2enmod proxy_http


Et restart le service apache

Permettant donc finalement d'acceder au site en externe à pyramid via apache
Probleme phpmyadmin aucun accès a la BDD erreur de php assez long, tentative d'ajout de ligne de code du dossier phpmyadmin au fichier 000-default.conf

Erreur persistant

Finalement creation de BDD via mariadb et abandon de gestion de BDD via phpmyadmin


**Server down**

ERROR 503 :
> Resolution : Redemarrage Serveur
