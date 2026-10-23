PERSONAL WEBSITE + CV -- how to publish and update (Salma Lemkhente, October 2026)

WHAT IS WHERE
  Desktop\website\            the website (upload the CONTENTS of this folder to GitHub)
    index.html                all the text of the site (one page)
    style.css                 the design -- no need to touch
    fonts\                    the typeface (Source Serif 4, open licence)
    img\                      photo-portrait.jpg (desktop), photo-square.jpg (phones / link previews), favicon.svg
    cv\Lemkhente_CV.pdf       the CV behind every "CV" link (keep this exact file name)
    papers\                   put paper PDFs here (e.g. Lemkhente_JMP.pdf)
  Desktop\cv_academic\Lemkhente_CV.tex   the CV source (Overleaf)

=====================================================================
A. PUBLISH THE WEBSITE (once, about 10 minutes)
=====================================================================
  1. Sign in at https://github.com (account: salma-lemkhente).
  2. Top right "+" > New repository. Repository name exactly:  salma-lemkhente.github.io
     Public. Tick nothing else. Create repository.
  3. On the new page click "uploading an existing file". Open Desktop\website in Windows Explorer,
     select everything inside it (index.html, style.css, README.txt, and the folders cv, fonts, img, papers)
     and drag it onto the page. Wait until all files are listed. Click "Commit changes".
     (Empty folders are skipped by GitHub -- that is fine.)
  4. Settings (top of the repository) > Pages (left menu) > Source: "Deploy from a branch",
     Branch: main, folder: / (root) > Save.
  5. After 1-2 minutes the site is live at  https://salma-lemkhente.github.io
     Your paper page stays at https://salma-lemkhente.github.io/innovation-rival-consolidation/

=====================================================================
A2. OWN DOMAIN, e.g. salmalemkhente.com (after A; about 15 minutes + waiting)
=====================================================================
  1. Buy it at a registrar that charges the same price every year and includes free privacy
     (e.g. Cloudflare Registrar or Porkbun; about 10-12 USD a year for .com). Turn ON auto-renew.
     Skip every add-on (email, website builder, "SSL certificate") -- GitHub gives HTTPS for free.
  2. Verify it with GitHub (stops anyone else from using it): github.com > your photo (top right) >
     Settings > Pages > "Add a domain" > type salmalemkhente.com. GitHub shows a TXT record:
     add it at the registrar (DNS settings), wait a few minutes, click "Verify".
  3. At the registrar's DNS settings add (delete any "parking" records it created):
        Type A      Name @     Value 185.199.108.153
        Type A      Name @     Value 185.199.109.153
        Type A      Name @     Value 185.199.110.153
        Type A      Name @     Value 185.199.111.153
        Type CNAME  Name www   Value salma-lemkhente.github.io
     On Cloudflare, set each record to "DNS only" (grey cloud), otherwise GitHub cannot issue HTTPS.
  4. Repository salma-lemkhente.github.io > Settings > Pages > Custom domain: salmalemkhente.com > Save.
     When the check turns green (minutes to a few hours), tick "Enforce HTTPS".
  5. Your paper page moves with it (salmalemkhente.com/innovation-rival-consolidation/); the old
     github.io links redirect, so links already printed in papers keep working.
  6. Then change the address in index.html (og:url, og:image) and in the CV header.

=====================================================================
B. UPDATE THE WEBSITE (any time, 2 minutes)
=====================================================================
  Edit text directly on GitHub:
    open the repository > click index.html > pencil icon (Edit) > change the text > "Commit changes".
    The live site updates within about a minute (refresh with Ctrl+F5).

  Typical edits -- each is marked in index.html with a comment:
    * Abstract of a paper: replace the text inside   <details> ... <p>[Abstract ...]</p>
    * Main result of the JMP: replace the text after <span>Main result.</span>
    * JMP PDF: upload papers\Lemkhente_JMP.pdf (step below), then make the title a link:
        <h3><a href="papers/Lemkhente_JMP.pdf">What Firms Build: ...</a></h3>
      and remove the <!-- --> around the "Paper / Slides" links line.
    * New presentation: add it to the  <p class="pres">Presented at ...</p>  line.
    * "Last updated October 2026" at the bottom.
  Only edit text between tags (between > and <); keep the tags themselves.

  Replace or add a file (new CV PDF, paper PDF):
    open the folder on GitHub (e.g. cv) > Add file > Upload files > drop the file with the SAME name > Commit.

=====================================================================
C. UPDATE THE CV (Overleaf)
=====================================================================
  First time: Overleaf > New Project > Upload Project > choose Desktop\cv_academic\Lemkhente_CV.tex
  (compiler: pdfLaTeX, the default). Press Recompile.

  Each entry is one command; copy an existing one and change the text in braces:
    \paper{Title}{with Coauthor -- status}{Abstract}{Presentations}     (leave {} empty if none)
    \talk{2027}{Event name, City}                                       presentations, training
    \course{Course name}{Program, level}{Years}{Details or {} }        teaching tables
    \job{Role}{Dates}{Institution}{City, Country}                       education, positions
    \referee{Name}{Title}{Institution}{email}
  Red [FILL: ...] text marks what is still missing; delete the whole \tofill{...} when you fill it.

  After editing: Download PDF > rename to Lemkhente_CV.pdf > upload to the website's cv folder (section B).
