# Conception d'une architecture TCP/IP
Ce projet s'appuie sur le cours "Concevez votre réseau TCP/IP" proposé par la plateforme OpenClassrooms. Il a été entièrement réalisé à l'aide de l'application Cisco Packet Tracer (je ne peux pas encore expérimenter avec GNS3 pour le moment 🙂). Le projet se compose de deux réseaux indépendants qui communiquent entre eux via un routeur.  
## Le Réseau 1
Il est encadré par un rectangle mauve et représente une petite entreprise (<span style="color: green">**Entreprise 1**</span>). Ce réseau est composé d'un PC fixe, d'un ordinateur portable, d'un serveur et d'un switch, tous connectés entre eux par des câbles Ethernet. Le PC et l'ordinateur portable sont configurés manuellement pour les adresses IP et les passerelles par défaut.
## Le Réseau 2
Il est encadré par un rectangle vert et représente une entreprise de taille moyenne (<span style="color: green">**Entreprise 2**</span>), voisine de l'entreprise 1, avec laquelle elle communique via un routeur. Ce réseau comprend deux PC fixes, pour lesquels les adresses IP, les passerelles par défaut et le serveur DNS ont été configurés manuellement. Il y a également deux ordinateurs portables configurés en tant que clients DHCP et DNS, ainsi que deux serveurs. Tous les appareils sont connectés par un switch. Cette entreprise a la capacité de continuer à recruter de nouveaux employés.
## Les Serveurs de l'Entrepise 2 
- ### Le Serveur Web  

  Le serveur nommé "Serveur Web" est configuré pour répondre aux requêtes HTTP et HTTPS. Sa passerelle par défaut est l'adresse du routeur du réseau local, ce qui permet d'y accéder depuis l'extérieur du réseau via le routeur. Il héberge quelques petites pages et des photos fournies par Cisco. Tous les ordinateurs (fixes ou portables) du réseau peuvent accéder au serveur et demander des ressources.

  Les ordinateurs de l'Entreprise 2 peuvent y accéder en saisissant "serveur_web" dans la barre de recherche de leur navigateur web, car ce nom de domaine est associé à l'adresse IP du serveur Web dans le serveur DNS. De leur côté, les ordinateurs de l'Entreprise 1 peuvent également accéder au serveur et demander des ressources, mais ils doivent utiliser l'adresse IP du serveur au lieu de son nom de domaine.

- ### Le Serveur DHCP/DNS  
  - #### Le Serveur DNS

        Ce serveur joue deux rôles, comme son nom l'indique. Il fonctionne à la fois comme serveur DNS, en résolvant les noms de domaine associés à certaines adresses IP (configurées manuellement). Les associations nom-IP sont ainsi enregistrées dans la table DNS (zonz DNS).      

  - #### Le Serveur DHCP

        Le serveur DHCP utilise le protocole DHCP pour attribuer automatiquement des adresses IP aux nouveaux appareils connectés au réseau. Pour le configurer, il faut lui attribuer une adresse IP manuelle, définir une plage d'adresses IP à distribuer, ainsi que le nombre d'adresses disponibles. En configurant correctement la passerelle par défaut et le serveur DNS (qui est également l'adresse du serveur DHCP lui-même), ce serveur peut fournir à chaque appareil une adresse IP, un DNS, ainsi qu'une passerelle par défaut pour permettre l'envoi et la réception de paquets vers d'autres réseaux.

    
## Utilisation du Projet

Vous pouvez réutiliser, améliorer ou modifier ce projet comme vous le souhaitez. Pour cela, suivez les étapes ci-dessous :

- ##### Télécharger le simulateur Cisco Packet Tracer

    Vous pouvez l'installer sur n'importe quel système d'exploitation, car il existe plusieurs sites proposant le téléchargement. Voici un lien vers un cours OpenClassrooms avec des vidéos explicatives pour l'installation en fonction de votre OS :
    
    [Installer Cisco Packet Tracer sur votre système d'exploitation](https://openclassrooms.com/fr/courses/7192261-simulez-le-schema-de-votre-reseau-avec-cisco-packet-tracer/7444116-installez-cisco-packet-tracer-sur-votre-systeme-d-exploitation)

- ##### Se connecter à votre compte Cisco

    Si vous avez déjà un compte Cisco, la connexion est rapide. Sinon, vous pouvez créer un compte gratuit sur le site "Cisco Networking Academy" :
    
    [Cisco Networking Academy](https://www.netacad.com/fr)
    
    Une fois votre compte créé, vous pouvez vous connecter.

- ##### Télécharger le fichier "Simulation_Reseaux.pkt" et l'ouvrir avec Packet Tracer

    Ce fichier se trouve dans le dossier `src` de ce dépôt. Téléchargez-le et ouvrez-le avec Cisco Packet Tracer pour accéder au projet et le modifier selon vos envies ou besoins.

## Ressources Videos
Vous trouverez dans le dossier `videos` de petites vidéos où je commente l'adressage IP sur les machines, la configuration du DNS et du DHCP, ainsi que l'accès au navigateur web d'un ordinateur, à son invite de commande, etc.

## PS
  Certaines fois, l'envoie des données refusent en mode "Realtime" et il vous faut juste refaire le processus en supprimant le paquet.  
  Ou faites un ping à la place ;)