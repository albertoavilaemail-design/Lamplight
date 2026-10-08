# Lamplight Bible Study

A nightly Bible study web app: reading plans (The Bible Recap, Bible in a Year, New Testament, or a single book), guided reflection questions, one daily action with a follow-up the next night, a private journal, memory verses with spaced review, a prayer list, and friend accountability by friend code.

People can sign in with Google so their study syncs across devices, or use it without an account (saved in that browser only).

## Files

| File | What it is |
|---|---|
| `index.html` | The whole app |
| `firebase-config.js` | Your Firebase project settings (you fill this in) |
| `firestore.rules` | Security rules that keep each person's journal private |

---

## Setup (about 20 minutes, free)

### 1. Create the Firebase project
1. Go to **console.firebase.google.com** and click **Create a project**. Name it `lamplight` (or anything). You can turn off Google Analytics.
2. On the project home page, click the **Web** icon (`</>`) to add a web app. Name it `Lamplight`. Leave "Firebase Hosting" unchecked. Click **Register app**.
3. Firebase shows a `firebaseConfig = { ... }` block. Copy the six values into `firebase-config.js`, replacing each `PASTE_...` value.

### 2. Turn on Google sign-in
1. In the left menu: **Build → Authentication → Get started**.
2. Under **Sign-in method**, choose **Google**, switch it on, pick your support email, and **Save**.

### 3. Create the database and lock it down
1. Left menu: **Build → Firestore Database → Create database**.
2. Choose a location near you (for Texas, `us-central` / `nam5` is fine) and start in **production mode**.
3. Open the **Rules** tab, delete what's there, paste the entire contents of `firestore.rules`, and click **Publish**.

### 4. Put it on GitHub Pages
1. Go to **github.com/new**. Name the repository `lamplight`, set it to **Public**, and create it.
2. Click **uploading an existing file**, drag in `index.html`, `firebase-config.js`, `firestore.rules` and `README.md`, then **Commit changes**.
3. Go to the repo's **Settings → Pages**. Under "Build and deployment," set **Source** to *Deploy from a branch*, **Branch** to `main` and folder `/ (root)`, then **Save**.
4. After a minute or two the site is live at `https://YOUR-USERNAME.github.io/lamplight/`.

### 5. Approve your site for sign-in
1. Back in Firebase: **Authentication → Settings → Authorized domains → Add domain**.
2. Add `YOUR-USERNAME.github.io` (no `https://`, no `/lamplight`).

Open your site, tap **Sign in with Google**, and you're in.

---

## Inviting friends
1. Send them the site link. They sign in and set up their own plan.
2. On the **Progress** tab, each of you copies your 6-character **friend code** and adds the other's.
3. Each of you turns on **Let friends see my progress**.

Friends see only your plan, current day, streak and nights studied. Journals, prayers and memory verses are private to each person.

## Add it to your phone's home screen
- **iPhone (Safari):** Share button → **Add to Home Screen**.
- **Android (Chrome):** ⋮ menu → **Add to Home screen**.

## Notes
- Scripture opens in the NIV on Bible Gateway. The app doesn't store Bible text.
- The Firebase config values are meant to be public. The security rules are what protect people's data.
- The free Firebase plan easily covers a few hundred people studying every night.
- Updating the app later: upload a new `index.html` to the repo; GitHub Pages redeploys automatically.
