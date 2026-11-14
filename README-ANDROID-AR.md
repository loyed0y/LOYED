# LOYED — تجهيز بناء APK

هذا مجلد تغليف Android للمشروع الحالي الموجود في `www/`. لم يتم استبدال الواجهة أو إنشاء تطبيق منفصل؛ يتم عرض ملفات HTML/CSS/JavaScript الحالية داخل Android WebView باستخدام Capacitor.

## بناء APK تلقائياً عبر GitHub Actions

1. ارفع **محتويات هذا المجلد** إلى جذر مستودع GitHub الصحيح (يجب أن يكون `package.json` و`capacitor.config.json` ومجلد `www` و`.github` في الجذر).
2. افتح تبويب **Actions** في المستودع.
3. اختر **Build LOYED Android APK** ثم **Run workflow**، أو ادفع commit إلى `main` أو `master`.
4. بعد نجاح البناء افتح نتيجة التشغيل، ثم نزّل الملف من **Artifacts → LOYED-debug-APK**.
5. فك ضغط الـ Artifact وثبّت `app-debug.apk` على هاتف Android. قد تحتاج للسماح بالتثبيت من هذا المصدر.

## متطلبات البناء

GitHub-hosted Ubuntu runner، Node.js 22، Java 21، واتصال الإنترنت لتنزيل Gradle وCapacitor.

## حدود النسخة الحالية

المصدر الأصلي Frontend Prototype يعتمد على `localStorage`. تحويله إلى APK لا ينشئ Backend أو مزامنة حقيقية أو مكالمات WebRTC أو إشعارات FCM أو تشفيراً طرفياً. الميزات المحاكية تظل محاكية إلى أن يتم بناء وربط الخادم والخدمات اللازمة واختبارها.

## ملاحظات الإصدار

- معرف التطبيق: `com.loyed.app`
- اسم التطبيق: `LOYED`
- الناتج الحالي: Debug APK للتجربة، وليس إصداراً موقعاً للنشر على Google Play.
- لا تضع كود المالك أو أسرار API داخل ملفات الواجهة أو مستودع عام. كود المالك الموجود في النموذج الأولي يجب نقله إلى تحقق خادمي قبل أي استخدام إنتاجي.
