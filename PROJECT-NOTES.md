# Project Notes — Adrian Smith Physiotherapy Website

Read this first before making any edits in a new chat session. It captures decisions and
constraints that aren't obvious just from looking at the files.

## What this is
Personal professional website for Adrian Smith, Registered Physiotherapist (Ontario).
Domain: adriansmithphysio.ca. "Stage 1" of a larger plan — a separate, fully independent
project called BOONES (boones.ca) is a different sub-brand with its own future accounts
system and is NOT part of this site.

## Tech stack (deliberately simple)
- Static HTML/CSS/JS. No framework, no build step, no npm packages.
- Hosting: Netlify (free tier) — chosen over Vercel because Vercel's free Hobby plan
  restricts use to non-commercial projects.
- DNS: Porkbun, using ALIAS + CNAME records pointed at Netlify.
- Deploy workflow: files are uploaded manually to GitHub (web UI), and Netlify auto-deploys
  from that GitHub repo.
- Contact: uses Adrian's existing Gmail (adriansmithphysio@gmail.com) via a plain
  `mailto:` link — no custom email hosting, no form backend.
- No memberships/paywall/login system exists or is planned for this site, ever.

## Critical structural rule: FLAT FILE STRUCTURE — NO SUBFOLDERS
All files (index.html, specialties.html, locations.html, contact.html, styles.css, main.js,
adrian-headshot.jpg, this notes file) live at the repo root with no subfolders whatsoever.
This is not a style preference — GitHub's browser drag-and-drop upload previously flattened
a nested `assets/` folder, which broke every relative path on the live site (unstyled text,
broken image). Keep everything flat to avoid a repeat of that bug. When zipping files to
hand to a new chat, zip them flat (no directory structure inside the zip).

## Content rules — must keep following these
- Never fabricate, exaggerate, or embellish anything about Adrian's credentials, experience,
  or bio. If a detail isn't confirmed, keep the language general/vague rather than invent
  specifics.
- No phone number anywhere on the site — Adrian does not want to publish it. Contact options
  are Email and the Find Me / booking links only.
- Visual style is "classic golf": neutral tones, deep green + gold accents, no tilted photos,
  no neon. Theme lives in `styles.css` under the `:root` CSS variables at the top of the file
  — change the site's whole look by editing those variables rather than hunting through rules.

## Current real content on the site (all confirmed by Adrian, not placeholder)
Five specialties, in this order: Golf Physiotherapy (TPI Level 1 certified), General Athletic
& Strength/Conditioning, Older Adult & Bone/Joint Health (McMaster PACE seniors program),
Cardiac Experience (McMaster PACE cardiac program), Post-Surgical Rehabilitation (hip/knee
replacements, rotator cuff repairs, fractures).

Find Me / locations page lists three real places: Revive Health (Hamilton), OAK Physio &
Wellness (Mississauga), McMaster PACE (Hamilton), each with a real booking/info link.

## Known open item
The addresses for Revive Health and McMaster PACE on locations.html were sourced from public
listings, not directly confirmed by Adrian. There's a visible note on that page flagging this.
Worth double-checking those two addresses against reality before treating the site as fully
final, if that hasn't happened yet.

## If you're a new Claude chat picking this up
1. You won't have any memory of prior conversations about this project — this file is your
   briefing.
2. Ask Adrian for the current repo contents (GitHub → Code → Download ZIP) rather than
   assuming any previously-generated zip is still current — Adrian's GitHub is the source of
   truth, not any one chat.
3. Preserve the flat file structure and the content/style rules above when making changes.
