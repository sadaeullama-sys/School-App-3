School Management System — GitHub APK Build Update

اس ZIP میں اصل School-App-2 پروجیکٹ کے موجودہ UI اور modules برقرار رکھے گئے ہیں۔
اہم تبدیلی: .github/workflows/main.yml کو آسان کیا گیا ہے تاکہ APK بنانے کے لیے
KEYSTORE_BASE64 یا دوسرے GitHub signing secrets لازمی نہ ہوں۔ اب workflow صرف APK
بناتا ہے؛ AAB/Play Store signing اس فائل میں شامل نہیں۔

GitHub پر استعمال:
1) ZIP extract کریں۔
2) اندر موجود School-App-2-main فولڈر کے تمام مواد اپنے GitHub repository کے main
   branch میں upload/replace کریں۔ .github/workflows/main.yml بھی ضرور replace کریں۔
3) GitHub میں Actions کھولیں۔
4) Build School Management System APK workflow منتخب کریں۔
5) Run workflow دبائیں اور مکمل ہونے کا انتظار کریں۔
6) کامیاب run کے Artifacts میں school-management-system-release-apk سے APK حاصل کریں۔

اہم:
- یہ workflow build کو secrets کے بغیر چلانے کے لیے بنایا گیا ہے؛ APK بننے کی ضمانت
  نہیں دی جا سکتی جب تک GitHub Actions میں حقیقی build کامیاب نہ ہو۔
- اس ماحول میں Flutter/Dart SDK دستیاب نہیں تھا، اس لیے flutter analyze یا APK build
  یہاں execute نہیں کیا جا سکا۔ GitHub Actions کا نتیجہ لازماً چیک کریں۔
- Firebase کی موجودہ Spark/Free configuration برقرار ہے۔ Blaze plan فعال نہ کریں۔
- موجودہ app میں Principal کے school modules کی Firestore sync موجود ہے، مگر Staff/Parent
  کے الگ phones پر مکمل Firebase login، principal approval اور محفوظ per-child access
  ابھی مکمل نہیں۔ اس ZIP کو ان فیچرز کے مکمل ہونے کا دعویٰ نہ سمجھیں۔
- Staff/Parent کے passwords کو Firestore میں upload نہ کریں۔
