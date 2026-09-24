# CountryManagerTnCandPnP

The privacy policy, terms and conditions, and account deletion page for the
Country Manager app. Plain HTML served by GitHub Pages, with no build step.

| Page | Published at |
| --- | --- |
| Landing page | https://empiricalcodelabs.github.io/CountryManagerTnCandPnP/ |
| Privacy Policy | https://empiricalcodelabs.github.io/CountryManagerTnCandPnP/privacy.html |
| Terms and Conditions | https://empiricalcodelabs.github.io/CountryManagerTnCandPnP/terms.html |
| Delete your account | https://empiricalcodelabs.github.io/CountryManagerTnCandPnP/delete-account.html |

The privacy policy URL goes into Play Console under App content, Privacy policy.
The delete-account URL goes under App content, Data deletion.

The app opens these same URLs, so the pages here are the only copy of the text.

## Turning on GitHub Pages

Settings, then Pages. Under Source choose "Deploy from a branch", branch
`main`, folder `/ (root)`. The `.nojekyll` file tells Pages to serve the files
as they are.

## Publishing a change

Each document carries a version: the date it was last changed, written
`YYYY-MM-DD`. It appears at the top of the page as "Version 2026-09-24".

1. Edit the page. Change both "Last updated" and "Version" at the top.
2. Commit and push. The site updates within a few minutes.
3. **Only if the change matters to users**, make the app ask everyone to
   accept it again. In the Firebase console, open Firestore, document
   `appConfig/legal`, and set `termsVersion` or `privacyVersion` to the new
   version. Put one or two sentences saying what changed in `changeSummary`.
   Every phone asks again the next time the app is opened, with no app
   release.
4. In the app's next release, raise the matching constant in
   `lib/core/constants/legal_documents.dart`, so that a phone that has never
   been online still knows the newest version.

A typo fix or a reworded sentence doesn't need step 3. A change to what is
collected, who sees it, prices, or anyone's rights does.

## Keeping it true

These pages describe what the app actually does. Change them when the app
changes in any way they mention, for example a new permission, a new
service that receives data, analytics or crash reporting, push
notifications, or changes to billing.
