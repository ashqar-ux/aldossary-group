# دليل نشر موقع مجموعة يوسف الدوسري القابضة
# Deployment Guide — Yousef Al-Dossary Holding Group

موقع ثابت (Static) بملف واحد `index.html` مع مجلد `assets/`. لا يحتاج خادوماً أو قاعدة بيانات — يُرفع كما هو.

## 📁 محتويات المشروع
```
aldossary-group/
├── index.html          # الموقع الكامل (HTML/CSS/JS مضمّن)
├── robots.txt
├── sitemap.xml
├── DEPLOY.md           # هذا الملف
└── assets/
    ├── favicon.png     # أيقونة التبويب
    ├── logo-full.png   # الشعار الشفاف (هيدر/فوتر/شريط الأعضاء)
    ├── og-image.png    # صورة المشاركة الاجتماعية 1200×630
    ├── board/          # صور مجلس الإدارة (4)
    └── logos/          # شعارات الأعضاء والشركاء
```

## ⚠️ قبل النشر: ضبط النطاق (Domain)
الوسوم مضبوطة افتراضياً على `https://www.aldossary-group.com`. إذا نشرت على نطاق مختلف، استبدله في:
- `index.html` → `canonical` و `og:url` و `og:image` و `twitter:image` وبيانات `JSON-LD`
- `robots.txt` → سطر `Sitemap:`
- `sitemap.xml` → `<loc>`

استبدال واحد بالبحث والاستبدال (find/replace) لكلمة `www.aldossary-group.com` يكفي.

> مهم: صورة المشاركة (og:image) تحتاج رابطاً مطلقاً `https://` ليظهر معاينة الرابط في واتساب/تويتر — لا تتركه نسبياً.

## 🚀 خيارات الاستضافة

### 1) استضافة عادية عبر FTP (cPanel وغيره)
ارفع كامل محتويات مجلد `aldossary-group/` إلى مجلد `public_html` (أو `www`). افتح النطاق — الموقع يعمل مباشرة.

### 2) Netlify (سحب وإفلات)
اذهب إلى https://app.netlify.com/drop واسحب مجلد `aldossary-group` بالكامل. يُنشر خلال ثوانٍ برابط مجاني، ويمكن ربط نطاقك لاحقاً.

### 3) Vercel
```bash
npm i -g vercel
cd aldossary-group
vercel --prod
```

### 4) GitHub Pages
ادفع الملفات إلى مستودع، ثم Settings → Pages → اختر الفرع والمجلد الجذر.

## ✅ بعد النشر
1. افتح الموقع وتأكد من ظهور الشعار والصور والخريطة.
2. اختبر معاينة الرابط: https://www.opengraph.xyz (الصق رابط موقعك) — للتأكد من صورة المشاركة.
3. افحص بيانات SEO المنظّمة: https://validator.schema.org
4. أرسل الـ sitemap إلى Google Search Console.
5. جرّب زر تبديل اللغة (عربي/إنجليزي) وقائمة الجوال.

## 🔗 روابط خارجية مستخدمة
- خطوط Google Fonts (Cairo / Manrope) — تحتاج اتصال إنترنت.
- خرائط Google (إطار مضمّن) لموقع المقر.
- روابط مواقع الشركات الأعضاء والشركاء.

---
صُمّم وطُوّر بواسطة أكفاء **Divoraix** · divoraix.com
