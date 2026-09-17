# GTW Baku Website Handover Guide

This package lets Valid own the GTW Baku GitHub repository, Vercel project and domain deployment independently.

## Before starting

Valid needs:

- A Vercel account
- A GitHub account with a verified email
- This complete ZIP file
- Access to the DNS controls for `gtwbaku.az`

## 1. Create a GitHub account

1. Open `https://github.com/signup`.
2. Create a free account using Valid's own email.
3. Complete GitHub's email verification.
4. Sign in to GitHub.

## 2. Create a private repository

1. In GitHub, press the `+` button in the upper-right corner.
2. Select **New repository**.
3. Enter `gtw-baku-website` as the repository name.
4. Select **Private**.
5. Do not add a README, `.gitignore` or license.
6. Press **Create repository**.

## 3. Upload this package to GitHub

1. Extract this ZIP file on the computer.
2. Open the new empty GitHub repository.
3. Select **uploading an existing file**.
4. Drag the contents of the extracted `GTW-Baku-Website` folder into GitHub. Upload the contents, not the outer folder itself.
5. Confirm that `index.html`, `vercel.json`, `README.md`, `VALID-DEPLOYMENT-GUIDE.md` and the `assets` folder are visible at the repository root.
6. In the commit message field, enter `Initial approved GTW Baku website`.
7. Commit directly to the `main` branch.
8. Press **Commit changes**.

## 4. Connect GitHub to Vercel

1. Sign in at `https://vercel.com/`.
2. Open the Vercel dashboard.
3. Press **Add New**, then **Project**.
4. If GitHub is not connected, select **Continue with GitHub** or **Connect GitHub**.
5. Approve the Vercel GitHub application.
6. Give Vercel access to the `gtw-baku-website` repository.
7. Return to Vercel and locate `gtw-baku-website` in the repository list.
8. Press **Import**.

## 5. Configure and deploy the preview

Use these settings:

- Project name: `gtw-baku-website`
- Framework preset: **Other**
- Root directory: `./`
- Build command: leave empty
- Output directory: leave empty
- Install command: leave empty
- Environment variables: none

Press **Deploy**. When deployment finishes, Vercel will provide a `.vercel.app` address.

Do not connect `gtwbaku.az` yet. First review the Vercel preview on desktop, tablet, mobile and in a private browser window that is not logged in to Vercel.

If the preview opens a Vercel login page, open **Project Settings**, then **Deployment Protection**, turn off **Require Log In** for the deployment and save. Test the link again in a private browser window. Do not send a session-bound share-token URL as the permanent website address.

## 6. Preview verification

Confirm all of the following:

- The site opens without a Vercel login page.
- The GTW logo, Baku skyline, fonts and favicon load.
- The navigation and all buttons work.
- The contact links open `valid@gtwbaku.az`.
- The LinkedIn link opens the official GTW Baku page.
- The Global GTW link opens `globaltechweekend.io`.
- The cancelled September 19 event does not appear.
- Baku ID and Sabah Hub do not appear as partners.
- No website copy uses the word `room`.
- The site is visually correct on desktop, tablet and mobile.

## 7. Connect the domain after approval

1. In Vercel, open the `gtw-baku-website` project.
2. Open **Settings**, then **Domains**.
3. Add `gtwbaku.az`.
4. Add `www.gtwbaku.az`.
5. Set `gtwbaku.az` as the primary address.
6. Configure `www.gtwbaku.az` to redirect to `gtwbaku.az`.
7. Vercel will show the exact DNS records required.
8. Open the DNS management page for `gtwbaku.az` at the domain registrar.
9. Replace only conflicting web records for `@` and `www` with the exact values displayed by Vercel.
10. Return to Vercel and wait for both domains to show a valid configuration and HTTPS.

Do not delete or modify MX, SPF, DKIM, DMARC or email-verification TXT records. Those records may be required for `valid@gtwbaku.az` to continue working. Do not change the domain's nameservers unless the entire DNS zone is intentionally being moved.

## 8. Update the final domain metadata

After `https://gtwbaku.az/` is live, edit these four values near the top of `index.html`:

- `og:url` to `https://gtwbaku.az/`
- `og:image` to `https://gtwbaku.az/assets/baku-skyline.webp`
- `twitter:image` to `https://gtwbaku.az/assets/baku-skyline.webp`
- canonical URL to `https://gtwbaku.az/`

Commit the change to `main`. Vercel will automatically publish the new commit.

## 9. Final verification

Test both `https://gtwbaku.az/` and `https://www.gtwbaku.az/`. Confirm the main domain opens over HTTPS, `www` redirects correctly, all assets and links work, and the contact email still receives mail.

For future website changes, edit files in the GitHub repository and commit them to `main`. Vercel will automatically deploy each new commit and preserve the full change history.
