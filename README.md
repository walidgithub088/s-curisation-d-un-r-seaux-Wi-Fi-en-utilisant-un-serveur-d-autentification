L'objectif de ce projet est de mettre en œuvre et de déployer un système d'authentification pour contrôler et sécuriser l'accès au WLAN.
Au lieu d'utiliser la même clé pré-partagée, qui n'est pas adaptée à un environnement d'entreprise, un système d'authentification gère le contrôle d'accès des utilisateurs en utilisant des comptes distincts.
Cela remplace les clés réseau facilement distribuées et non sécurisées.
De plus, les administrateurs de ce système ont plus de flexibilité, car ils peuvent facilement gérer l'accès au WLAN et révoquer l'accès si nécessaire.
La figure ci-dessous illustre l'architecture réseau à déployer.
Cette architecture se compose des nœuds principaux suivants :
1. Serveur Active Directory : Ce serveur est responsable de la création de comptes d'utilisateur, de groupes et de la gestion des ressources réseau

2. Serveur de stratégie réseau (NPS) ou serveur RADIUS : Ce serveur est utilisé pour configurer la politique d'accès sans fil et permettre aux utilisateurs WLAN de se connecter au réseau en utilisant leurs comptes Active Directory.

3. Serveur d'autorité de certification : Ce serveur est utilisé pour la création et la gestion des certificats nécessaires à EAP-TLS (PEAP) ou EAP-TTLS.

   ![image](https://github.com/walidgithub088/s-curisation-d-un-r-seaux-Wi-Fi-en-utilisant-un-serveur-d-autentification/assets/151946258/a6912123-a0c1-4b9d-93ee-3daddeb69e32)

1. Installer et configurer le serveur Active Directory. Créer votre nom de domaine et installer le service DNS.
2. Dans le contrôle de domaine (serveur Active Directory), créer plusieurs comptes d'utilisateur. Créer un groupe WIFI et ajouter quelques utilisateurs à ce groupe.
3. Installer et déployer le serveur Radius ou NPS et l'intégrer en tant que membre de votre domaine. Créer la politique d'accès sans fil et sélectionner le protocole d'authentification nécessaire (EAP-TLS, EAP-TTLS). Appliquer cette politique au groupe WIFI.
4. Installer et déployer le serveur d'autorité de certification, créer les certificats nécessaires et les déployer.
5. Configurer le point d'accès en utilisant le mode entreprise WPA2.
6. À partir de la machine cliente, tester l'accès WIFI en utilisant deux comptes utilisateur différents : un appartenant au groupe WIFI et un n'appartenant pas au groupe WIFI.

Pour cela, on utilise trois VM de type Windows Server 2016, un point d'accès prenant en charge WPA2-Entreprise, et une VM Windows 10 pour tester la connectivité.
