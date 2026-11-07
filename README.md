# Kohat Division Polio Dashboard (static site)

Static website: `index.html` + `decks/` + `reports/`. No server code. Host with GitHub Pages
(Settings > Pages > Deploy from branch > main / root) or any web folder.
Locally: `python3 -m http.server` in this folder, then open http://localhost:8000
(opening the file directly will not load the downloads).

## What works here
- All dashboard pages, filters, maps and UC drill-through.
- ERM PowerPoint downloads (decks/ folder) work in any browser for anyone.
- Summary Reports (Word/PDF): files in `reports/` are encrypted; the page asks for the common password.
  The report files are useless without it, even though the site is public.

## What does not work here
- ERM minutes entry / "include ERM decisions" and the owner password-change button need claude.ai
  (shared database). On this site reports download without ERM decisions.
- To change the common password here, re-run the build (ask Claude) - it re-wraps the key and a new index.html is produced.

## GitHub upload
The decks folder is large (about 400 files). Use git, not the web uploader:
  git init && git add . && git commit -m "Kohat dashboard" && git branch -M main
  git remote add origin https://github.com/<user>/<repo>.git && git push -u origin main
Public repo = public site. Use a private repo + Pages only if your plan allows it.
