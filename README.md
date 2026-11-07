# هوصلك – مشروع التطبيق (Android + iOS)
تطبيق native مبني بـ Capacitor: نفس تصميم التطبيق لكن بيتثبت كتطبيق حقيقي (APK للأندرويد، IPA للآيفون).

## أندرويد – طريقة ١ (بدون Android Studio)
1. اعمل حساب مجاني على github.com وأنشئ Repository جديد وارفع عليه محتويات المجلد ده كلها.
2. من تبويب Actions شغّل "Build Android APK" (Run workflow) وانتظر ~5 دقايق.
3. حمّل الملف howsalak-apk من الـ Artifacts → هيطلع app-debug.apk → انقله للموبايل وثبّته (اسمح بالتثبيت من مصدر غير معروف).

## أندرويد – طريقة ٢ (Android Studio، ولنسخة Google Play)
npm install ثم npx cap sync android ثم npx cap open android
بعدها Build ▸ Build APK، أو Generate Signed Bundle (AAB) للنشر على Google Play (رسوم حساب المطوّر ٢٥$ مرة واحدة).

## آيفون (محتاج Mac + Xcode + حساب Apple Developer ٩٩$/سنة)
npm install
npx cap add ios
npx @capacitor/assets generate --ios
npx cap open ios
من Xcode اختار Team الخاص بيك، شغّله على الجهاز، ثم Product ▸ Archive للرفع على TestFlight/App Store.
(مفيش طريقة لتثبيت تطبيق آيفون خارج المتجر من غير توقيع Apple.)

## بعد أي تعديل في www/index.html
npx cap sync
## ملاحظة
التطبيق لسه محتاج سيرفر (Supabase/Firebase) علشان الطلبات تتزامن بين الأجهزة وتتصل بلوحة الإدارة.
