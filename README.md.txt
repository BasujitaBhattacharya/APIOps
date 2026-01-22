# APIOps Repo Setup (Initialize & Push to GitHub)

## Prerequisites
- **Git** installed
- A **GitHub repository URL** ready (example: `https://github.com/<your-username>/<repo>.git`)

## Steps

1. **Download** the GitHub APIOps contents.
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