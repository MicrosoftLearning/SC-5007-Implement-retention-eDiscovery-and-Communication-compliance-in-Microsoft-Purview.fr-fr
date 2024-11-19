---
lab:
  task: Create retention labels
  exercise: Exercise 2 - Create retention labels
---

## Locataires WWL - Conditions d’utilisation

Si un locataire vous est fourni dans le cadre d’une formation dispensée par un instructeur, notez qu’il est mis à votre disposition dans le seul but de prendre en charge les labos pratiques de la formation.

Vous ne devez ni partager ni utiliser les locataires en dehors des labos pratiques. Le locataire utilisé dans ce cours est un locataire d’essai. Au terme de la classe, le locataire ne pourra pas faire l’objet d’une prolongation et vous ne pourrez plus l’utiliser ni y accéder.

Vous n’êtes pas autorisé à convertir un locataire en abonnement payant. Les locataires obtenus dans le cadre de ce cours sont la propriété de Microsoft Corporation. Nous nous réservons le droit d’y accéder et d’en reprendre possession à tout moment.

# Tâches associées à la compétence de l’exercice 2

Votre tâche consiste à créer et gérer des étiquettes de rétention qui respectent les critères requis.

- **Créer des étiquettes de rétention** : configurez des étiquettes de rétention pour différents types de documents et d’e-mails.
- **Publier des étiquettes de rétention** : mettez les étiquettes de rétention à la disposition des utilisateurs pour l’utilisation.
- **Appliquer automatiquement des étiquettes de rétention** : configurez des étiquettes de rétention pour qu’elles soient appliquées automatiquement en fonction de conditions spécifiques.

## Tâche 1 : créer des étiquettes de rétention

Dans cette tâche, vous allez créer des étiquettes de rétention qui peuvent être affectées aux documents et aux e-mails.

1. Dans Microsoft Edge, accédez au portail Microsoft Purview, `https://purview.microsoft.com`, et connectez-vous.
1. Sélectionnez **Afficher toutes les solutions**.
1. Sous **Risque et Conformité**, sélectionnez la carte **Gestion des enregistrements**.
1. Dans le volet de navigation de gauche, sélectionnez **Plan de gestion de fichiers**.
1. Sur la page **Étiquettes**, sélectionnez **+ Créer une étiquette**.
1. Sur la page **Nommer votre étiquette de rétention**, saisissez :

    - **Nom :** `Financial Records`
    - **Description pour les utilisateurs** : `Assign this label to financial documents to ensure they are retained for the required period.`
    - **Description pour les administrateurs** : `Financial records with retention period.`
1. Cliquez sur **Suivant**.
1. Sur la page **Définir des descripteurs de plan gestion de fichiers pour cette étiquette**, sélectionnez **Suivant**.
1. Sur la page **Définir les paramètres d’étiquette**, choisissez l’option **Conserver les éléments indéfiniment ou pour une période spécifique**, puis sélectionnez **Suivant**.

1. Sur la page **Définir la période**, saisissez :

    - **Quelle est la durée de la période ?**  : 7 ans
    - **Quand la période doit-elle commencer ?**  : Quand des éléments ont été créés
1. Cliquez sur **Suivant**.
1. Sur la page **Choisir ce qui se passe pendant la période de rétention**, sélectionnez **Conserver les éléments même si les utilisateurs les suppriment**, puis **Suivant**.
1. Sur la page **Choisir ce qui se passe après la période de rétention**, sélectionnez **Désactiver les paramètres de rétention**, puis **Suivant**.
1. Sur la page **Vérifier et terminer**, sélectionnez **Créer une étiquette**.
1. Sur la page **Votre étiquette de rétention est créée**, sélectionnez **Ne rien faire**, puis **Terminé**. L’étiquette sera publiée ultérieurement dans l’exercice.
1. De retour sur la page **Plan de gestion de fichiers**, sélectionnez **+ Créer une étiquette** pour créer une autre étiquette de rétention.
1. Sur la page **Nommer votre étiquette de rétention**, saisissez :

    - **Nom :** `HR Records`
    - **Description pour les utilisateurs** : `This label is auto-applied to HR records with a retention period of five years.`
    - **Description pour les administrateurs** : `Auto-applied retention label for HR records.`
1. Cliquez sur **Suivant**.
1. Sur la page **Définir des descripteurs de plan gestion de fichiers pour cette étiquette**, sélectionnez **Suivant**.
1. Sur la page **Définir les paramètres d’étiquette**, choisissez l’option **Conserver les éléments indéfiniment ou pour une période spécifique**, puis sélectionnez **Suivant**.
1. Sur la page **Définir la période**, saisissez :

    - **Quelle est la durée de la période ?**  : 5 ans
    - **Quand la période doit-elle commencer ?**  : Quand des éléments ont été créés
1. Cliquez sur **Suivant**.
1. Sur la page **Choisir ce qui se passe pendant la période de rétention**, sélectionnez **Conserver les éléments même si les utilisateurs les suppriment**, puis **Suivant**.
1. Sur la page **Choisir ce qui se passe après la période de rétention**, sélectionnez **Désactiver les paramètres de rétention**, puis **Suivant**.
1. Sur la page **Vérifier et terminer**, sélectionnez **Créer une étiquette**.
1. Sur la page **Votre étiquette de rétention est créée**, sélectionnez **Ne rien faire**, puis **Terminé**.

Vous avez créé des étiquettes de rétention pour des enregistrements financiers avec une période de rétention de sept ans et des enregistrements RH avec une période de rétention de cinq ans.

