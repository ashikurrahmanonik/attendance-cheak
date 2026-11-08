# Attendance System (Admin + Student)
1. Repo te upload korun. src/common.js e CLOUD & PRESET (Cloudinary unsigned preset) boshan.
2. Firebase Console: Firestore Database + Authentication (Email/Password) chalu korun, admin user banan.
3. Firestore rules:
   rules_version='2'; service cloud.firestore { match /databases/{d}/documents {
     match /{c}/{id} { allow read: if true; allow write: if request.auth!=null; }
     match /attendance/{id} { allow read: if true; allow write: if request.auth!=null; } } }
4. Ekbar keystore banan, repo root e debug.keystore name commit korun:
   keytool -genkey -v -keystore debug.keystore -storepass android -alias androiddebugkey -keypass android -keyalg RSA -keysize 2048 -validity 10000 -dname "CN=Android Debug,O=Android,C=US"
5. Release: git tag v1.0.0 && git push --tags  -> admin.apk + student.apk Releases e jabe. Notun tag dile app nijei "Update" banner dekhabe.
6. Web version: src/admin.html, src/student.html + src/common.js ekta hosting e (Firebase Hosting/GitHub Pages) deploy korun.
