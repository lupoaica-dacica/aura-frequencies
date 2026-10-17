# STEP 2: Create Azure Static Web App - Detailed Guide

## 🔗 Start Here: https://portal.azure.com

---

## Step-by-Step Instructions

### 1️⃣ Click "Create a resource"

**Location:** Top-left corner of Azure Portal
```
OR Search bar → Type "Static Web App"
```

---

### 2️⃣ Search for "Static Web App"

- In the search box, type: **Static Web App**
- Click the matching result

---

### 3️⃣ Click "Create"

- Click the blue **"Create"** button

---

### 4️⃣ Basics Tab - Fill in Project Details

```
SUBSCRIPTION:         Select your subscription
RESOURCE GROUP:       (Create new or select existing)
					  Recommended name: aura-frequencies-rg

NAME:                 aura-frequencies
					  (Must be globally unique)

PLAN TYPE:            Free (recommended for learning)

REGION:               Select closest to your location
					  Examples: East US, West US 2, Central US
```

---

### 5️⃣ Sign in with GitHub

```
Click: "Sign in with GitHub"

You'll be redirected to GitHub login.
```

**What it asks:**
- GitHub username/email
- GitHub password
- GitHub 2FA code (if enabled)

Click **"Authorize AzureStaticWebApps"**

---

### 6️⃣ Configure GitHub Repository

```
ORGANIZATION:         lupoaica-dacica
REPOSITORY:           aura-frequencies
BRANCH:               main
```

---

### 7️⃣ Click "Next: Build >"

Move to Build configuration tab

---

### 8️⃣ Build Configuration Tab

```
BUILD PRESETS:        Select "Custom"
					  (Not Node.js, but Custom)

APP LOCATION:         .
					  (Current directory/root)

API LOCATION:         (Leave empty - no API)

BUILD OUTPUT LOCATION: dist
					  (Where Vite outputs build)
```

⚠️ **IMPORTANT:** If you see "Building output location", make sure it's **dist** not **build**

---

### 9️⃣ Review Tab

- Review all settings
- Verify GitHub repository is correct
- Verify branch is **main**
- Verify build output location is **dist**

Click **"Create"**

---

### 🔟 Deployment Started!

Azure will:
1. Create the Static Web App resource
2. Create GitHub Actions workflow automatically
3. Trigger first deployment from your repository
4. Start building your app

**Wait 2-3 minutes for deployment to complete**

---

## ✅ After Creation - Get Your Deployment Token

### 1. Go to Your Static Web App

- Portal Home → Your Static Web App (aura-frequencies)
- OR Search "aura-frequencies" in search bar

### 2. Copy Deployment Token

```
Left sidebar → "Manage deployment token"
OR
Settings → "Deployment tokens"
```

Copy the entire token (starts with: SharedAccessSignature or similar)

---

## 🌐 Your Live URL

Once deployment completes:

```
https://aura-frequencies-[random].azurestaticapps.net
```

You'll see this in:
- Azure Portal → Overview → URL
- GitHub Actions → Deployment logs

---

## Troubleshooting During Creation

### Issue: "Repository name not found"
- ✅ Make sure GitHub is signed in
- ✅ Check spelling: `lupoaica-dacica` (with dashes)
- ✅ Verify you have access to the repository

### Issue: "Invalid build output location"
- ✅ Must be **dist** (case-sensitive on Linux)
- ✅ Not **build** or **public**

### Issue: "Name already taken globally"
- ✅ Use different name: aura-frequencies-[yourname]
- ✅ Names must be unique across all Azure regions

---

## Next Steps After Creation

1. ✅ Copy deployment token (from Step 2 above)
2. ⏳ Wait for first deployment to complete (GitHub Actions)
3. 🔗 Get your live URL from Azure Portal
4. 🚀 Share your PWA with the world!

---

## Estimated Timeline

| Step | Time |
|------|------|
| Fill out form | 2-3 min |
| GitHub auth | 1 min |
| Azure setup | 1 min |
| First deployment | 3-5 min |
| **Total** | **7-10 min** |

---

## ⏭️ Once Complete

→ Go to **STEP 3** in the deployment process
