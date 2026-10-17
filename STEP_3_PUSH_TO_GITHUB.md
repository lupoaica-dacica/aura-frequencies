# STEP 3: Commit and Push to GitHub

## Option A: Command Line (Recommended)

### Prerequisites
- Git must be installed: https://git-scm.com/download/win
- GitHub credentials ready

### Commands to Run

Open PowerShell in your project directory:

```powershell
cd "C:\Users\lupoa\source\repos\lupoaica-dacica\aura-frequencies"

# Check current status
git status

# Add all new and modified files
git add .

# Commit with message
git commit -m "Configure deployment for Azure Static Web Apps

- Add DEPLOYMENT_GUIDE.md with complete deployment instructions
- Add GitHub Actions workflow for CI/CD
- Update vite.config.ts for Windows/VS compatibility
- Ready for Azure deployment"

# Push to GitHub
git push origin main

# Verify success
git log --oneline -n 3
```

Expected output after `git push`:
```
To https://github.com/lupoaica-dacica/aura-frequencies.git
   abc123..def456  main -> main
```

---

## Option B: Visual Studio Code

If you have VS Code installed:

1. Open project in VS Code
```powershell
code "C:\Users\lupoa\source\repos\lupoaica-dacica\aura-frequencies"
```

2. **Source Control Panel** (Left sidebar, Ctrl+Shift+G)
   - View changed files
   - Click **+** to stage files
   - Or click "Stage All Changes"

3. **Commit Message Box**
   - Enter commit message (see below)
   - Press Ctrl+Enter OR click Commit button

4. **Push to GitHub**
   - Click **...** menu → Push

---

## Option C: GitHub Desktop

If you have GitHub Desktop:

1. Open GitHub Desktop
2. Select repository "aura-frequencies"
3. Left panel shows changed files (should show ~3 new files)
4. Click **"Stage all changes"**
5. Bottom-left: Enter commit message (see below)
6. Click **"Commit to main"**
7. Top menu: Click **"Push origin"**

---

## Suggested Commit Message

```
Configure deployment for Azure Static Web Apps

- Add DEPLOYMENT_GUIDE.md with complete deployment instructions
- Add GitHub Actions workflow for CI/CD automation
- Update vite.config.ts with Windows/VS file watching compatibility
- Add STEP_2_AZURE_PORTAL_SETUP.md guide for Azure setup
- Add STEP_3_PUSH_TO_GITHUB.md documentation
```

---

## What Gets Pushed

New/Modified files:
- ✅ `DEPLOYMENT_GUIDE.md` - Complete deployment guide
- ✅ `.github/workflows/azure-static-web-apps-deploy.yml` - CI/CD workflow
- ✅ `STEP_2_AZURE_PORTAL_SETUP.md` - Azure setup guide
- ✅ `STEP_3_PUSH_TO_GITHUB.md` - This file
- ✅ `vite.config.ts` - Updated with watch config

NOT pushed:
- ❌ `node_modules/` - Already in .gitignore
- ❌ `dist/` - Build output
- ❌ `.vs/` - Visual Studio cache

---

## Verify Push Succeeded

### Method 1: Command Line
```powershell
git log --oneline -n 1
```

Should show your commit message

### Method 2: GitHub Website
1. Go to https://github.com/lupoaica-dacica/aura-frequencies
2. Click **"<> Code"** tab
3. Should show your commit message at the top
4. Check file count increased

### Method 3: GitHub Actions
1. Open https://github.com/lupoaica-dacica/aura-frequencies/actions
2. Should see workflow running automatically!
3. Status shows "in progress" or "completed"

---

## Troubleshooting git Push

### Issue: "Git not recognized"
```powershell
# Solution: Install Git for Windows
# https://git-scm.com/download/win
# Then restart PowerShell
```

### Issue: "Permission denied (publickey)"
```powershell
# Solution: Generate SSH key or use HTTPS
# Option 1: Use HTTPS instead
git remote set-url origin https://github.com/lupoaica-dacica/aura-frequencies.git

# Option 2: GitHub Personal Access Token
# Settings → Developer settings → Personal access tokens
# Paste token when prompted for password
```

### Issue: "Nothing to commit"
```powershell
# Solution: Files might be already committed
git status  # Check what's new
git add -A  # Add everything
git commit -m "Your message"
```

### Issue: "Rejected: non-fast-forward"
```powershell
# Solution: Pull latest changes first
git pull origin main
git push origin main
```

---

## Next: Monitor GitHub Actions

Once push succeeds, GitHub Actions automatically:
1. ✅ Detects changes to `main` branch
2. ✅ Starts workflow (see in Actions tab)
3. ✅ Installs Node.js 18
4. ✅ Runs `npm run build`
5. ✅ Deploys to Azure using deployment token

**Timeline:** 3-5 minutes

---

## Quick Checklist

- [ ] Git installed on system
- [ ] In correct directory: `aura-frequencies`
- [ ] Run `git status` - shows new files
- [ ] Run `git add .`
- [ ] Run `git commit -m "..."`
- [ ] Run `git push origin main`
- [ ] Check GitHub website - commit appears
- [ ] Check Actions tab - workflow running

---

## ⏭️ NEXT STEP

→ Go to **STEP 4** to add deployment token to GitHub Secrets
→ Then watch **STEP 5** for live deployment!
