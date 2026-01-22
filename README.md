# APIOps Repo Setup (Initialize & Push to GitHub)

## Prerequisites
- **Git** installed from [here](https://git-scm.com/install/windows)
- **Azure CLI** installed from [here](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows?view=azure-cli-latest&pivots=winget#winget-windows-package-manager)
- A **GitHub repository URL** ready (example: `https://github.com/<your-username>/<repo>.git`)

## Steps

1. **Download** the GitHub APIOps release contents from here https://github.com/Azure/apiops/releases.
2. **Extract** the ZIP and **delete** the ZIP file.
3. Open a terminal and navigate to the folder that contains the **`.github`** folder.

   Example path:
   ```txt
   C:\Users\<YourUser>\APIOps\GitHub>
   ```

## Initialize the repo and push

Run the commands below from inside the folder:

```bash
git init
git branch -M main
git add .
git commit -m "Adding workflow files"
git remote add origin https://github.com/<your-username>/<repo>.git
git push -u origin main
```

## Login to Azure

1. Run the commands below from inside the folder:

```bash
az login
```
2. Use your azure login credentials and select subscription.
3. Create 2 service principles with different names for dev and prod
   
```bash
az ad sp create-for-rbac -n "apiopslabdev" --role Contributor --scopes /subscriptions/{subscription-id}/resourceGroups/{dev-resource-group} --sdk-auth
az ad sp create-for-rbac -n "apiopslabprod" --role Contributor --scopes /subscriptions/{subscription-id}/resourceGroups/{prod-resource-group} --sdk-auth
```


## Notes
- If you see `error: remote origin already exists`, remove it and add again:
  ```bash
  git remote remove origin
  git remote add origin https://github.com/<your-username>/<repo>.git
  ```
  Or just update the URL:
  ```bash
  git remote set-url origin https://github.com/<your-username>/<repo>.git
  ```
