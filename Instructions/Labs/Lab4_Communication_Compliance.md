---
lab:
  task: Configure Communication Compliance
  exercise: Exercise 4 - Configure Communication Compliance
---
## Locataires WWL - Conditions d’utilisation

Si un locataire vous est fourni dans le cadre d’une formation dispensée par un instructeur, notez qu’il est mis à votre disposition dans le seul but de prendre en charge les labos pratiques de la formation.

Vous ne devez ni partager ni utiliser les locataires en dehors des labos pratiques. Le locataire utilisé dans ce cours est un locataire d’essai. Au terme de la classe, le locataire ne pourra pas faire l’objet d’une prolongation et vous ne pourrez plus l’utiliser ni y accéder.

Vous n’êtes pas autorisé à convertir un locataire en abonnement payant. Les locataires obtenus dans le cadre de ce cours sont la propriété de Microsoft Corporation. Nous nous réservons le droit d’y accéder et d’en reprendre possession à tout moment.

# Tâches associées à la compétence de l’exercice 4

- **Stratégie de modèle prédéfinie** : créez une stratégie de conformité des communications à l’aide d’un modèle prédéfini.
- **Stratégie de modèle personnalisée** : créez une stratégie de conformité des communications en modifiant un modèle prédéfini.
- **Stratégie de communication personnalisée** : créez une stratégie de conformité des communications unique adaptée aux besoins spécifiques de votre organisation.

## Tâche 1 : créer une stratégie de conformité des communications à partir d’un modèle

Dans cette tâche, vous allez créer une stratégie à l’aide d’un modèle prédéfini pour résoudre rapidement les scénarios de conformité courants.

1. Dans Microsoft Edge, accédez au portail Microsoft Purview, `https://purview.microsoft.com`, et connectez-vous.
1. Sélectionnez **Afficher toutes les solutions**.
1. Sous **Risque et Conformité**, sélectionnez la carte **Conformité des communications**.
1. Dans le volet de navigation de gauche, sélectionnez **Stratégies**.
1. Sélectionnez **Créer une stratégie** et passez en revue les modèles de stratégie disponibles :

   - **Interactions Copilot** : surveille toutes les interactions avec Copilot pour Microsoft 365.
   - **Contenu inapproprié** : détecte le contenu à caractère haineux, violent, sexuel et lié à l’auto-mutilation dans Microsoft Teams.
   - **Texte inapproprié** : signale les menaces, la discrimination et le harcèlement dans Exchange Online, Microsoft Teams et Viva Engage.
   - **Images inappropriées** : identifie les images pour adultes et osées dans Exchange Online et Microsoft Teams.
   - **Informations sensibles** : surveille les informations sensibles dans Exchange Online, Microsoft Teams et Viva Engage avec un pourcentage de révision inférieur.
   - **Conformité réglementaire** : assure la conformité aux réglementations financières dans Exchange Online, Microsoft Teams et Viva Engage.
   - **Conflit d’intérêt** : détecte les conflits d’intérêt potentiels en interne dans Exchange Online, Microsoft Teams et Viva Engage.

1. Sélectionnez le modèle de stratégie pour **Détecter un texte inapproprié**.
1. Sur la page volante **Détecter les communications pour le texte inapproprié** à droite, saisissez l’utilisateur qui examinera les alertes de conformité des communications dans le champ **Réviseurs**.
1. Sélectionnez **Créer une stratégie** en bas de la page volante, puis **Fermer** sur la page **Votre stratégie a été créée**.

Vous avez créé une stratégie de conformité des communications à l’aide du modèle **Détecter le texte inapproprié**.

## Tâche 2 : créer une stratégie de conformité des communications à partir d’un modèle personnalisé

Ici, vous allez modifier un modèle de stratégie pour l’adapter aux besoins spécifiques de votre organisation.

1. Vous devriez toujours être sur la page **Stratégies** de **Conformité des communications** dans le portail Microsoft Purview.

   Si ce n’est pas le cas, dans Microsoft Edge, accédez au portail Microsoft Purview, `https://purview.microsoft.com`, et connectez-vous. Sélectionnez la carte **Afficher toutes les solutions** > **Conformité des communications** sous **Risque et Conformité**.

