# Personal Academic Website

A Song Dynasty aesthetic personal academic site for Anqi Zhang, built as a single static HTML page for deployment via GitHub Pages.

## Quick Deploy (Three Steps)

### 1. Create the repository

The cleanest URL on GitHub Pages comes from a user-named repository. If your GitHub username is `azhang`, name your repository exactly `azhang.github.io`. Your site will then live at `https://azhang.github.io`.

If you want a project-style URL instead (such as `azhang.github.io/website`), name the repository anything you like.

To create:

1. Go to [github.com/new](https://github.com/new)
2. Name the repository as described above
3. Set it to **Public** (GitHub Pages requires public for free accounts)
4. Do NOT initialize with a README (you have this one already)
5. Click **Create repository**

### 2. Upload these files

You can do this two ways.

**Web upload (easiest):**
1. On the new repository page, click **uploading an existing file**
2. Drag the entire contents of this folder (`index.html`, `.nojekyll`, `README.md`, and the `images` folder) into the upload area
3. Scroll down, write a commit message such as `Initial site`
4. Click **Commit changes**

**Git command line:**
```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
# copy all files from this folder into the repo
git add .
git commit -m "Initial site"
git push origin main
```

### 3. Enable GitHub Pages

1. In your repository, click **Settings** (top right)
2. In the left sidebar, click **Pages**
3. Under **Source**, choose **Deploy from a branch**
4. Set branch to **main** and folder to **/ (root)**
5. Click **Save**

Within one to two minutes your site will be live. The URL appears at the top of the Pages settings panel.

## Adding Your Photo

1. Save your portrait photo as a JPG (a 4:5 aspect ratio fits best, for example 800 × 1000 pixels)
2. Name it `anqi.jpg` and place it in the `images` folder of your repository
3. Open `index.html` and find this line near the About section (around line 999):
   ```html
   <!-- When you have a portrait photo, save it as images/anqi.jpg and replace this comment with:  <img src="images/anqi.jpg" alt="Anqi Zhang" />  -->
   ```
4. Replace the entire comment with:
   ```html
   <img src="images/anqi.jpg" alt="Anqi Zhang" />
   ```
5. Commit and push. The site will update within a minute.

If your photo has a different aspect ratio, the celadon frame will crop it to fit using `object-fit: cover`. To change which part of your face is centered in the crop, edit `style.css` and add `object-position: top` (or `center top`, etc.) to the `.portrait img` rule.

## Editing Content

The entire site lives in `index.html`. Open it in any text editor (VS Code, Sublime Text, even GitHub's own web editor). The structure is well-commented:

- `<!-- ============ NAV ============ -->` block: the top navigation
- `<!-- ============ HERO ============ -->` block: the landing area with your name
- `<section id="about">`: Chapter I, your bio and education
- `<section id="research">`: Chapter II, research areas and publications
- `<section id="teaching">`: Chapter III, teaching philosophy and courses
- `<section id="service">`: Chapter IV, reviewing, honors, and news
- `<section id="contact">`: Chapter V, contact information

The four ink-divider phrases between chapters can also be edited in the `<span class="ornament">` tags. The ornaments are currently:

- 寒英栖雪 (after Chapter I)
- 墨海探渊 (after Chapter II)
- 清馨化雨 (after Chapter III)
- 终见暖烟 (after Chapter IV)

After editing, commit and push. Changes appear on the live site in about a minute.

## Custom Domain (Optional)

If you eventually register `uncannyeffect.com` (or any other domain) and want it to point at this site instead of `<username>.github.io`:

1. Create a file in the root of your repository named exactly `CNAME` (no extension)
2. Inside that file, write a single line: `uncannyeffect.com`
3. With your domain registrar, add the following DNS records:
   - **A records** pointing to:
     `185.199.108.153`
     `185.199.109.153`
     `185.199.110.153`
     `185.199.111.153`
   - **CNAME record** for `www` pointing to `<your-username>.github.io`
4. In your repository's **Settings → Pages**, the custom domain field will detect the CNAME file. Tick the **Enforce HTTPS** box once it becomes available (usually within an hour after DNS propagates)

DNS propagation can take up to 48 hours. Most of the time it is closer to one hour.

## File Structure

```
your-repo/
├── index.html              # the entire site lives here
├── .nojekyll               # tells GitHub Pages to skip Jekyll processing
├── README.md               # this file
├── CNAME                   # optional, for custom domain (create later)
└── images/
    └── anqi.jpg            # your portrait photo, when you add it
```

## Updating Later

Any time you want to add a publication, swap a course evaluation, or update your news section:

1. Open `index.html` (either locally or directly in GitHub's web interface by clicking the pencil icon)
2. Edit the content
3. Commit the change with a brief message
4. Push (or save if using the web interface)

The live site refreshes automatically within a minute or two.

## Notes

- The site uses Google Fonts via their CDN, so it requires an internet connection to render typography correctly. This works fine on GitHub Pages with no extra setup.
- All styles and scripts are inlined in `index.html` for simplicity. If you would prefer them split into separate `style.css` and `script.js` files later, the markup is structured cleanly enough to extract them with minor effort.
- The site has no build step, no dependencies, no Node, no Jekyll. Pure HTML, CSS, and a small piece of vanilla JavaScript for the scroll effects.

## Credit

Designed in the visual register of Song dynasty literati aesthetics: rice-paper warmth, ink black, celadon and cinnabar accents, generous negative space, and refined serif typography paired with calligraphic Chinese characters.
