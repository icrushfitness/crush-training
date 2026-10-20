# Crush Training: go-live steps (about 20 minutes, no cost)

## 1. Firebase (logins + saved data)
1. Go to console.firebase.google.com, sign in with your Google account, click **Add project**, name it "crush-training". Skip Google Analytics.
2. **Build > Authentication > Get started > Email/Password > Enable > Save.**
3. **Build > Firestore Database > Create database.** Pick a US location. Choose **production mode**.
4. In Firestore, open the **Rules** tab. Delete what's there, paste the contents of `firestore.rules`, click **Publish**.
5. **Project settings (gear) > General > Your apps > the </> Web icon.** Register the app (skip Hosting). Copy the config values (apiKey, authDomain, projectId, appId) into `firebase-config.js`.

## 2. GitHub (hosting)
1. github.com > **New repository**, name it `crush-training`. Public (free Pages requires public for personal accounts). No secrets are in these files.
2. **Add file > Upload files**: upload every file in this folder (index.html, firebase-config.js, firestore.rules, manifest.webmanifest, icon-192.png, icon-512.png, .nojekyll). Commit.
3. **Settings > Pages > Source: Deploy from a branch > main / (root) > Save.** After a minute your site is at `https://YOUR-USERNAME.github.io/crush-training/`.

## 3. Let the login work on that address
Firebase console > **Authentication > Settings > Authorized domains > Add domain**: `YOUR-USERNAME.github.io`.

## 4. Testers
- No setup needed. Send them the link. They tap **Create an account** with any email.
- See who signed up: Firebase console > Authentication > Users. Their workouts: Firestore Database > Data > users.
- iPhone: Share > Add to Home Screen. Android: menu > Install app.

## Updating the app later
Replace `index.html` in the GitHub repo with the new one I give you. Everyone's data stays.

## Sign-up link
Your site address opens the login screen. Add `?signup` to open the Create account form directly, e.g. `https://YOUR-USERNAME.github.io/crush-training/?signup`.
Each member's name, email and mobile number are saved on their account: Firebase console > Firestore Database > Data > users > (a user) > contact.