1. Sélectionnez **Créer une stratégie** > **Détecter les images inappropriées**.
1. Sur la page volante **Détecter les communications pour les images inappropriées**, sélectionnez **Personnaliser la stratégie** en bas de la page volante.
1. Sélectionnez **Personnaliser la stratégie** en bas de la page volante.
1. Sur la page **Nommer et décrire votre stratégie**, sélectionnez **Suivant**.
1. Sur la page **Choisir des utilisateurs et des réviseurs**, saisissez l’utilisateur qui examinera les alertes de conformité des communications dans le champ **Réviseurs**, puis sélectionnez **Suivant**.
1. Sur la page **Choisir les emplacements pour détecter les communications**, activez les emplacements pour :

   - Exchange.
   - Équipes.
   - Viva Engage.

1. Cliquez sur **Suivant**.
1. Sur la page **Choisir les conditions et le pourcentage de révision**, passez en revue les actions par défaut pour le modèle d’images inappropriées, puis sélectionnez **Suivant**.
1. Sur la page **Vérifier et terminer**, sélectionnez **Créer la stratégie**, puis **Terminé** sur la page **Votre stratégie a été mise à jour**.

Vous avez personnalisé une stratégie de conformité des communications à l’aide du modèle **Détecter les images inappropriées**.

## Tâche 3 : créer une stratégie de conformité des communications personnalisée

Dans cette tâche, vous allez créer une stratégie de conformité des communications à partir de zéro pour répondre à des exigences de conformité uniques.

1. Vous devriez toujours être sur la page **Stratégies** de **Conformité des communications** dans le portail Microsoft Purview.

   Si ce n’est pas le cas, dans Microsoft Edge, accédez au portail Microsoft Purview, `https://purview.microsoft.com`, et connectez-vous. Sélectionnez la carte **Afficher toutes les solutions** > **Conformité des communications** sous **Risque et Conformité**.

1. Sélectionnez **Créer une stratégie** > **Stratégie personnalisée**.
1. Sur la page **Nommer et décrire votre stratégie**, saisissez :

   - **Nom :** `Global Communication Compliance Policy`
   - **Description** : `Monitors emails and Teams messages for policy violations.`

1. Cliquez sur **Suivant**.
1. Sur la page **Choisir les utilisateurs et réviseurs** :

   - Sous **Choisir les utilisateurs et réviseurs**, sélectionnez **Tous les utilisateurs**.
   - Laissez le champ **Utilisateurs et groupes exclus** vide.
   - Dans le champ **Réviseurs**, saisissez les réviseurs qui surveilleront les alertes de conformité.

1. Cliquez sur **Suivant**.
1. Sur la page **Choisir les emplacements pour détecter les communications**, activez uniquement :

   - Exchange
   - Teams

   Vérifiez que tous les autres emplacements ne sont pas sélectionnés.

1. Cliquez sur **Suivant**.
1. Sur la page **Choisir les conditions et le pourcentage de révision**, conservez les valeurs par défaut sélectionnées pour **Sens de la communication**.
1. Sous **Conditions**, activez l’option permettant d’utiliser le **Nouveau générateur de conditions (préversion)**.
1. Sélectionnez **+ Ajouter une condition** > **Le contenu correspond à un classifieur entraînable**.
1. Sous **Le content correspond à des classifieurs entraînables**, sélectionnez **Ajouter** > **Classifieurs entraînables**.
1. Sur la page volante **Classifieurs entraînables** à droite, sélectionnez des classifieurs pour **Collusion réglementaire**, **Manipulation de stock**, **Divulgation non autorisée** et **Sabotage d’entreprise**.
1. Sélectionnez **Ajouter** en bas de la page volante **Classifieurs entraînables** à droite.
1. De retour sur la page **Choisir les conditions et le pourcentage de révision**, réglez le curseur **Pourcentage de révision** sur **25 %**.
1. Sélectionnez **Suivant** en bas de la page **Choisir les conditions et le pourcentage de révision**.
1. Sur la page **Vérifier et terminer**, sélectionnez **Créer la stratégie**, puis **Terminé** sur la page **Votre stratégie a été créée**.

Vous avez créé une stratégie de conformité des communications personnalisée nommée _Stratégie globale de conformité des communications_.
