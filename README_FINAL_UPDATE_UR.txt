NEW IQRA CHILDREN ACADEMY — FINAL DESIGN UPDATE (SOURCE PACKAGE)

اس ZIP میں درج ذیل تبدیلیاں شامل کی گئی ہیں:
1) DMC / Detailed Marks Certificate کو نئے پروفیشنل ڈیزائن میں بنایا گیا ہے: ڈبل بارڈر، سبز اور گولڈ تھیم، سائیڈ پر پھول نما ڈیکوریٹو نشان، اسکول کا نام، لوگو، طالب علم کی تصویر، مضمون وار نمبر، فیصد، گریڈ، پاس/فیل نتیجہ، کلاس ٹیچر اور پرنسپل کے دستخط کی جگہ۔
2) DMC میں وہی موجودہ marks data استعمال ہوتا ہے؛ نیا نتیجہ یا نمبر خود سے شامل نہیں کیے جاتے۔
3) Staff Portal میں صرف وہی ماڈیول دکھائے جاتے ہیں جن کے لیے کوئی اجازت دی گئی ہو۔ اجازتیں View/Add/Edit/Delete کے طور پر دکھائی جاتی ہیں۔
4) Android launcher icon کے لیے موجودہ academy icon asset استعمال کرتے ہوئے GitHub Actions میں icon generation کا مرحلہ شامل کیا گیا ہے۔
5) موجودہ Backup & Restore، PDF share، syllabus/date sheet، license اور دوسرے موجودہ سورس ماڈیول برقرار رکھے گئے ہیں۔

اہم حدود / ضروری جانچ:
- PDF ایک جامد دستاویز ہے؛ اس لیے DMC کو animated نہیں بنایا جا سکتا۔ اسے decorative/floral print design دیا گیا ہے۔
- Staff کے View/Add/Edit/Delete حقوق ابھی ہر موجودہ data-entry callback اور Firebase request پر مکمل طور پر enforce نہیں ہوتے۔ یہ ZIP صرف Staff Portal میں غیرمجاز ماڈیول چھپاتی اور اجازتیں دکھاتی ہے؛ اسے مکمل security fix نہ سمجھیں۔
- Firebase permission-denied مسئلے کی اصل وجہ جانچنے کے لیے آپ کے Firebase Console کے موجودہ Rules، signed-in account UID، school ownerUid/status اور مکمل error message درکار ہیں۔ اس پیکیج میں Firestore rules کو غیرمحفوظ طور پر کھلا نہیں کیا گیا۔
- DMC logo کے لیے موجودہ app launcher emblem استعمال ہوتا ہے۔ ہر اسکول کا الگ uploaded logo DMC میں شامل کرنے کے لیے logo file path کو school record میں محفوظ اور PDF تک منتقل کرنا الگ کام ہے۔
- اس ماحول میں Flutter/Dart SDK موجود نہیں، اس لیے flutter analyze، APK build اور physical Android test نہیں چلائے جا سکے۔ GitHub Actions میں build کے بعد APK artifact چیک کریں۔

BUILD:
GitHub پر ZIP extract کرکے project کی تمام فائلیں repository root میں upload کریں۔ Actions میں موجود workflow چلائیں۔ یہ workflow بغیر signing secrets کے installable debug APK بناتا ہے؛ اسے فون میں test کے لیے install کریں۔ Play Store کے لیے الگ signed release build درکار ہوگا۔
