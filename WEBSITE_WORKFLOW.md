# Website review and release workflow

## Current setup status

Repository: https://github.com/tantohtelmah/voyag-website

The reviewed starting commit is `7a253fa503172a4aa38522df83c74830adda2e33` on `master`. The website is static HTML with local images. `netlify.toml` specifies `publish = "."` and no build command.

The user confirmed Netlify's production branch is `master`, branch deploys are limited to production, and Deploy Previews are enabled for pull requests against production / branch-deploy branches. GitHub access to this repository is verified. The Netlify repository connection will be corroborated by the pull request's preview status. GitHub branch protections and the currently published production commit have not been verified. These instructions document the intended workflow; they do not enforce GitHub or Netlify settings by themselves.

## Account setup

1. In Netlify, confirm the site belongs to VOYAG, its linked repository is the repository above, and record its production branch and current published deploy/commit.
2. Confirm Deploy Previews are enabled for pull requests targeting that branch. Preview links are separate from production. Avoid treating preview URLs as private.
3. In GitHub, protect the confirmed production branch: require pull requests and the observed Netlify preview check; restrict direct pushes, force pushes, deletions, and bypass where available. Require an independent reviewer if the team's account/ownership setup permits it. Never substitute a self-approval for the user's explicit release approval.
4. Leave automatic merging disabled. A successful preview is evidence for review, not authorization to publish.

## Each update

1. Start from the latest confirmed production revision on `website/<change>`.
2. Implement the requested change and inspect the diff. Check desktop/mobile layouts, image loading, internal links, email links, external links, and event dates/countdowns. Confirm organizational claims and logo selection with approved sources.
3. Push only the feature branch and open a pull request against the confirmed production branch. Wait for its Netlify preview to finish successfully.
4. Give the user the summary, pull request, exact commit, and preview. Prefer the immutable deploy permalink when recording approval, since the normal preview URL changes after new commits.
5. Wait for explicit approval to release that revision. Record the approval in the review record. Any subsequent change invalidates that approval until reviewed again.
6. Immediately before merging, confirm the approved revision is still current and checks pass. Merge only after approval; do not separately push unreviewed changes to production.

## Verify the release

1. Record the resulting production commit after merge (it can differ from the feature commit).
2. Wait for Netlify's production deployment and confirm its source branch and commit match. Check that it is published, not merely built or available as a preview.
3. Open the live site and verify the intended update, page loading, images, navigation, and contact actions on desktop and mobile.
4. Report the production URL, commit, deploy identifier/link, and checks performed. If deployment fails or is locked, report the actual state rather than assuming the live site changed.
5. For a rollback, identify the last verified deployment and obtain explicit approval before republishing it unless the user has already authorized that recovery action.

## First proposed maintenance change

Remove four tracked `:Zone.Identifier` metadata files that prevent Windows checkout. Existing `.gitignore` already excludes future additions. Keep site content, images, and Netlify configuration unchanged in this maintenance proposal.

Reference: https://docs.netlify.com/deploy/deploy-types/deploy-previews/
