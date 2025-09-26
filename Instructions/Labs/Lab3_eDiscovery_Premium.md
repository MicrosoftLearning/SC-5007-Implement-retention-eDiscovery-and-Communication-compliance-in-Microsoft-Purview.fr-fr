---
lab:
  task: Case investigation with eDiscovery
  exercise: Exercise 3 - Case investigation with eDiscovery
---

## Locataires WWL - Conditions d’utilisation

Si un locataire vous est fourni dans le cadre d’une formation dispensée par un instructeur, notez qu’il est mis à votre disposition dans le seul but de prendre en charge les labos pratiques de la formation.

Vous ne devez ni partager ni utiliser les locataires en dehors des labos pratiques. Le locataire utilisé dans ce cours est un locataire d’essai. Au terme de la classe, le locataire ne pourra pas faire l’objet d’une prolongation et vous ne pourrez plus l’utiliser ni y accéder.

Vous n’êtes pas autorisé à convertir un locataire en abonnement payant. Les locataires obtenus dans le cadre de ce cours sont la propriété de Microsoft Corporation. Nous nous réservons le droit d’y accéder et d’en reprendre possession à tout moment.

# Tâches associées à la compétence de l’exercice 3

Contoso soupçonne que des données de paiement sensibles, notamment des numéros de carte de crédit et de compte, ont été mal manipulées ou divulguées. En tant qu’enquêteur, votre travail consiste à utiliser Microsoft Purview eDiscovery pour créer un dossier, effectuer des recherches dans les sources de données, identifier les contenus sensibles et les masquer avant de produire les résultats à des fins de conformité ou d’examen juridique.

Votre tâche consiste à créer et gérer des cas eDiscovery qui respectent les critères d’enquête :

- **Créer un cas eDiscovery** : Configurez un dossier pour gérer l’enquête sur les données de paiement.
- **Effectuer une recherche eDiscovery** : Effectuez une recherche dans les sources de données pour identifier les fichiers susceptibles de contenir des informations relatives aux cartes de paiement ou aux comptes.
- **Ajouter des éléments au jeu de révision** : Commitez vos résultats de recherche dans un jeu de révision pour une analyse plus approfondie.
- **Marquer les éléments à réviser** : Appliquez des étiquettes de pertinence et de masquage pour organiser les documents liés au dossier.
- **Appliquer les masquages** : Utilisez des outils d’annotation pour masquer les informations sensibles telles que les numéros de carte et de compte.
- **Exporter les résultats** : Exportez les éléments révisés et balisés, ainsi qu’un rapport sur les éléments, pour production.

   > **Remarque** : ce labo implique d’accéder à un locataire M365 E5 avec des données à explorer pour mener une enquête. Vous pouvez parcourir cet exercice sans données, mais les collections et les jeux à réviser ne donneront aucun résultat.

## Tâche 1 : accorder des autorisations pour eDiscovery

Pour exporter des fichiers, vous avez besoin d’autorisations spécifiques en raison de l’accès direct que cette option octroie sur les fichiers utilisateur.

1. Dans Microsoft Edge, accédez au portail Microsoft Purview, `https://purview.microsoft.com`, et connectez-vous.

1. Dans le volet de navigation de gauche, sélectionnez **Paramètres**.

1. Dans le volet de navigation de gauche, développez **Rôles et étendues**, puis sélectionnez **Groupes de rôles**.

1. Sur la page **Groupes de rôles pour les solutions Microsoft Purview**, sélectionnez **Gestionnaire eDiscovery**.

1. Sur la page volante **Gestionnaire eDiscovery** à droite, sélectionnez **Modifier**.

1. Sur la page **Gérer le Gestionnaire eDiscovery**, sélectionnez **Choisir des utilisateurs**.

1. Sur la page volante **Choisir des utilisateurs** à droite, sélectionnez l’utilisateur que vous utiliserez pour mener l’enquête eDiscovery dans les étapes suivantes, puis sélectionnez **Sélectionner**.

    >**Note** : vérifiez que vous sélectionnez l’utilisateur qui examine les données et exporte les résultats de la recherche.

1. De retour sur la page **Gérer le Gestionnaire eDiscovery**, sélectionnez **Suivant**.

1. Sur la page **Gérer le Gestionnaire eDiscovery**, sélectionnez **Suivant**.

1. Sur la page **Vérifier le groupe de rôles et terminer**, sélectionnez **Enregistrer** pour ajouter votre utilisateur au groupe de rôles Gestionnaire eDiscovery.

1. Une fois que vous avez ajouté les utilisateurs, sélectionnez **Terminé** sur la page **Vous avez mis à jour le groupe de rôles**.

Vous avez accordé l’autorisation Gestionnaire eDiscovery.

## Tâche 2 : créer un dossier eDiscovery

Dans cette tâche, vous allez créer un nouveau dossier eDiscovery afin de gérer l’enquête sur les données de paiement.

1. Dans Microsoft Purview, sélectionnez **Solutions** > **eDiscovery**.

1. Sur la page **Dossiers**, sélectionnez **Créer un dossier**.

