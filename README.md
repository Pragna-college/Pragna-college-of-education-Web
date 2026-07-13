# Pragna College website (MVP)

Static site — Home + Admissions. Ready to deploy to Cloudflare Pages as-is.

## Structure
```
pragna-website/
├── index.html          Home page
├── admissions.html      Admissions page + enquiry form (static)
├── css/style.css        Shared design system (kinetic minimal style)
└── README.md
```

## Deploy to Cloudflare Pages
1. Push this folder to a new GitHub repo (or a `website/` subfolder in an existing repo).
2. In Cloudflare Pages: **Create a project → Connect to Git**, pick the repo.
3. Build settings: no build command needed, output directory = `/` (or `website/` if nested).
4. Deploy — you'll get a `*.pages.dev` URL, and can attach a custom domain after.

## Current state
- Fully static, no backend calls.
- The enquiry form on `admissions.html` shows a "thanks" message on submit, but does **not** save anywhere yet — it's a placeholder.

## Next step: wire the form to Supabase
When ready:
1. Create a new Supabase project for this site (kept separate from Arise / Pragna PWA, as usual).
2. Create an `enquiries` table: `id, full_name, phone, email, program, message, created_at`.
3. In `admissions.html`, replace the placeholder in the `<script>` block at the bottom with a Supabase JS client insert call, using the anon key (safe to expose client-side) and a Row Level Security policy that only allows `insert`, not `select`, from the public role.

Happy to build that wiring whenever you're ready — just say the word.
