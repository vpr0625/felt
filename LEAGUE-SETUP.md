# Setting up the Felt league

The League tab stores shared results in a free Firebase project. You set this up once,
and everyone who opens your copy of Felt uses the same league service.
Personal sessions, notes and hands never leave each person's phone.

It takes about 15 minutes. A computer is easiest, but a phone works too.

## 1. Create the Firebase project
1. Go to https://console.firebase.google.com and sign in with a Google account.
2. Tap **Create a project**, name it something like `felt-league`, and continue.
3. When asked about Google Analytics, you can turn it off. Then create the project.

## 2. Turn on anonymous sign-in
Felt signs each phone in automatically, without accounts or passwords.
1. In the left menu, open **Build → Authentication** and tap **Get started**.
2. On the **Sign-in method** tab, choose **Anonymous**, switch it on, and save.
3. On the **Settings** tab, open **Authorized domains** and add your site's domain,
   for example `yourname.github.io`.

## 3. Create the database
1. Open **Build → Firestore Database** and tap **Create database**.
2. If asked for an edition, choose **Standard**.
3. Pick a location close to you, and choose **Start in production mode**.

## 4. Add the security rules
1. In Firestore, open the **Rules** tab.
2. Delete what's there, paste in everything from `firestore.rules` (included with the app), and tap **Publish**.

These rules make sure only league members can see results, people can only add and edit their own,
and reactions can only change your own reaction.

## 5. Connect Felt to the project
1. Tap the gear next to **Project Overview**, then **Project settings**.
2. Under **Your apps**, tap the web icon `</>`, give it a nickname like `Felt`, and register it.
   You don't need Firebase Hosting.
3. Firebase shows a `firebaseConfig` with values like `apiKey`, `authDomain` and `projectId`.
4. In your GitHub repository, open `firebase-config.js`, tap the pencil to edit,
   copy each value into the matching line between the quotes, and commit the change.

These values aren't secret. They only identify your project, and the security rules are what protect the data.

## 6. Start your league
Open Felt, go to the **League** tab, tap **Start a league**, and share the invite with your friends.
They add Felt to their home screen from the same web address, open League, and enter the code.

## Free limits
The free Firebase plan includes 50,000 reads and 20,000 writes a day, far more than a group of friends will use.
If a limit were ever reached on the free plan, Firebase stops the database until the quota resets instead of charging you.
