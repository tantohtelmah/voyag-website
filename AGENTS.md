# VOYAG website updates

- Work on a separate `website/<change>` branch. Never develop directly on the Netlify production branch.
- Confirm the production branch and linked repository in Netlify before any remote write. Do not assume `master` is production.
- Prepare a pull request and non-production preview. Check mobile and desktop layout, images, navigation, contact links, and date-dependent behavior.
- Present the change summary, exact commit, and preview URL to the user.
- Obtain explicit user approval for that reviewed revision before merging or pushing to the production branch, deploying to production, or publishing a deploy manually. General instructions to proceed with work do not constitute release approval.
- If the reviewed changes change, obtain renewed approval. Do not enable auto-merge or bypass protections.
- After an approved release, verify Netlify's published production deploy matches the resulting production commit and check the live website. Report the deploy URL, commit, result, and any failure; never claim success based only on a Git push.
- Do not invent VOYAG facts, commitments, partnerships, or impact figures. Use the team-approved logo and content.

See `WEBSITE_WORKFLOW.md` for setup and release details.
