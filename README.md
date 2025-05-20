1-1 Pour quelle raison est-il préférable d’exécuter le conteneur avec un drapeau pour donner les variables d’environnement plutôt que de les mettre directement dans le Dockerfile ? -e

Il est préférable d’utiliser le drapeau `-e` lors de l’exécution du conteneur pour fournir les variables d’environnement, car cela permet de ne pas exposer d’informations sensibles (comme des mots de passe ou des clés API) dans le Dockerfile, qui peut être partagé ou versionné. Cela offre également plus de flexibilité pour modifier les valeurs des variables sans avoir à reconstruire l’image Docker à chaque changement.

1-2 Pourquoi avons-nous besoin d’un volume à attacher à notre conteneur postgres ?

Nous avons besoin d’un volume attaché au conteneur Postgres afin de persister les données de la base de données en dehors du cycle de vie du conteneur. Sans volume, toutes les données seraient perdues à chaque suppression ou recréation du conteneur. Le volume permet donc de conserver les données même si le conteneur est arrêté, supprimé ou mis à jour.

1-6 Why is docker-compose so important?

Docker-compose est important car il permet de définir, configurer et gérer facilement des applications multi-conteneurs à l’aide d’un simple fichier YAML. Il simplifie l’orchestration, l’automatisation du déploiement, la gestion des réseaux et des volumes, et facilite la reproduction de l’environnement de développement ou de production. Cela rend la gestion de projets complexes plus efficace et moins sujette aux erreurs.

2-1 What are testcontainers?

Testcontainers is a Java library that allows you to run lightweight, throwaway containers (usually Docker containers) for your integration tests. It helps you create reliable and reproducible test environments by spinning up real instances of databases, message brokers, or other services your application depends on, all within Docker containers.

2-2 For what purpose do we need to use secured variables ?

We need to use secured variables to protect sensitive information such as passwords, API keys, and tokens from being exposed in source code, configuration files, or version control systems. Secured variables help prevent unauthorized access and reduce the risk of security breaches by ensuring that confidential data is only accessible to authorized processes or users at runtime.

2-3 Why did we put `needs: build-and-test-backend` on this job? Maybe try without this and you2-3 Why di

We use `needs: build-and-test-backend` in a GitHub Actions workflow to specify that the current job depends on the successful completion of the `build-and-test-backend` job before it can start. This ensures that jobs run in the correct order and that any required artifacts or results from the backend build and test process are available. If you remove this dependency, the jobs may run in parallel or in the wrong order, potentially causing failures if the backend is not ready or tested before subsequent steps execute.d we put needs: build-and-test-backend on this job? Maybe try without this and you will see! will see!

2-4 For what purpose do we need to push docker images?

We need to push Docker images to a remote registry (like Docker Hub or GitHub Container Registry) so that they can be easily shared, deployed, and used by others or by automated systems (such as CI/CD pipelines or production servers). Pushing images ensures that the exact environment and application code are available wherever needed, enabling consistent deployments and easier scaling.