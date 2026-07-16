Pragna College website
Static, informational site — Home, Courses, Gallery, Contact. No forms, no backend.
Structure (flat — all files at repo root)
```
Pragna-college/
├── index.html      Home page
├── courses.html     B.Ed / D.Ed course details
├── gallery.html      Event photo grid (placeholders — swap in real photos anytime)
├── contact.html      Google Maps embed + admissions phone number
├── style.css         Shared design system
├── campus-hero.jpg    Homepage hero photo (drone shot of the campus building)
└── README.md
```
Why everything is flat (no css/ subfolder)
GitHub's web upload flow doesn't reliably preserve folders when you drag in loose files —
it silently drops them at the repo root. Keeping `style.css` at the same level as the HTML
files avoids that entirely: every page links to it as just `style.css`, no subfolder to break.
Updating on GitHub
To edit any page: open the file in GitHub → pencil (edit) icon → make changes → commit to `main`.
Cloudflare Pages auto-redeploys within about a minute of any commit.
Swapping in real event photos
In `gallery.html`, each placeholder is a `.gallery-item` div. Replace it with an `<img>` tag:
```html
<div class="gallery-item">
  <img src="events/annual-day-1.jpg" alt="Annual Day 2025" style="width:100%;height:100%;object-fit:cover;">
</div>
```
Upload photos to an `events/` folder the same way — as a single batch upload if possible, so
GitHub keeps the folder structure intact.
Contact info currently on the site
Phone: +91 98480 66101
Map: embedded Google Maps iframe on the Contact page
