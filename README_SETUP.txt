STAYEASY FIREBASE PROJECT - SETUP GUIDE

1. Extract this ZIP and open the StayEasy_Firebase_Project folder in VS Code.

2. Create a Firebase project:
   https://console.firebase.google.com/

3. Add a Web App in Firebase Project Settings > General > Your apps.
   Copy the Firebase config values into firebase.js.
   Replace all YOUR_* placeholders with your actual project values.

4. Enable Authentication:
   Firebase Console > Authentication > Get started > Sign-in method
   Enable:
   - Email/Password
   - Anonymous

5. Create your admin user:
   Authentication > Users > Add user.
   Copy that user's UID.

6. Replace YOUR_ADMIN_UID with the same UID in BOTH:
   - admin/admin.js
   - firestore.rules

7. Create Firestore:
   Build > Firestore Database > Create database.
   Open the Rules tab, paste firestore.rules and Publish.

8. Run locally:
   - Install VS Code Live Server extension.
   - Open index.html with Live Server.
   - Do not open the HTML file directly with file://.
   - Admin page: /admin/admin.html

9. Test:
   - Submit a test booking from the main website.
   - Check Firestore Database > bookings collection.
   - Open admin/admin.html and sign in using the admin email/password.
   - The admin dashboard should show booking records.

IMPORTANT SECURITY NOTES:
- Never share your Firebase admin password or admin UID publicly.
- Firebase web config is not a password; Firestore Rules protect the data.
- This is a learning/demo booking app, not a production payment system.
- The displayed total is calculated in browser JavaScript. A real hotel must
  validate prices and booking availability on a trusted server before payment.
- Anonymous users can submit bookings; protect production deployments against
  spam and abuse (for example with App Check and server-side validation).
- My Booking uses localStorage on the same browser. Clearing browser data or
  switching devices can remove that local display; the admin records remain
  in Firestore.
- This starter records bookings, not every anonymous website visitor.
