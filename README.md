# AI Guide — دليل أدوات الذكاء الاصطناعي

موقع ثابت (HTML/CSS/JS + JSON) بدون Backend. التنقل يعتمد على `#/` فلا يحتاج Server Routing.

## 1) التشغيل محليًا
المتصفح يمنع `fetch` من `file://`، لذا شغّل خادمًا بسيطًا:
`python3 -m http.server 8000` ثم افتح `http://localhost:8000`.

## 2) النشر على GitHub Pages
1. ارفع كل الملفات إلى مستودع GitHub (الملف `index.html` في الجذر).
2. Settings ← Pages ← Source: Deploy from a branch ← `main` / `(root)`.
3. بعد دقائق يعمل الموقع على `https://USERNAME.github.io/REPO/`.
4. استبدل `USERNAME/REPO` في `robots.txt` و`sitemap.xml`، وغيّر البريد في `data/tools.json` (`site.email`).

## 3) إضافة أداة
أضف عنصرًا في مصفوفة `tools` في `data/tools.json` بالحقول: id, icon, name, category (معرّف مجال), also (مجالات إضافية), description, website, pricing, freePlan, difficulty (مبتدئ/متوسط/متقدم), rating, bestFor, tags, features, pros, cons, tutorials, prompts, alternatives (معرّفات أدوات).
استخدم الموقع الرسمي الحقيقي فقط وراجع الأسعار دوريًا.

## 4) إضافة مجال
أضف في `categories` عنصرًا `{id, name, icon, desc}` ثم اجعل `category` أو `also` في الأدوات يشير إلى `id` الجديد.

## 5) تعديل الدروس
عدّل مصفوفة `lessons` (level, title, text, example, steps, prompt, exercise). وعدّل `wizard` لأهداف "ماذا أستخدم؟".
