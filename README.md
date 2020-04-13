# Medicamento

Cette application est inspirée de Medico, une appli iPhone ayant pour but de rendre accessible les données publiques sur les médicaments en France. Medicamento vise à fournir aux non-utilisateurs d'iPhone un accès immédiat aux données via une simple application web.

### Provenance des données

Un algorithme en Python permet de récupérer les fichiers sur un site dédié du gouvernement (BDPM, [page de téléchargement](http://base-donnees-publique.medicaments.gouv.fr/telechargement.php)), les transforme en fichiers CSV facilement exploitables, et enfin constitue un Dataframe Pandas afin d'exporter la base de données en différents formats (notamment JSON, pour la partie suivante).

Les en-têtes de colonnes ont été remplis manuellement à partir du [fichier descriptif des données (PDF)](http://base-donnees-publique.medicaments.gouv.fr/docs/Contenu_et_format_des_fichiers_telechargeables_dans_la_BDM_v1.pdf) et d'un peu de rétro-ingénierie sur les fiches de description consultables sur le site.

### Scan d'un code-barre

La webapp Javascript permet actuellement de scanner un code-barre sur une boîte de médicament, et redirige ensuite vers la page correspondante de BDPM.

Pour fonctionner, Medicamento requiert l'accès à votre caméra/webcam, cependant *aucune donnée n'est stockée* ; cette application s'exécute uniquement dans votre navigateur et se contente de faire le lien entre un numéro sur la boîte et une adresse URL sur BDPM. Le lien est fait grâce au fichier `db.json` comportant les différents identifiants des médicaments.


### Ressources & liens utiles

- Bibliothèque pour la lecture du code-barre : [QuaggaJS](http://base-donnees-publique.medicaments.gouv.fr/docs/Contenu_et_format_des_fichiers_telechargeables_dans_la_BDM_v1.pdf)
- [p5js](https://github.com/processing/p5.js)
- [Base de Données Publique des Médicaments (site gouvernemental)](http://base-donnees-publique.medicaments.gouv.fr)
- app Medico (iOS, [lien App Store](https://apps.apple.com/fr/app/medico/id1462935634))
- Une application similaire pour Android : [TinyMan/MediScan](https://github.com/TinyMan/MediScan)
- [TinyMan/bdpm-tools](https://github.com/TinyMan/bdpm-tools)
