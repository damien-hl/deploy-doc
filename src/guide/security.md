# Sécurité

## Sudo

Afin qu'il ait plus de pouvoir, ajoutons notre utilisateur au groupe `sudo`
``` bash
usermod -aG sudo <utilisateur>
```

## Configurer SSH

Par défaut SSH utilise le port 22, changeons ce port afin d'ajouter une fine couche de sécurité.
Ouvrez le fichier `/etc/ssh/sshd_config` avec nano par exemple :
``` bash
nano /etc/ssh/sshd_config
```
Décommentez et changez la ligne définissant le port à utiliser pour par exemple 1337, 5555 ou 1234
``` bash{6-7}
# The strategy used for options in the default sshd_config shipped with
# OpenSSH is to specify options with their default value where
# possible, but leave them commented.  Uncommented options override the
# default value.

- #Port 22
+ Port 1337
#AddressFamily any
#ListenAddress 0.0.0.0
#ListenAddress ::
```
Refusez la connexion à root en décommentant et en modifiant la ligne `PermitRootLogin`
``` bash{4-5}
# Authentication:

#LoginGraceTime 2m
- #PermitRootLogin prohibit-password
+ PermitRootLogin no
#StrictModes yes
#MaxAuthTries 6
#MaxSessions 10
```
Quittez et sauvegardez avec `CTRL + X`
Redémarrez le service SSH
``` bash
systemctl restart sshd
```
Vérifiez le statut du service (Figure 1)
``` bash
systemctl status sshd
```

![Statut du service SSH](./ssh-status.jpg)
*Figure 1: Statut du service SSH*

Vous pouvez à présent vous déconnectez du serveur et vous reconnectez avec le nouveau port
``` bash
ssh <utilisateur>@<IP_du_serveur> -p 1337
```
