# STEP 4: Add Deployment Token to GitHub Secrets

## 🔑 What is the Deployment Token?

Azure generates a secure token that allows GitHub Actions to deploy your app. It's kept secret in GitHub.

---

## Step 1: Get Deployment Token from Azure

### 1. Go to Azure Portal
```
https://portal.azure.com
```

### 2. Find Your Static Web App
```
Search: "aura-frequencies"
Click on the resource
```

### 3. Get the Token

**Option A: Manage deployment token (Recommended)**
```
Left sidebar → "Manage deployment token"
```

**Option B: Via Settings**
```
Left sidebar → Settings → "Deployment tokens"
```

### 4. Copy the Token
```
Click "Copy deployment token"
(Token starts with: SharedAccessSignature=...)
```

⚠️ **IMPORTANT:** Keep this token SECRET!
- Don't share it
- Don't commit it to Git
- Only store in GitHub Secrets

---

## Step 2: Add Token to GitHub Secrets

### 1. Go to Repository Settings
```
https://github.com/lupoaica-dacica/aura-frequencies
```

### 2. Go to Secrets

**Left sidebar:**
```
Settings
  └─ Secrets and variables
	 └─ Actions
```

OR Direct URL:
```
https://github.com/lupoaica-dacica/aura-frequencies/settings/secrets/actions
```

### 3. Create New Secret

Click **"New repository secret"**

### 4. Fill in Secret Details

**Name (exactly):**
```
AZURE_STATIC_WEB_APPS_API_TOKEN
```

**Secret (paste from Azure):**
```
SharedAccessSignature=... (entire token)
```

### 5. Click "Add secret"

---

## Verification

### 1. Check Secret Added
```
Settings → Secrets and variables → Actions
```

Should see:
```
✓ AZURE_STATIC_WEB_APPS_API_TOKEN  Updated recently
```

### 2. Verify GitHub Actions Can See It
```
GitHub Actions workflow will use it automatically
(You won't see the actual value for security)
```

---

## 🔄 GitHub Actions Workflow Uses This Token

In `.github/workflows/azure-static-web-apps-deploy.yml`:

```yaml
with:
  azure_static_web_apps_api_token: ${{ secrets.AZURE_STATIC_WEB_APPS_API_TOKEN }}
```

This securely passes the token during deployment.

---

## Troubleshooting

### Issue: "Cannot find secret credentials"
- ✅ Check secret name is exactly: `AZURE_STATIC_WEB_APPS_API_TOKEN`
- ✅ Verify you're in correct repository
- ✅ Verify you have admin access to repository

### Issue: "Deployment still fails after adding token"
- ✅ Ensure token is complete (copy entire thing from Azure)
- ✅ Token might have expired - get new one from Azure
- ✅ Check GitHub Actions logs for specific error message

### Issue: "Cannot see secret in workflow"
- ✅ Secrets are hidden by design
- ✅ Workflow can access them, but you cannot view them
- ✅ Use `echo "Token set: ${TOKEN}"` in logs if you need to debug

---

## 🔐 Security Best Practices

✅ DO:
- Keep token in GitHub Secrets only
- Rotate token periodically
- Use separate tokens for development and production
- Log which repositories use the token

❌ DON'T:
- Commit token to repository
- Paste token in emails
- Share token with team members
- Use same token for multiple projects

---

## Token Expires?

If deployment fails:

1. Go to Azure Portal → Your Static Web App
2. Click "Manage deployment token"
3. Click "Generate new token"
4. Copy new token
5. Update GitHub Secret: Settings → Secrets → AZURE_STATIC_WEB_APPS_API_TOKEN

---

## ⏭️ NEXT STEP

→ Go to **STEP 5** to monitor deployment and get your live URL!
