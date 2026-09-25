مشروع أندرويد - راديو الجزائر
==============================

هذا مشروع Gradle قياسي (بدون ملفات gradlew لأنني بنيته بدون اتصال إنترنت).

خطوات التجميع:

الطريقة الأسهل (موصى بها):
1. افتح Android Studio.
2. File > Open > اختر مجلد RadioDZ.
3. اترك Android Studio يقوم بـ Gradle Sync تلقائيًا (سيولّد ملفات gradlew بنفسه).
4. Build > Build Bundle(s) / APK(s) > Build APK(s).
5. ستجد الملف الناتج في: app/build/outputs/apk/debug/app-debug.apk

الطريقة اليدوية (إن كان لديك Gradle مثبت على جهازك):
    gradle wrapper --gradle-version 8.7
    ./gradlew assembleDebug

محتوى المشروع:
- app/src/main/assets/index.html  -> واجهة الراديو (HTML/JS) بكل قائمة الإذاعات.
- app/src/main/java/.../MainActivity.kt -> يفتح الواجهة داخل WebView بملء الشاشة.
- الحد الأدنى لإصدار أندرويد: 8.0 (API 26).

ملاحظات:
- التطبيق يحتاج اتصال إنترنت فعلي وقت التشغيل (لأنه يبث الإذاعات مباشرة عبر الشبكة).
- إذا أردت تغيير قائمة الإذاعات أو الروابط، عدّل مصفوفة STATIONS داخل app/src/main/assets/index.html مباشرة.
- المفاتيح المحفوظة (Presets) تُخزَّن محليًا داخل التطبيق (WebView storage) ولا تُرسَل لأي خادم.
