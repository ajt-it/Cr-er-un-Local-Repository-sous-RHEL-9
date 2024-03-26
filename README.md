Dans un scénario où un serveur Red Hat est hors ligne, laissant les utilisateurs et les machines clientes sans accès aux dépôts nécessaires, une solution pratique consiste à mettre en place un dépôt HTTP Red Hat local. Cela permet aux administrateurs système Linux de maintenir les opérations même dans des environnements isolés.

Dans cet article, nous explorerons étape par étape la procédure pour configurer un serveur de dépôt local HTTP Red Hat à partir d'une image ISO installée sur un serveur. Cette compétence essentielle contribuera à assurer la continuité des opérations.

A. Configuration du serveur

Étape I: Configuration du serveur de dépôt local

![1](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/0ceae4f6-3aac-4ac3-902b-604a09af9131)

![2 - a](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/8d96ebf6-2466-4e7c-aa19-8de6be4178f3)


Étape II

a- Création du dossier "rhl9-repo" dans "/mnt" sur le serveur

b- Montage de l'ISO

c- Rendre le montage permanent

![3 -a](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/8112a858-ff93-47dd-be2f-0559005ddf8b)

![4 - a](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/cea8f569-8f9d-45fc-b745-0c1f508ef5e6)


Étape III

a- Création du fichier de configuration du dépôt local dans "/etc/yum.repos.d/rhl9.repo"

Attribution de la permission 644 au fichier "rhl9.repo"

Configuration comme suit :

![4 - b](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/a3d24c0d-58f5-4d94-a499-c55236c6d8a9)

![4 - c](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/72225561-e613-4f56-bcbe-8e42f9deb897)


b- Exécution des commandes suivantes : "dnf clean all" ; "dnf repolist" ; "subscription-manager clean"

![5](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/1145cab8-7fc9-4291-9dea-1f57c864df2e)


c- Test de la fonctionnalité du dépôt et installation du serveur "http"

![6](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/e219f0cc-7e88-4cbe-b8ad-1198e009d0a6)

![7](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/6b104d62-67dd-4349-9ae7-b737b23683d5)


Étape IV

a- Une fois le serveur HTTP installé, démarrer et activer le démarrage automatique du service au démarrage.
b- Vérification de l'état

![8](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/bf11b47c-acd6-44f6-bc88-d139cc0f058c)


Étape V

a- Installation des packages requis pour créer, configurer et gérer le dépôt local

![9](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/02891e7c-d2fb-4ecd-a38f-a71b8e0474f8)

![10](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/8581d073-d7e8-4b7e-bd4d-40186d73fc47)

![11](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/4b113440-8ccf-4f03-bb70-71915ad35cf3)

![12](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/7b2b1ac1-1030-4b38-a934-042a219b8d58)

![14](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/e4252e02-8b48-4e4c-a5c2-d81146b7e888)


b- Création du dossier "/var/www/html/rhl9-repo/rhl9-repo/" & copie du contenu du dossier "/mnt/rhl9-repo/" dans "/var/wwww/html/rhl9-repo/"

![13](https://github.com/ajt-it/Creer-un-Local-Repository-Server-sous-RHEL-9/assets/46109209/07452fa1-2e10-46ea-89d3-e85ecbe566e3)


c- Comparaison du contenu des dossiers "/mnt/rhl9-repo/" et "/var/wwww/html/rhl9-repo/"

Image 14-a

B. Configuration du client
