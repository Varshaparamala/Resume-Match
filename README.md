# Resume Match

A single-page web app that compares a resume with a job description. Paste both, and it shows a match score, the skills the posting asks for that your resume is missing, and specific edits to make.

## Features

- Match score from 0 to 100, with a strong, partial or weak verdict
- Skills found on both sides, and skills missing from the resume
- Essential ("core") skills told apart from nice-to-have ones, based on how the posting words them
- Suggested edits, such as which skills to add, which to mention more often, and when to add numbers to bullets
- Words the posting repeats that the resume never uses
- Light and dark theme, works on phones
- Runs fully in the browser. Nothing is uploaded.

## How it works

1. The job description is scanned against a built-in list of about 80 technical and soft skills.
2. A skill counts as core if it appears under requirement wording ("must", "proficiency in", "experience with") or is mentioned more than once. Skills under "preferred" or "nice to have" count less.
3. The score is the weighted share of the posting's skills that also appear on the resume.
4. Edit suggestions come from the gaps and from simple checks on the resume, such as missing numbers or sections.

## Run it

No build step and no dependencies. Open `index.html` in a browser.

## Publish it with GitHub Pages

1. Push this folder to a GitHub repository.
2. In the repository, open Settings, then Pages.
3. Under Build and deployment, choose Deploy from a branch, pick `main` and the `/ (root)` folder, and save.
4. After a minute the site is live at `https://<your-username>.github.io/<repository-name>/`.

## Limits and ideas

- Skills outside the built-in list are not detected. Add more entries to the `SKILLS` array in `index.html`.
- Possible next steps: a FastAPI backend with an LLM for rewriting resume bullets, PDF upload, and saving past comparisons.
