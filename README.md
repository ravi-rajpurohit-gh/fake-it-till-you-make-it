# fake-it-till-you-make-it

This project automates Git commits and pushes using **GitHub Actions**, ensuring that your GitHub profile remains active by making daily commits. This can help simulate developer activity on your profile.

## Features

- **Automated Daily Commits**: Updates a log file with the current date every day.
- **Uses GitHub Actions**: Runs without needing your local machine.
- **Customizable Schedule**: Modify the cron job to adjust commit frequency.

## 🛠️ Setup Instructions

### 1️⃣ **Fork or Clone This Repository**

```bash
 git clone https://github.com/your-username/fake-it-till-you-make-it.git
 cd fake-it-till-you-make-it
```

### 2️⃣ **Create a Personal Access Token (PAT)**

1. Go to **[GitHub Personal Access Tokens](https://github.com/settings/tokens)**
2. Click **"Generate new token (classic)"** → Select **"Fine-grained token"**
3. **Repository Access**: Select this repo
4. **Permissions**:
   - `Contents`: Read & Write
   - `Workflows`: Read & Write
5. Click **Generate Token** and copy it.

### 3️⃣ **Add the PAT as a GitHub Secret**

1. Navigate to your repository on GitHub.
2. Go to **Settings → Secrets and Variables → Actions**.
3. Click **New repository secret**.
4. **Name**: `GH_PAT`
5. **Value**: Paste your copied token.
6. Click **Save**.

### 4️⃣ **Set Up GitHub Actions Workflow**

The automation is controlled by `.github/workflows/activity.yml`.
Modify the schedule as needed:

```yaml
schedule:
  - cron: "0 12 * * *" # Runs daily at 12 PM UTC
```

To trigger manually, go to **Actions tab → Select workflow → Run workflow**.

### 5️⃣ **Commit and Push Changes**

```bash
git add .github/workflows/activity.yml
git commit -m "Setup GitHub Activity Automation"
git push origin main
```

## ✅ How It Works

- The workflow runs daily and appends the current date to `activity.log`.
- It commits and pushes the change using the provided GitHub token.
- This keeps your GitHub profile active with automated commits.

## 🔧 Customization

- **Adjust the commit frequency**: Modify the `cron` schedule in `activity.yml`.
- **Modify commit messages**: Change the commit message inside the workflow file.
- **Commit different files**: Instead of `activity.log`, modify other files.
