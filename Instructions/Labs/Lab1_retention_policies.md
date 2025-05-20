---
lab:
  task: Configure Retention Policies
  exercise: Exercise 1 - Configure Retention Policies
---

## Locataires WWL - Conditions d’utilisation

Si un locataire vous est fourni dans le cadre d’une formation dispensée par un instructeur, notez qu’il est mis à votre disposition dans le seul but de prendre en charge les labos pratiques de la formation.

Vous ne devez ni partager ni utiliser les locataires en dehors des labos pratiques. Le locataire utilisé dans ce cours est un locataire d’essai. Au terme de la classe, le locataire ne pourra pas faire l’objet d’une prolongation et vous ne pourrez plus l’utiliser ni y accéder.

Vous n’êtes pas autorisé à convertir un locataire en abonnement payant. Les locataires obtenus dans le cadre de ce cours sont la propriété de Microsoft Corporation. Nous nous réservons le droit d’y accéder et d’en reprendre possession à tout moment.

# Tâches associées à la compétence de l’exercice 1

Votre tâche consiste à créer et gérer des stratégies de rétention qui respectent les critères requis :

- **Stratégie de rétention à l’échelle de l’entreprise** : appliquez une période de rétention et définissez les emplacements de cette stratégie.
- **Stratégies de rétention basées sur l’emplacement** : créez des stratégies de rétention pour des emplacements spécifiques, tels que des canaux et des conversations Teams, utilisateurs spécifiques compris.
- **Stratégies de rétention PowerShell** : implémentez des stratégies de rétention à l’aide de PowerShell.
- **Stratégies d’étendue adaptative** : créez et appliquez des stratégies de rétention avec des étendues adaptatives pour les services tels que le service juridique et les points de vente.

## Tâche 1 : créer une stratégie de rétention à l’échelle de l’entreprise

Ici, vous allez créer une stratégie de rétention qui s’applique à l’ensemble de l’organisation.

1. Dans Microsoft Edge, accédez au portail Microsoft Purview, `https://purview.microsoft.com`, et connectez-vous.
1. Un message à propos du nouveau portail Microsoft Purview s’affiche à l’écran. Sélectionnez l’option permettant d’accepter les conditions de divulgation de flux de données et la déclaration de confidentialité, puis sélectionnez **Démarrer**.

    >![Capture d’écran de l’écran Bienvenue sur le nouveau portail de conformité Microsoft Purview.](./Media/welcome-purview-portal.png)

1. Sélectionnez **Solutions** > **Gestion du cycle de vie des données**.
1. Développez **Stratégies**, puis sélectionnez **Stratégies de rétention** dans le volet de navigation de gauche.
1. Sélectionnez **+ Nouvelle stratégie de rétention**.
1. Sur la page **Nommer votre stratégie de rétention**, saisissez le nom et la description :

   - **Nom :** `Company wide`
   - **Description** : `All locations except for teams`

1. Cliquez sur **Suivant**.
1. Sur la page **Étendue de la stratégie**, sélectionnez **Suivant**.
1. Sur la page **Choisir le type de stratégie de rétention à créer**, sélectionnez **Statique**, puis **Suivant**.
1. Sur la page **Choisir où appliquer cette stratégie**, activez :

   - Les boîtes aux lettres Exchange
   - Sites classiques et de communication SharePoint
   - Comptes OneDrive
   - Boîtes aux lettres de groupe et sites Microsoft 365

1. Cliquez sur **Suivant**.
1. Sur la page **Décider si vous voulez conserver du contenu, le supprimer ou les deux**, pour la section **Conserver les éléments pendant une période spécifique**, saisissez les informations suivantes :

   - **Conserver les éléments pendant une période spécifique** : choisissez **Personnalisé** dans la liste déroulante
   - Définissez le champ des années sur **3**
   - **Démarrer la période de rétention en fonction de** : Quand les éléments ont été modifiés pour la dernière fois
   - **À la fin de la période de rétention** : Supprimer automatiquement les éléments