## Tâche 2 : publier des étiquettes de rétention

Après la tâche 1, vous allez maintenant publier les étiquettes de rétention afin qu’elles soient disponibles pour que les utilisateurs puissent les appliquer aux documents dans les e-mails Exchange et les documents SharePoint.

1. Vous devriez toujours être sur la page **Plan de gestion de fichiers** dans le portail Microsoft Purview.

   Si ce n’est pas le cas, dans Microsoft Edge, accédez au portail Microsoft Purview, `https://purview.microsoft.com`, et connectez-vous. Sélectionnez **Afficher toutes les solutions**, puis **Gestion des enregistrements** > **Plan de gestion de fichiers**.

1. Sélectionnez la coche en regard de l’étiquette de rétention **Enregistrements financiers**, puis le bouton **Publier des étiquettes**.

    >![Capture d’écran montrant où sélectionner l’étiquette de rétention et le bouton Publier des étiquettes.](./Media/publish-labels.png)

1. Sur la page **Choisir les étiquettes à publier**, l’étiquette de rétention **Enregistrements financiers** doit être affichée.
1. Cliquez sur **Suivant**.
1. Sur la page **Étendue de la stratégie**, sélectionnez **Suivant**.
1. Sur la page **Choisir le type de stratégie de rétention à créer**, sélectionnez **Statique**, puis **Suivant**.
1. Sur la page **Choisir où publier des étiquettes**, sélectionnez **Me laisser choisir des emplacements spécifiques** et activez les éléments suivants :

   - Les boîtes aux lettres Exchange
   - Sites classiques et de communication SharePoint
   - Comptes OneDrive

1. Vérifiez que les boîtes aux lettres de groupe et les sites Microsoft 365 sont définis sur **Désactivé**, puis sélectionnez **Suivant**.
1. Sur la page **Nommer votre stratégie**, saisissez :

   - Nom : `Financial Records Retention Label`
   - Description : `Retention label for financial records with a seven-year retention period.`
1. Cliquez sur **Suivant**.
1. Sur la page **Terminer**, sélectionnez **Envoyer**.
1. Sur la page **Votre étiquette de rétention a été publiée**, sélectionnez **Terminé**.

Vous avez publié l’étiquette de rétention pour les enregistrements financiers.

## Tâche 3 : publier ou appliquer automatiquement des étiquettes de rétention

Après la tâche 1, vous allez maintenant appliquer automatiquement l’étiquette de rétention des enregistrements RH afin que les informations soient conservées.

1. Vous devriez toujours être dans **Gestion des enregistrements** dans le portail Microsoft Purview. 

   Si ce n’est pas le cas, dans Microsoft Edge, accédez au portail Microsoft Purview, `https://purview.microsoft.com`, et connectez-vous. Sélectionnez **Afficher toutes les solutions**, puis **Gestion des enregistrements**.

1. Dans le volet de navigation de gauche, développez **Stratégies**, puis sélectionnez **Stratégies des étiquettes**.
1. Sélectionnez **Appliquer automatiquement une étiquette** pour démarrer la configuration de **Créer une stratégie d’étiquetage automatique**.
1. Sur la page **Prise en main**, pour le **Nom** et la **Description**, saisissez les informations suivantes :

   - **Nom :** `HR Records auto-applied`
   - **Description** : `HR Records auto-applied retention label, with a retention period of five years for all locations.`
1. Cliquez sur **Suivant**.
1. Sur la page **Choisir le type de contenu auquel vous voulez appliquer cette étiquette**, sélectionnez **Appliquer l’étiquette au contenu qui contient des informations sensibles**, puis **Suivant**.
1. Sur la page **Contenu qui contient des informations sensibles**, sélectionnez la catégorie **Amélioré** et la **Réglementation américaine améliorée relative aux informations d’identification personnelle**, puis sélectionnez **Suivant**.

    >![Capture d’écran montrant le type d’informations d’identification personnelle sensibles sélectionné pour une étiquette de rétention appliquée automatiquement.](./Media/sensitive-info-pii.png)

1. Sur la page **Définir le contenu qui contient des informations sensibles**, conservez les valeurs par défaut sélectionnées, puis sélectionnez **Suivant**.
1. Sur la page **Étendue de la stratégie**, sélectionnez **Suivant**.
1. Sur la page **Choisir le type de stratégie de rétention à créer**, sélectionnez **Statique**, puis **Suivant**.
1. Sur la page **Choisir les emplacements pour appliquer la stratégie**, activez les options pour :

   - Les boîtes aux lettres Exchange
   - Sites classiques et de communication SharePoint
   - Comptes OneDrive
   - Boîtes aux lettres de groupe et sites Microsoft 365

1. Cliquez sur **Suivant**.
1. Sur la page **Choisir une étiquette à appliquer automatiquement**, sélectionnez **Ajouter une étiquette**.
1. Sur la page volante **Choisir une étiquette** à droite, cochez la case en regard de **Enregistrements RH**, puis sélectionnez **Ajouter**.
1. De retour sur la page **Choisir une étiquette à appliquer automatiquement**, sélectionnez **Suivant**.
1. Sur la page **Décider de tester ou d’exécuter votre stratégie**, sélectionnez **Activer la stratégie**, puis **Suivant**.
1. Sur la page **Vérifier et terminer**, sélectionnez **Envoyer**. Lorsque la stratégie est créée, sélectionnez **Terminé**.

Vous avez publié une étiquette de rétention avec application automatique. Pendant les sept jours suivants, tous les documents concernés seront automatiquement étiquetés avec l’étiquette publiée.
