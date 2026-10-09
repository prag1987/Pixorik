# Pixorik ko live karna (pixorik.com)

Site ek simple static website hai (index.html + assets), isliye free hosting kaafi hai.
Domain Hostinger se liya hai — hosting GitHub Pages par hogi, Hostinger me sirf DNS set karna hai.

> Agar aapka domain `pixorik.com` nahi hai, to `CNAME` file me apna exact domain likh dein.

## Step 1 — Code `main` branch par laayein
Is branch (`claude/quirky-wright-ikx8e7`) ko `main` me merge karein. Workflow sirf `main` par chalta hai.

## Step 2 — Repo public karein (ya GitHub Pro lein)
Repo abhi **private** hai. Free GitHub account par Pages sirf public repo par chalta hai.
GitHub → Repo → Settings → General → sabse neeche "Danger Zone" → **Change visibility → Public**.
(Private hi rakhna hai to neeche "Option B: Netlify" dekhein.)

## Step 3 — GitHub Pages on karein
Repo → Settings → **Pages** → Build and deployment → Source: **GitHub Actions**.
Phir Actions tab me "Deploy to GitHub Pages" run hone dein (ya "Run workflow" dabayein).

## Step 4 — Hostinger DNS
Hostinger hPanel → **Domains → pixorik.com → DNS / Nameservers → DNS records**.
Pehle purane `A` record (`@`) aur `CNAME` (`www`) jo Hostinger parking ki taraf point karte hain, delete karein. Phir ye add karein:

| Type  | Name | Points to            | TTL  |
|-------|------|----------------------|------|
| A     | @    | 185.199.108.153      | 3600 |
| A     | @    | 185.199.109.153      | 3600 |
| A     | @    | 185.199.110.153      | 3600 |
| A     | @    | 185.199.111.153      | 3600 |
| CNAME | www  | prag1987.github.io   | 3600 |

(Optional IPv6: AAAA @ → 2606:50c0:8000::153, 2606:50c0:8001::153, 2606:50c0:8002::153, 2606:50c0:8003::153)

## Step 5 — Domain + HTTPS
Settings → Pages → Custom domain: `pixorik.com` → Save. DNS check green hone ke baad
**Enforce HTTPS** tick karein. DNS propagate hone me 10 min se 24 ghante lag sakte hain.

Check: https://pixorik.com aur https://www.pixorik.com dono khulne chahiye.

---

## Option B: Netlify (repo private rakhna ho to)
1. netlify.com → Sign up with GitHub → **Add new site → Import from Git** → `prag1987/Pixorik`, branch `main`.
   Build command khali, Publish directory `.` → Deploy.
2. Site settings → **Domain management → Add domain** → `pixorik.com`.
3. Hostinger DNS me: `A @ → 75.2.60.5` aur `CNAME www → <aapki-site>.netlify.app`.
4. Netlify khud free HTTPS certificate laga dega.
(Is option me `.github/workflows/pages.yml` ki zaroorat nahi — chahein to delete kar dein.)
