# VOYAG landing page

A small static site for Voices of Young African Girls. No build command or package installation is required.

## Files

- `index.html` — page content and styling
- `assets/voyag-logo.png` — transparent logo used in the header and hero
- `netlify.toml` — tells Netlify to publish the repository root

## Open in VS Code

1. Extract the ZIP into a folder named `voyag-website` on your computer.
2. In VS Code, choose **File → Open Folder** and select that folder.
3. Open `index.html` in a browser to see the site. Edit text and CSS in `index.html`, then refresh the browser.

## Push to GitHub

Create an **empty** repository on GitHub named `voyag-website` (do not add a README or `.gitignore` there). In VS Code's terminal, from the extracted project folder, run:

```bash
git init
git branch -M main
git add .
git commit -m "Create VOYAG landing page"
git remote add origin https://github.com/YOUR-USERNAME/voyag-website.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your GitHub username or use the repository URL GitHub displays. Sign in when Git prompts you. Do not put passwords, donation account credentials, or other secrets in the repository.

## Connect GitHub to Netlify

In Netlify, choose **Add new project → Import an existing project → GitHub**. Authorize the repository and select `voyag-website`. Choose `main` as the production branch. The site has no build command; the publish directory is `.` (repository root). Deploy the project.

If you already published this site through Netlify Drop, connect that existing Netlify project to the repository in **Project configuration → Developer settings → Continuous deployment → Repository** instead of creating a second site.

## Update the site

Edit and save `index.html` in VS Code, then run:

```bash
git add .
git commit -m "Update VOYAG content"
git push
```

Netlify deploys a new version after each push to `main`.

## Before public launch

VOYAG's constitution is still a draft. Review the mission and motto wording with the team. The donation link currently opens an email enquiry and does not accept payment. Add an approved donation destination only after VOYAG has one.
