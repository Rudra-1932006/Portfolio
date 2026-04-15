# 🚀 Rudra Dabhi — Portfolio
**Hosted on GitHub Pages · Custom domain via DuckDNS · Emails via EmailJS**

Everything is **2 files** — `index.html` and `CNAME`. No server, no build step.

---

## 📁 What you push to GitHub

```
your-repo/
├── index.html   ← Your entire portfolio
└── CNAME        ← Your custom domain
```

---

## ⚡ Setup Guide (follow in order)

---

### STEP 1 — Set up EmailJS (so the contact form sends emails)

1. Go to **https://www.emailjs.com** → Create a free account
2. **Add Email Service:**
   - Dashboard → **Email Services** → **Add New Service**
   - Choose **Gmail** → Connect your Gmail account (`rudradabhi29@gmail.com`)
   - Note the **Service ID** (e.g. `service_abc123`)

3. **Create Email Template:**
   - Dashboard → **Email Templates** → **Create New Template**
   - Set **To Email** → your Gmail address
   - Paste this template body:
     ```
     New message from {{from_name}} ({{from_email}})
     Subject: {{subject}}

     {{message}}
     ```
   - Save it. Note the **Template ID** (e.g. `template_xyz789`)

4. **Get your Public Key:**
   - Dashboard → **Account** → **General** tab
   - Copy the **Public Key**

5. **Update `index.html`** — find these 3 lines near the top and replace the placeholder values:
   ```js
   const EMAILJS_PUBLIC_KEY  = 'YOUR_PUBLIC_KEY';    // ← paste here
   const EMAILJS_SERVICE_ID  = 'YOUR_SERVICE_ID';    // ← paste here
   const EMAILJS_TEMPLATE_ID = 'YOUR_TEMPLATE_ID';   // ← paste here
   ```

---

### STEP 2 — Push to GitHub

```bash
# Create a new repo on github.com first, then:
git init
git add index.html CNAME
git commit -m "Initial portfolio"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

---

### STEP 3 — Enable GitHub Pages

1. Go to your repo on GitHub
2. **Settings** → **Pages** (left sidebar)
3. Under **Source** → select **Deploy from a branch**
4. Branch: **main** / Folder: **/ (root)**
5. Click **Save**

GitHub will give you a URL like `https://yourusername.github.io/your-repo`
Wait 1–2 minutes for it to go live.

---

### STEP 4 — Set up DuckDNS (free custom domain)

1. Go to **https://www.duckdns.org** → Log in with GitHub/Google
2. In the **domain** box, type your chosen name (e.g. `rudradabhi`) → click **add domain**
3. You now have `rudradabhi.duckdns.org`
4. In the **current ip** field for your domain, enter GitHub Pages' IP addresses one by one.
   GitHub Pages IPs (enter all four):
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```
   *(DuckDNS only stores one IP — use the first one: `185.199.108.153`)*

---

### STEP 5 — Connect DuckDNS domain to GitHub Pages

1. Back in your repo → **Settings** → **Pages**
2. Under **Custom domain** → type `rudradabhi.duckdns.org` → click **Save**
3. Check **Enforce HTTPS** (may take a few minutes to appear)
4. Update the `CNAME` file to match your chosen subdomain:
   ```
   rudradabhi.duckdns.org
   ```

Wait 5–15 minutes for DNS to propagate. Then visit `https://rudradabhi.duckdns.org` 🎉

---

## 🔄 Making Updates Later

Just edit `index.html` and push:

```bash
git add index.html
git commit -m "Update portfolio"
git push
```

GitHub Pages auto-deploys on every push. Changes go live in ~1 minute.

---

## ✅ Checklist

- [ ] EmailJS account created and keys filled in `index.html`
- [ ] Repo pushed to GitHub
- [ ] GitHub Pages enabled (main branch)
- [ ] DuckDNS domain created and pointed to `185.199.108.153`
- [ ] Custom domain set in GitHub Pages settings
- [ ] HTTPS enforced
- [ ] Test the contact form — you should receive an email

---

**Made with ☕ by Rudra Dabhi · BSc. IT · KES Shroff College, Mumbai**