1. Dans la fenêtre de dialogue **Nouveau dossier**, entrez :

   - **Nom du cas** : `Payment Data Leak Investigation`
   - **Description du cas** : `Investigation into potential exposure of payment card and account data at Contoso.`

1. Sélectionnez **Créer**.

   Une fois votre dossier créé, vous serez directement redirigé vers votre nouveau dossier.

Vous avez créé avec succès un nouveau dossier eDiscovery nommé _Enquête sur la fuite de données de paiement_.

## Tâche 3 : créer une recherche eDiscovery

Dans cette tâche, vous générez une recherche pour trouver les e-mails et les documents qui font référence à des données de paiement sensibles.

1. Sélectionnez **Créer une recherche**.

1. Dans la fenêtre de dialogue **Nouvelle recherche**, entrez :

   - **Nom de recherche** : `Payment Data Exposure Search`
   - **Description de la recherche** : `Find emails and documents that reference credit cards, debit cards, or account numbers.`

1. Sélectionnez **Créer**.

1. Sur la page **Recherche d’exposition des données de paiement**, sélectionnez **Ajouter des sources**.

1. Sur la page **Rechercher une source**, **filtrez** vos sources pour **Groupes uniquement**.

1. Sélectionnez **Ajouter des sources à l’échelle du locataire** et laissez les cases **Toutes les personnes et tous les groupes** et **Tous les dossiers publics** cochées.

1. Cliquez sur **Enregistrer**.

1. De retour à la page **Recherche d’exposition des données de paiement**, dans le **Générateur de conditions**, ajoutez des conditions :

   - Dans la première case, définissez **Mots-clés =**, puis tapez `credit card`.
   - Dans la deuxième zone, tapez `debit card`.
   - Dans la troisième zone, tapez `account number`.

   > **Remarque** : Les conditions sont considérées comme reliées par un OU, donc la recherche renvoie les éléments contenant « carte de crédit », « carte de débit » ou « numéro de compte ».

1. Sélectionnez **Exécuter la requête**.

1. Sur la page **Choisir les résultats de recherche**, sélectionnez **Statistiques**, puis cochez **Inclure le rapport sur les mots-clés de la requête**.

1. Sélectionnez **Exécuter la requête** pour lancer la recherche.

   > **Remarque** : Ce processus peut prendre environ 5 minutes pour générer les résultats.

1. Une fois la recherche terminée, passez en revue vos résultats dans l’onglet **Statistiques**. Consultez le nombre d’éléments, le volume de données et les occurrences des mots-clés.

1. Passez à l’onglet **Échantillon**. Sélectionnez **Générer des résultats d’échantillon**.

1. Sur la page **Générer une vue d’échantillon**, conservez les valeurs par défaut, puis sélectionnez **Exécuter la requête**.

   > **Remarque** : Ce processus peut prendre environ 5 minutes pour générer les résultats.

1. Une fois la requête terminée, passez en revue les résultats.

Vous avez exécuté la recherche avec succès et passé en revue les résultats à l’aide des vues Statistiques et Échantillon.

## Tâche 4 : ajouter votre recherche au jeu de révision

Dans cette tâche, vous commitez les résultats de votre recherche dans un jeu de révision afin qu’ils puissent être analysés plus en profondeur.

1. Dans la page **Recherche d’exposition des données de paiement**, sélectionnez **Ajouter au jeu de révision**.

1. Dans le menu volant **Ajouter au jeu de révision**, sélectionnez **Ajouter au nouveau jeu de révision**.

   - Entrez un nom : `Payment Data Review Set`.

1. Sous **Sélectionner les éléments à inclure**, conservez **Éléments indexés correspondant à votre requête de recherche sélectionnés**.

1. Sous **Sélectionner les éléments dans les listes et les pièces jointes**, sélectionnez **Pièces jointes de la liste** afin que les fichiers joints soient inclus dans le jeu de révision.

1. Laissez toutes les autres options par défaut, puis sélectionnez **Ajouter au jeu de révision**.

   > **Remarque** : Ce processus peut prendre environ 5 minutes pour générer les résultats.

Vous avez créé avec succès le **Jeu de révision des données de paiement** et y avez ajouté vos résultats de recherche.

## Tâche 5 : passer en revue et marquer les éléments

Dans cette tâche, vous filtrez les éléments du jeu de révision et appliquez des étiquettes afin de les organiser pour l’enquête.

1. Sur la page **Jeu de révision des données de paiement**, sélectionnez **Requête**, puis configurez :

   - Premier menu déroulant : **Mots clés**
   - Opérateur : **Est égal à l’un des éléments suivants**
   - Entrez des mots clés :

     - `Visa`
     - `Master Card`
   - Cliquez sur **+ Ajouter des conditions**.
   - Ajouter une condition :

     - Champ : **Classe de fichier**
     - Opérateur : **Est égal à l’un des éléments suivants**
     - Valeur: `Document`
   - Sélectionnez **Exécuter la requête**.

1. Sélectionnez **Enregistrer** pour enregistrer cette requête de recherche. Dans le champ Nom du filtre, entrez `Payment data docs`.

1. Dans la barre de commandes, sélectionnez **Étiqueter les fichiers**.

