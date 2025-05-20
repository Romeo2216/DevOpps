1-1 Pour quelle raison est-il préférable d’exécuter le conteneur avec un drapeau pour donner les variables d’environnement plutôt que de les mettre directement dans le Dockerfile ? -e

Il est préférable d’utiliser le drapeau `-e` lors de l’exécution du conteneur pour fournir les variables d’environnement, car cela permet de ne pas exposer d’informations sensibles (comme des mots de passe ou des clés API) dans le Dockerfile, qui peut être partagé ou versionné. Cela offre également plus de flexibilité pour modifier les valeurs des variables sans avoir à reconstruire l’image Docker à chaque changement.

1-2 Pourquoi avons-nous besoin d’un volume à attacher à notre conteneur postgres ?

Nous avons besoin d’un volume attaché au conteneur Postgres afin de persister les données de la base de données en dehors du cycle de vie du conteneur. Sans volume, toutes les données seraient perdues à chaque suppression ou recréation du conteneur. Le volume permet donc de conserver les données même si le conteneur est arrêté, supprimé ou mis à jour.

1-6 Why is docker-compose so important?

Docker-compose est important car il permet de définir, configurer et gérer facilement des applications multi-conteneurs à l’aide d’un simple fichier YAML. Il simplifie l’orchestration, l’automatisation du déploiement, la gestion des réseaux et des volumes, et facilite la reproduction de l’environnement de développement ou de production. Cela rend la gestion de projets complexes plus efficace et moins sujette aux erreurs.
