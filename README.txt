CAMPUS EVENTS - HOST + REGISTRATION VERSION

What this version fixes:
1. Events and registrations are stored in Firebase Cloud Firestore, so they do NOT disappear when the browser is closed.
2. Only the host Firebase account can open the host dashboard and create/edit/delete events.
3. Students can view published events without logging in.
4. Students can register with name, roll number, email and selected event.
5. The host dashboard shows total events, total registrations, and a table showing which student registered for which event.

SETUP

A. Create Firebase project
1. Open the Firebase Console.
2. Create a project named Campus Events.
3. Add a Web App.
4. Copy the Firebase configuration into firebase-config.js.
Firebase's official web setup guide explains registering a web app and getting the config object.

B. Enable Authentication
1. Firebase Console -> Authentication -> Sign-in method.
2. Enable Email/Password.
3. Add ONE host user.
4. Use your own email and a strong password.
5. Do not put the password in this code.

C. Create Firestore
1. Firebase Console -> Firestore Database -> Create database.
2. Choose a suitable region.
3. Open Firestore -> Rules.
4. Paste firestore.rules.
5. Replace YOUR_HOST_UID with your host user's Firebase Authentication UID.
   You can find the UID in Authentication -> Users.

D. Upload these files to GitHub Pages
- index.html
- host.html
- app.js
- host.js
- firebase-config.js
- style.css
- college-logo.jpg

HOW IT WORKS

Public:
https://YOUR-GITHUB-USERNAME.github.io/YOUR-REPOSITORY/

Host:
https://YOUR-GITHUB-USERNAME.github.io/YOUR-REPOSITORY/host.html

Students never get access to the host dashboard unless they have the host Firebase account.

IMPORTANT
The Firebase web config is not a password. Security is provided by Firebase Authentication and Firestore Security Rules. Never put your host password or service-account private key into the website.

For production, consider adding Firebase App Check, validation/rate limiting, and a better student identity system.