1. Dans le menu volant **Étiqueter les fichiers**, sélectionnez **Créer/modifier des étiquettes**.

1. Sur la page **Gérer les étiquettes**, configurez :

   - **Nom du groupe d’étiquettes** : `Relevance`

     - **Nom de l’étiquette** : `Relevant`
     - Sélectionnez **Ajouter une étiquette**, puis ajoutez `Not relevant`
   - Sélectionnez **Ajouter un groupe d’étiquettes**.
   - **Nom du groupe d’étiquettes** : `Review status`
     - **Nom de l’étiquette** : `Needs redaction`

1. Sélectionnez **Enregistrer**, puis **Fermer**.

1. Dans le menu volant **Étiqueter les fichiers**, appliquez l’étiquette **Pertinent** au premier élément et l’étiquette **Non pertinent** au deuxième élément.

1. Dans le jeu de révision, recherchez **Contoso Purchasing Permissions - Q1.docx** de **Irvin S** daté du **2 août 2019**.

1. Sélectionnez l’élément et étiquetez-le comme **À masquer**.

1. Sélectionnez **Fermer** pour fermer le menu volant **Étiqueter les fichiers**.

Vous avez correctement étiqueté les documents Pertinent, Non pertinent et À masquer.

## Tâche 6 : appliquer des masquages

Dans cette tâche, vous masquez les informations sensibles d’un document dans votre jeu de révision.

1. Dans le **Jeu de révision des données de paiement**, sélectionnez l’élément **Contoso Purchasing Permissions - Q1.docx** de **Irvin S** daté du **2 août 2019** pour ouvrir la visionneuse de documents.

1. Dans la barre d’outils de la visionneuse, sélectionnez **Annoter**.

1. Dans les outils d’annotation, ouvrez le menu déroulant **Dessin**, puis sélectionnez **Masquage de zone**.

    >![Capture d’écran indiquant où sélectionner Masquage de zone.](./Media/area-redaction.png)

1. À l’aide de votre curseur, tracez un cadre autour des informations sensibles contenues dans le fichier, telles que :

   - Numéro de carte Visa
   - Numéro de carte MasterCard
   - Numéro de compte bancaire

1. Répétez l’opération autant que nécessaire jusqu’à ce que toutes les données sensibles soient masquées.

1. Fermez la visionneuse de documents.

1. De retour sur la page **Jeu de révision des données de paiement**, avec le fichier **Contoso Purchasing Permissions - Q1.docx** sélectionné, choisissez **Actions** > **Appliquer les masquages au PDF**.

   > **Remarque** : Valider les masquages permet d’enregistrer un PDF masqué dans le jeu de révision tout en conservant le fichier d’origine inchangé.

Vous avez correctement appliqué les masquages et les avez validés dans une copie PDF masquée.

## Tâche 7 : exporter les résultats

Dans cette tâche, vous exportez les éléments masqués et étiquetés de votre jeu de révision en vue de leur production.

1. Dans le **Jeu de révision des données de paiement**, cochez les cases des éléments que vous souhaitez exporter.

   > Assurez-vous d’inclure le document **Contoso Purchasing Permissions - Q1.docx** que vous avez masqué.

1. Dans la barre de commandes, sélectionnez **Actions** > **Exporter**.

1. Dans le menu volant **Exporter**, configurez :

   - **Nom de l’exportation** : `PaymentData_Export_2025`
   - **Description** : `Export of review set items with redacted versions for Payment Data Leak Investigation.`

1. Sous **Sélectionner les éléments à inclure dans l’exportation** :

   - Choisissez **Documents sélectionnés uniquement**.
   - Laissez la case **Développer les documents sélectionnés pour inclure > Éléments associés de la famille** cochée (cela permet d’inclure les pièces jointes).

1. Sous **Type d’exportation**, sélectionnez **Exporter les éléments avec le rapport sur les éléments**.

   - Cochez la case **Exporter les masquages** pour inclure les PDF masqués et la case **Exporter les étiquettes** pour inclure les informations d’étiquetage.

1. Sous **Format d’exportation**, sélectionnez **Créer des fichiers .msg pour les messages** et laissez toutes les autres options par défaut sélectionnées.

1. Sélectionnez **Exporter**.

1. Sélectionnez le **Gestionnaire de processus** pour afficher l’état de l’exportation.

1. Sélectionnez **Actualiser** dans le gestionnaire de processus jusqu’à ce que le statut de l’exportation soit **Terminé**.

1. Une fois que le statut est **Terminé**, sélectionnez la ligne correspondant à votre exportation.

1. Dans le menu volant **Exporter**, sélectionnez tous les fichiers sous **Exporter les packages**, puis **Télécharger**.

1. Sélectionnez un emplacement pour télécharger vos exportations, puis accédez à l’emplacement de vos exportations téléchargées.

1. Explorez les éléments de votre fichier zip.

Vous avez créé un dossier, recherché des données sensibles, ajouté des éléments à un jeu de révision, appliqué des étiquettes et des masquages, puis exporté les résultats masqués. Ce sont les étapes clés pour mener une enquête avec Microsoft Purview eDiscovery.