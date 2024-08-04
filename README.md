# Pour accorder des autorisations à un script Codespace pour écrire sur GitHub, vous devrez suivre les étapes ci-dessous :

- Créez un compte GitHub si vous ne l'avez pas déjà fait.
- Sur votre compte GitHub, créez un "GitHub App" (vous pouvez trouver cette option dans le menu déroulant de gauche en haut de la page) et nommez-le (par exemple, "Codespace Script").
- Configurez les autorisations pour votre application GitHub :
- Sélectionnez "Authorization" > "Read and write: repositories".
- Ajoutez les "Repositories" que vous souhaitez que l'application puisse modifier.
- Copiez le "Client Secret" généré lors de la création de l'application GitHub. Vous ne pourrez pas récupérer ce code ultérieurement, donc assurez-vous de le copier maintenant.
- Maintenant, sur Codespace :

- Ouvrez votre Codespace et créez un fichier settings.json dans le dossier racine de votre projet.
- Ajoutez les lignes suivantes au fichier settings.json :
  
1 - ▶️

```bash
{
  "octokit": {
    "client_id": "<votre_client_id>",
    "client_secret": "<votre_client_secret>"
  }
}
```
- Remplacez <votre_client_id> et <votre_client_secret> par les valeurs que vous avez générées lors de la création de votre application GitHub précédemment.

- Installez l'extension "Octokit" (SDK GitHub) en ajoutant la ligne suivante dans votre fichier codespace.yml :
  
2 - 🍫

```bash
packages:
  - octokit@latest
```
- Redémarrez votre Codespace pour que les modifications prennent effet.
- Vous pouvez maintenant utiliser l'extension Octokit dans votre Codespace pour interagir avec votre dépôt GitHub et effectuer des opérations comme la création, la mise à jour ou la suppression de fichiers.
- N'oubliez pas de sauvegarder et de déployer vos modifications pour voir les changements reflétés sur votre dépôt GitHub.

