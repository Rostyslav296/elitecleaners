# Elite Cleaners Website

Professional cleaning company website hosted on GitHub Pages.

**Live URL:** https://rostyslav296.github.io/elitecleaners/

## Website Architecture

```
elitecleaners/
├── index.html          Home page (hero, services, pricing, CTA)
├── contact.html        Contact info + email form (Web3Forms)
├── social.html         Social media link cards
├── reviews.html        Customer testimonials
├── photos.html         Photo gallery with lightbox viewer
├── css/
│   └── styles.css      All styles (colors, layout, responsive)
├── js/
│   └── main.js         Navigation, contact form, photo lightbox
├── images/
│   └── photos/         Gallery images go here
└── README.md           This file
```

## How to Update the Website

All updates follow the same 3-step process:

```bash
# 1. Make your edits to the files (see sections below)
# 2. Stage and commit your changes
git add .
git commit -m "Brief description of what you changed"
# 3. Push to GitHub (site updates automatically)
git push
```

Your site typically updates within 1-2 minutes after pushing.

---

### Update Prices

Open `index.html` and find the `PRICING SECTION` comment. Each price is in a `<td>` tag:

```html
<tr><td>Studio / 1 Bedroom</td><td>$75</td></tr>
```

Change `$75` to your new price. Save, commit, push.

### Add a Photo

1. Put your image in the `images/photos/` folder (JPEG recommended, max 1200px wide)
2. Open `photos.html` and add a new block inside `<div class="photo-gallery">`:

```html
<figure class="gallery-item">
    <img src="images/photos/your-photo.jpg" alt="Description of the photo" loading="lazy">
    <figcaption>Caption shown below the photo</figcaption>
</figure>
```

3. Save, commit, push.

### Add a Customer Review

Open `reviews.html` and copy an existing review card. Paste it inside the `<div class="reviews-grid">` and edit the text:

```html
<div class="review-card">
    <div class="review-stars">★★★★★</div>
    <p class="review-text">"Their review text here."</p>
    <p class="review-author">&mdash; Customer Name</p>
    <span class="review-badge">Airbnb Turnover</span>
</div>
```

Badge options: `Airbnb Turnover`, `Office Cleaning`, `Hotel Cleaning`, `Commercial Cleaning`, `Deep Clean`

### Add or Change Social Media Links

Open `social.html`. Each social platform is an `<a>` block. Change the `href` URL:

```html
<a href="https://facebook.com/YOUR-ACTUAL-PAGE" target="_blank" ...>
```

To remove a platform, delete the entire `<a>...</a>` block.

### Change Contact Info

Search across all `.html` files for the phone number `(864) 824-1536` or email `elitecleaners1@icloud.com` and replace with new info. These appear in the header area of `contact.html` and in the footer of every page.

---

## Contact Form Setup (Web3Forms)

The contact form sends emails using [Web3Forms](https://web3forms.com/) (free, 250 submissions/month).

**To activate the form:**

1. Go to https://web3forms.com
2. Enter your email: `elitecleaners1@icloud.com`
3. Check your email for the access key
4. Open `contact.html` and find this line:
   ```html
   <input type="hidden" name="access_key" value="YOUR_ACCESS_KEY_HERE">
   ```
5. Replace `YOUR_ACCESS_KEY_HERE` with your actual key
6. Commit and push

## Custom Domain (Optional)

If you purchase a domain (e.g., `elitecleanerstn.com`):

1. Create a file called `CNAME` in the project root containing just the domain:
   ```
   elitecleanerstn.com
   ```
2. At your domain registrar, add these DNS records:
   - A record: `185.199.108.153`
   - A record: `185.199.109.153`
   - A record: `185.199.110.153`
   - A record: `185.199.111.153`
   - CNAME record: `www` → `rostyslav296.github.io`
3. In GitHub repo Settings > Pages, add your custom domain and enable HTTPS
4. Commit and push

## Tech Stack

- Pure HTML, CSS, JavaScript (no frameworks)
- Google Fonts (Montserrat + Open Sans)
- Web3Forms for contact form emails
- GitHub Pages for free hosting
