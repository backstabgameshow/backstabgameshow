# Backstab Website

Loyalty is a liability.

## File Structure
```
backstab-site/
├── index.html          # Homepage with how-to-play video
├── socials.html        # Discord + YouTube links + contact email
├── casting.html        # Three-step application form
├── styles.css          # All site styles
└── assets/
    ├── backstab-logo.png    # Full wordmark with dagger+snake
    ├── backstab-mark.png    # Standalone dagger+snake (favicon)
    └── dagger.png           # Spare dagger asset
```

## Before You Deploy: Set Up Form Submissions

The casting form currently won't deliver submissions until you add a Web3Forms access key. It's free and takes about 60 seconds.

1. Go to **https://web3forms.com**
2. Click "Create Access Key"
3. Enter `backstabgameshow@gmail.com` (the email you want submissions sent to)
4. Check your inbox and verify the email
5. Copy your access key
6. Open `casting.html` and find this line near the top of the `<form>` element:
   ```html
   <input type="hidden" name="access_key" value="YOUR_ACCESS_KEY_HERE" />
   ```
7. Replace `YOUR_ACCESS_KEY_HERE` with your actual key

That's it. Submissions will now arrive at `backstabgameshow@gmail.com`.

## Deploying to GitHub Pages

1. Create a new GitHub repository (public). Name it whatever you want — e.g. `backstab-site`.
2. Upload all the files in this folder to the repo (including the `assets/` folder).
3. In the repo, go to **Settings → Pages**.
4. Under "Source," select **Deploy from a branch**.
5. Branch: `main`, folder: `/ (root)`. Save.
6. Wait 1–2 minutes. Your site will be live at:
   `https://YOUR-USERNAME.github.io/backstab-site/`

## When You Buy a Custom Domain

1. Buy from Cloudflare, Porkbun, or Namecheap (~$10/year).
2. In your GitHub repo: **Settings → Pages → Custom domain** — enter your domain.
3. At your domain registrar, add DNS records pointing to GitHub Pages:
   - Four `A` records pointing to: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - Or one `CNAME` record pointing to `YOUR-USERNAME.github.io`
4. Check "Enforce HTTPS" once it's available (usually within an hour).

## Updating Content Later

- **Change the how-to-play video:** In `index.html`, find the `<iframe>` and replace the YouTube ID (`8tZRFYnSZ58`) with the new one.
- **Change social links:** Edit the `href` values in `socials.html`.
- **Update eligibility requirements:** Edit the `<ul class="requirements">` list in `casting.html`.
- **Tweak colors:** Edit the CSS variables at the top of `styles.css` (`--gold`, `--ink`, etc).
