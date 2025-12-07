 (cd "$(git rev-parse --show-toplevel)" && git apply --3way <<'EOF' 
diff --git a/README.md b/README.md
index 956f4cb20dcd93e40a4edbb0e05a6a699d080b15..7c3736554a048fd55c3587b6c870ba4ba9b658f5 100644
--- a/README.md
+++ b/README.md
@@ -1,2 +1,27 @@
-# maintenance-CMDK
-suivi des tâches de la maintenance CMDK
+# Maintenance CMDK – suivi des tâches
+
+Application web statique pour suivre les tickets de maintenance des sites CMDK (CMDG, CMDN, CMDLT, CMDB, Résidence et Manhattan). L'interface propose un tableau de bord, des rapports automatiques, une séparation par site et une archive centralisée pour les tâches terminées.
+
+## Fonctionnalités principales
+- **Accès sécurisé** : seules les adresses `@cmd.cd` peuvent se connecter. L'ajout ou la modification des tâches est réservé à `mkhalife@cmd.cd`.
+- **Menus déroulants** : navigation rapide vers les sites, les rapports et les archives.
+- **Tableau de bord** : cartes de synthèse des tâches en attente, en cours et terminées, avec un focus par site.
+- **Ajout et classement automatique** : les nouvelles tâches sont assignées au site choisi. Les tâches marquées « Terminée » sont déplacées automatiquement vers l'archive pour ne pas encombrer le tableau principal.
+- **Vue par site** : colonnes séparées pour « En attente » et « En cours » pour chaque site.
+- **Rapports automatiques** : génération instantanée d'un rapport mensuel (30 jours) et annuel (365 jours) avec export CSV.
+- **Archives centralisées** : toutes les tâches terminées sont regroupées dans un seul espace pour consultation ou export.
+
+## Démarrage
+Aucune dépendance n'est requise :
+1. Ouvrez `index.html` dans votre navigateur (clic ou double-clic depuis l'explorateur de fichiers).
+2. Saisissez votre email professionnel `@cmd.cd` dans la fenêtre de connexion.
+3. Connectez-vous avec `mkhalife@cmd.cd` pour créer ou modifier des tâches. Les autres comptes restent en lecture seule.
+
+## Utilisation rapide
+- **Ajouter une tâche** : section « Ajouter une nouvelle tâche ». Choisissez le site et le statut initial (les tâches terminées iront directement dans l'archive).
+- **Changer un statut** : depuis les colonnes « En attente » ou « En cours », utilisez le sélecteur de statut (uniquement pour `mkhalife@cmd.cd`).
+- **Archiver** : les tâches terminées sont migrées automatiquement. Le menu « Archives » propose un bouton pour archiver en masse si nécessaire.
+- **Rapports** : section « Rapports automatiques » pour visualiser les synthèses mensuelle et annuelle, avec export CSV.
+
+## Stockage des données
+Toutes les données sont conservées dans le `localStorage` du navigateur de l'utilisateur. Aucune donnée n'est envoyée vers un serveur.
 
EOF
)
