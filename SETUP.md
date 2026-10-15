# Baatein (live): setup

Isme asli members join karte hain, sabka online/offline status dikhta hai, follow/unfollow hota hai, aur messages dono taraf real-time dikhte hain. Free Firebase plan (Spark) se chalta hai, card nahi chahiye.

## Files
- `index.html`: poora app
- `firestore.rules`: database ke security rules (kaun kya padh sakta hai)

## Steps
1. console.firebase.google.com par jao, Google account se login karo, **Add project** dabao. Naam: `baatein`. Analytics off rakh sakte ho.
2. **Build > Authentication > Get started**. **Email/Password** chuno aur Enable karke Save karo.
3. **Build > Firestore Database > Create database**. Production mode chuno, aur apne paas ka region.
4. Firestore me **Rules** tab kholo. Wahan ka sab kuch hatao, `firestore.rules` ka poora text paste karo, aur **Publish** dabao.
5. **Project settings** (gear icon) > **Your apps** > Web icon `</>`. App register karo (Hosting mat chuno). Jo `firebaseConfig` dikhe, uski 4 values copy karo: `apiKey`, `authDomain`, `projectId`, `appId`.
6. `index.html` kholo aur `PASTE_...` wali 4 values un values se badal do.
7. App ko host karo. Aasan raasta: GitHub par nayi repo banao, `index.html` upload karo, **Settings > Pages** me branch chuno. Tumhe `https://<tumhara-username>.github.io/<repo>/` jaisa link milega.
8. **Authentication > Settings > Authorized domains** me `<tumhara-username>.github.io` add karo. Ye na karne par login nahi chalega.
9. Link kholo, account banao, naam aur username chuno. Profile tab se "Invite friends" dabakar dost ko link bhejo. Jo bhi join karega, People tab me dikhega.

Agar pehle wala Baatein (bina follow/status wala) setup kar chuke ho, to Firebase project wahi rehne do. Bas step 4 me nayi rules paste karo aur nayi `index.html` me wahi config daalo.

## Kaise kaam karta hai
- **Online/offline:** App khula ho to har 40 second me apna status likhti hai. 75 second tak koi update na aaye to wo offline dikhta hai, saath me last seen time. Free quota chhote group ke liye kaafi hai.
- **Tumhara admin view:** Firebase console me Authentication > Users (email aur join date) aur Firestore > users. Ye sirf tumhe dikhta hai. Users ko sign-up par ye bata dena.

## Seedhi baatein
- Messages dusre users se private hain (rules ki wajah se), par end-to-end encrypted nahi hain. Tum Firebase console me chat padh sakte ho.
- Online status sabhi members ko dikhta hai. Isse band karne ka option abhi nahi hai.
- Maine ye code yahan chalakar test nahi kiya, kyunki yahan Firebase se connection nahi ban sakta. Code ka syntax check kiya hai. Pehli baar chalane par error aaye to uska message bhej dena.
- Abhi nahi hain: message requests, report, encryption, typing indicator, unread count.