1. Cliquez sur **Suivant**.
1. Sur la page **Vérifier et terminer**, sélectionnez **Envoyer**.
1. Une fois votre stratégie créée, sélectionnez **Terminé**.

Vous avez créé une stratégie de rétention à l’échelle de l’entreprise qui conserve les éléments pendant trois ans à partir de la date de la dernière modification.

## Tâche 2 : créer des stratégies de rétention basées sur l’emplacement avec filtre

Ici, vous allez créer des stratégies de rétention spécifiquement pour les canaux et conversations Teams, filtres d’utilisateurs spécifiques compris.

1. Vous devriez toujours être sur l’écran **Stratégies de rétention** dans le portail Microsoft Purview.

   Si ce n’est pas le cas, dans Microsoft Edge, accédez au portail Microsoft Purview, `https://purview.microsoft.com`, et connectez-vous. Une fois connecté, sélectionnez la carte **Gestion du cycle de vie des données** > **Stratégies** > **Stratégies de rétention**.

1. Sélectionnez **+ Nouvelle stratégie de rétention**.
1. Sur la page **Nommer votre stratégie de rétention**, saisissez le nom et la description :

   - **Nom :** `Teams Retention`
   - **Description** : `Retention for Teams locations`

1. Cliquez sur **Suivant**.
1. Sur la page **Étendue de la stratégie**, sélectionnez **Suivant**.
1. Sur la page **Choisir le type de stratégie de rétention à créer**, sélectionnez **Statique**, puis **Suivant**.
1. Dans la section Choisir les emplacements pour appliquer la stratégie, activez :

   - Messages des canaux Teams
   - Conversations Teams et interactions Copilot

   Vérifiez que toutes les autres options sont désactivées.

1. Pour l’emplacement **Conversations Teams et interactions Copilot**, sélectionnez le lien **Modifier** sous **Tous les utilisateurs** et ajoutez deux utilisateurs.

    >![Capture d’écran montrant l’option Ajouter des utilisateurs pour les conversations Teams et les interactions Copilot.](./Media/add-users-retention-policy.png)

1. Sur la page volante **Conversations Teams et interactions Copilot**, une fois que les utilisateurs sont ajoutés, sélectionnez **Terminé**, puis **Suivant**.
1. Sur la page **Décider si vous voulez conserver du contenu, le supprimer ou les deux**, saisissez :
   - **Conserver les éléments pendant une période spécifique** : choisissez **Personnalisé** dans la liste déroulante.
   - Définissez le champ des années sur 3.
   - **Démarrer la période de rétention en fonction de** : Quand les éléments ont été modifiés pour la dernière fois.

1. Cliquez sur **Suivant**.
1. Sur la page **Vérifier et terminer**, sélectionnez **Envoyer**.
1. Une fois votre stratégie créée, sélectionnez **Terminé**.

Vous avez créé une stratégie de rétention pour les emplacements Teams avec une période de rétention de trois ans, en appliquant un filtre pour des utilisateurs spécifiques.

## Tâche 3 : créer une stratégie de rétention via PowerShell

Dans cette tâche, vous allez utiliser PowerShell pour créer et gérer des stratégies de rétention.

1. Ouvrez une fenêtre PowerShell avec des privilèges élevés.
1. Saisissez la cmdlet suivante pour installer la dernière version du module PowerShell Exchange Online :

    ```powershell
    Install-Module ExchangeOnlineManagement
    ```

1. Confirmez la boîte de dialogue de sécurité du fournisseur NuGet en appuyant sur **Y** pour Oui, puis appuyez sur **Entrée**. Ce processus peut prendre un certain temps.
1. Confirmez la boîte de dialogue de sécurité du référentiel non approuvé en appuyant sur **Y** pour Oui, puis appuyez sur **Entrée**.  Ce processus peut prendre un certain temps.
1. Saisissez la cmdlet suivante pour modifier votre stratégie d’exécution, puis appuyez sur **Entrée**. La commande suppose que vous êtes connecté en tant qu’utilisateur disposant des autorisations appropriées.

    ```powershell
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
    ```

