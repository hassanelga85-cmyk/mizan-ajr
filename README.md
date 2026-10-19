# ميزان الأجر — مشروع تطبيق أندرويد (Capacitor)

## الطريقة الأسهل: بناء APK سحابياً (دون تثبيت أي شيء)
1. أنشئ مستودعاً جديداً على GitHub وارفع محتويات هذا المجلد.
2. افتح تبويب **Actions** ← **Build Android APK** ← **Run workflow**.
3. بعد دقائق نزّل الملف `mizan-ajr-apk` من قسم Artifacts، وفيه `app-debug.apk`.
4. انقله للهاتف وثبّته (فعّل «التثبيت من مصادر غير معروفة»).

## البناء على حاسوبك
المتطلبات: Node 20+، JDK 21، Android Studio (أو Android SDK).
```
npm install
npm run build
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug
```
الناتج: `android/app/build/outputs/apk/debug/app-debug.apk`

## ملاحظات
- النسخة debug موقّعة بمفتاح تجريبي: تصلح للتثبيت المباشر، لا للنشر في Google Play.
- للنشر في Play اصنع مفتاح توقيع وابنِ `bundleRelease` (ملف AAB).
