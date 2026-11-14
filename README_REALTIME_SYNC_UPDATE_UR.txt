آن لائن Realtime Sync اپ ڈیٹ — School-App-2

اس اپ ڈیٹ میں موجودہ ڈیزائن اور موجودہ ماڈیولز برقرار رکھے گئے ہیں۔

شامل کی گئی تبدیلی:
- Principal کے لاگ اِن اور منظور شدہ اسکول کے لیے Firestore appData کے 12 ماڈیولز پر realtime snapshots listeners شامل کیے گئے ہیں۔
- دوسرے ڈیوائس سے Firestore میں ریکارڈ تبدیل ہونے پر کھلے ہوئے Principal dashboard میں تبدیلی آ سکتی ہے۔
- آنے والا cloud ڈیٹا SharedPreferences کے local cache میں بھی محفوظ ہوتا ہے۔
- انٹرنیٹ بند ہونے پر موجودہ local data برقرار رہتا ہے؛ Firestore Android persistence کی queue نیٹ ورک واپس آنے پر sync کر سکتی ہے۔
- Dashboard بند ہونے پر listeners cancel کیے جاتے ہیں۔

اہم حدود:
- یہ تبدیلی Principal کے موجودہ Firebase Auth / schoolId flow کے لیے ہے۔
- Staff اور Parent کے موبائل+پاس ورڈ آن لائن اکاؤنٹس، invitation redemption، parent-only child access اور server-side staff permissions ابھی اس ZIP میں مکمل implement نہیں ہیں۔
- موجودہ module data ایک Firestore document میں records array کی صورت میں ہے؛ بہت بڑے ڈیٹا کے لیے یہ مناسب نہیں اور Firestore document size limit کا خیال رکھنا ہوگا۔
- اس ماحول میں Flutter SDK دستیاب نہیں، اس لیے flutter analyze، APK build اور حقیقی موبائل ٹیسٹ نہیں کیے جا سکے۔

استعمال سے پہلے:
1. Firebase Console میں موجودہ project کے لیے Firestore فعال ہونا چاہیے۔
2. Firestore Rules کو صرف اپنے پروجیکٹ کی موجودہ محفوظ rules کے مطابق deploy کریں۔ ZIP میں موجود firestore.rules فائل Principal-owner approved school access کے لیے ہے؛ اسے غیر متعلقہ rules کے ساتھ merge کیے بغیر replace نہ کریں۔
3. GitHub Actions میں Flutter build چلائیں اور build کامیاب ہونے کے بعد دو ڈیوائسز پر ایک ہی Principal اکاؤنٹ سے sync ٹیسٹ کریں۔

نوٹ: ZIP میں کسی Firestore rule کو خودکار طور پر publish نہیں کیا گیا۔