1. Confirmez les modifications de la stratégie d’exécution en appuyant sur **Y** pour Oui, puis appuyez sur **Entrée**.
1. Fermez la fenêtre PowerShell.
1. Ouvrez une fenêtre PowerShell normale, sans élévation, en sélectionnant le bouton Windows avec le bouton droit de la souris et en sélectionnant **Windows PowerShell**.
1. Connectez-vous au Centre de sécurité et de conformité dans votre locataire avec la cmdlet suivante :

    ```powershell
    Connect-IPPSSession
    ```

1. Lorsque vous y êtes invité, connectez-vous en tant qu’utilisateur disposant des autorisations appropriées.
1. Exécutez la cmdlet suivante pour créer la première stratégie de rétention pour tous les emplacements à l’exception de Teams :

    ```powershell
    New-RetentionCompliancePolicy -Name "Company Wide PS" -ExchangeLocation All -ModernGroupLocation All -SharePointLocation All -OneDriveLocation All
    ```

1. Exécutez la cmdlet suivante pour définir la période de rétention, en utilisant les jours comme unités selon la date de modification :

    ```powershell
    New-RetentionComplianceRule -Name "Company Wide PS Rule" -Policy "Company Wide PS" -RetentionDuration 1095 -ExpirationDateOption ModificationAgeInDays -RetentionComplianceAction Keep
    ```

Vous avez créé des stratégies de rétention via PowerShell avec une période de rétention de trois ans.

<!--- Commenting out until adaptive scope issue is resolved

## Task 4 – Create retention policy with adaptive scope

Here, you will create a retention policy with adaptive scope targeting specific departments like Legal and Retail.

1. In Microsoft Edge, navigate to the Microsoft Purview portal, `https://purview.microsoft.com`, and log in.
1. Select **Settings** from the left navigation bar.
1. Expand **Roles and scopes** then select **Adaptive scopes**.
1. On the **Adaptive scopes** page select **+ Create scope**.
1. On the **Name your adaptive policy scope page**, enter:

   - **Name**: `Legal Documents Retention`
   - **Description**: `Retention for legal related documents`

1. Select **Next**.
1. On the **Assign admin unit page**, select **Next**.
1. On the **What type of scope do you want to create?** page, select **Users** and then **Next**.
1. On the **Create the query to define users** page, under **User attributes**, select:

   - **Attribute**: Department
   - **Operator**: is equal to
   - **Value**: `Legal`

1. Add a second attribute by selecting the **+ Add attribute** button with values:

   - **Query operator**: Or
   - **Attribute**: Department
   - **Operator**: is equal to
   - **Value**: `Retail`

    >![Screenshot showing the query to define users values.](./Media/query-to-define-users.png)

1. Select **Next** and then **Submit** on the **Review and finish** page.
1. Once your scope has been created select **Done** to get back to the **Adaptive scopes** page.
1. Select **Solutions** > **Data Lifecycle Management**.
1. Expand **Policies** then select **Retention policies**.
1. On the **Retention policies** page select **+ New retention policy**.
1. On the **Name your retention policy page**, enter:

   - **Name**: `Legal Data Retention`
   - **Description**: `Retention of all documents within the legal and retail departments.`

1. Select **Next**.
1. On the **Policy Scope** page, select **Next**.
1. On the **Choose the type of retention policy to create** page, select **Adaptive** and then **Next**.
1. On the **Choose adaptive policy scopes and locations** page, select **+ Add scopes** and choose the **Legal Documents Retention** scope.
1. Under **Choose locations to apply the policy** enable:

   - Exchange mailboxes
   - OneDrive accounts

1. Select **Next**.
1. On the **Decide if you want to retain content, delete it, or both** page, enter:

   - **Retain items for a specific period**: 5 years
   - **Start the retention period based on**: When items were created
   - **At the end of the retention period**: Do nothing

1. Select **Next** and then **Submit** on the **Review and finish**.
1. Once your policy is created, select **Done**.

You have successfully applied an adaptive scope to a retention policy.

--->
