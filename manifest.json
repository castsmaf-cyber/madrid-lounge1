# مدريد PS Lounge v4 — دليل الإعداد

## الملفات
```
madrid_app/
├── index.html      ← التطبيق الكامل
├── manifest.json   ← إعدادات PWA
├── sw.js           ← Service Worker
├── icon-192.png    ← أيقونة
└── icon-512.png    ← أيقونة كبيرة
```

---

## ⚙️ إعداد التحكم في الاشتراك (Google Sheets)

### الخطوة 1: إنشاء Google Sheet
1. افتح Google Sheets وأنشئ شيت جديد
2. اكتب في الصف الأول (الرؤوس):
   ```
   client_id  |  active  |  expiry_date  |  notes
   ```
3. في الصف التاني اكتب بيانات عميلك:
   ```
   CLIENT_001  |  TRUE  |  2025-12-31  |  اسم العميل
   ```

### الخطوة 2: نشر الشيت عام
1. من القائمة: **File → Share → Publish to web**
2. اختر **Comma-separated values (.csv)**
3. انسخ الرابط اللي هيظهر

### الخطوة 3: تعديل التطبيق
افتح `index.html` بأي محرر نصوص (Notepad, VS Code...)

ابحث عن السطرين دول في أول الكود:
```javascript
const SHEET_CSV_URL = 'YOUR_GOOGLE_SHEET_CSV_URL_HERE';
const CLIENT_ID = 'CLIENT_001';
```

استبدلهم بـ:
```javascript
const SHEET_CSV_URL = 'https://docs.google.com/spreadsheets/d/...رابطك هنا.../export?format=csv';
const CLIENT_ID = 'CLIENT_001';
```

---

## 🎛️ التحكم في الاشتراك

| تريد إيه؟ | افعل إيه في الشيت |
|---|---|
| تفعيل الاشتراك | اكتب `TRUE` في خانة `active` |
| إيقاف الاشتراك | اكتب `FALSE` في خانة `active` |
| تجديد الاشتراك | غير `expiry_date` لتاريخ جديد |

**مهم:** التغيير بيأثر فوراً — العميل بعد ما يفتح التطبيق هيتحقق أوتوماتيكي.

---

## 📶 الاشتراك بدون نت
لو العميل فتح التطبيق وما فيش نت:
- التطبيق هيشتغل لمدة **7 أيام** من آخر تحقق ناجح
- بعد كده محتاج نت لإعادة التحقق

---

## 🖥️ تثبيت التطبيق (PWA)
1. ارفع الملفات **كلها** على سيرفر أو Netlify أو GitHub Pages
2. افتح الرابط في المتصفح
3. هيظهر زرار "Install" أو "إضافة للشاشة الرئيسية"
4. بعد التثبيت يشتغل كتطبيق مستقل بأيقونة

---

## 🔑 الدخول الافتراضي
| المستخدم | كلمة المرور |
|---|---|
| admin | admin123 |
| admin2 | admin2123 |
| cashier | cashier123 |

**غيّر كلمات المرور من الإعدادات فور أول دخول!**
