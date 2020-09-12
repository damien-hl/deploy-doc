# Upload de l'application

## Compilation du projet Angular

Ouvrez un terminal et rendez-vous dans votre dossier de projet Angular (Figure 1)

![Dossier du projet Angular](./angular_dir.jpg)
*Figure 1 : Dossier du projet Angular*

Compilez votre projet pour la production avec la commande
``` bash
ng build --prod
``` 

Par défaut Angular va compiler votre projet dans `/dist/<nom_du_projet>` (Figure 2)

![Contenu du projet compilé](./angular_dist.jpg)
*Figure 2 : Contenu du projet compilé*

Ce sont ces fichiers que vous allez envoyer sur votre serveur

## Compilation du projet Spring Boot

*À venir*

## Envoi des fichiers

Vous disposez de 2 choix pour envoyer vos fichiers, soit via un client SFTP disposant d'une interface graphique comme FileZilla ou bien en ligne de commande avec SCP.

### Avec FileZilla - interface graphique

Commencez par vous connecter à votre serveur, pour cela dans FileZilla, allez dans `File > Site Manager`, cliquez sur `New Site` et donnez-lui un nom.

Entrez les identifiants de connexion au serveur, si vous vous connectez au serveur par mot de passe, choisissez `Logon Type > Normal` (Figure 3)

![Connexion par mot de passe](./filezilla_password.jpg)
*Figure 3 : Connexion par mot de passe*

En revanche, si vous vous connectez au serveur avec votre clé SSH, choisissez `Logon Type > Key file` et choisissez votre clé privée `id_rsa`. (Figure 4)
Vous aurez peut-être besoin de passer le filtres des extensions à `All files` pour voir le fichier.

![Connexion par SSH](./filezilla_ssh_key.jpg)
*Figure 4 : SSH*

Si tout se passe bien, FileZilla vous demandera si vous souhaitez ajouter la clé du serveur à la liste des hôtes connus, cliquez sur `yes`.

### Avec SCP - en ligne de commande

*À venir*
