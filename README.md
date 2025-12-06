# 🤖 LLM QA Automation Framework

> إطار عمل لأتمتة اختبار جودة مخرجات نماذج اللغة الكبيرة (LLM) باستخدام Postman و Google Gemini API

[![Postman](https://img.shields.io/badge/Postman-FF6C37?style=flat&logo=postman&logoColor=white)](https://www.postman.com/)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Gemini](https://img.shields.io/badge/Google_Gemini-4285F4?style=flat&logo=google&logoColor=white)](https://ai.google.dev/)

---

## 📖 نظرة عامة

هذا المشروع يوفر حلاً تلقائياً لاختبار استجابات نماذج الذكاء الاصطناعي (LLM) من خلال:

- ✅ إرسال استعلامات محددة مسبقاً
- ✅ تخزين الإجابات تلقائياً
- ✅ تقييم الإجابات باستخدام النموذج نفسه
- ✅ تحديد النتيجة: **PASS** أو **FAIL**

---

## 🎯 لماذا هذا المشروع؟

في عصر الذكاء الاصطناعي، نحتاج لطرق موثوقة لاختبار جودة مخرجات نماذج اللغة. هذا المشروع يوفر:

- **الأتمتة الكاملة:** لا حاجة للاختبار اليدوي
- **القابلية للتكرار:** نفس الاختبار بنفس الدقة في كل مرة
- **القياس الموضوعي:** استخدام AI لتقييم AI
- **سهولة التوسع:** إضافة اختبارات جديدة بسهولة

---

## 🚀 البدء السريع

### المتطلبات الأساسية

- [Postman](https://www.postman.com/downloads/) (Desktop أو Web)
- حساب [Google Gemini API](https://ai.google.dev/) مع API Key
- معرفة أساسية بـ Postman و APIs

### خطوات التثبيت

#### 1. استنساخ المشروع

```bash
git clone https://github.com/Ahmad-ELManaseer03/QA-LLM.git
cd QA-LLM
```

#### 2. استيراد Environment

1. افتح Postman
2. اذهب إلى **Environments** → **Import**
3. اختر الملف `environment.json`
4. أضف `GEMINI_API_KEY` في حقل **Current Value**
5. احفظ واختر الـ Environment

#### 3. استيراد Collection

1. اذهب إلى **Collections** → **Import**
2. اختر الملف `Postman collection.json`
3. ستظهر جميع الطلبات

---

## 🧪 سيناريوهات الاختبار

### السيناريو الأول: اختبار المعرفة الجغرافية

**الهدف:** التحقق من معرفة النموذج بعاصمة فرنسا

**الخطوات:**
1. **Ask Question 1:** "ما هي عاصمة البلد الذي يحتوي على برج إيفل؟"
2. **Evaluator 1:** تقييم هل الإجابة "باريس" صحيحة؟

**النتيجة المتوقعة:** ✅ PASS

---

### السيناريو الثاني: اختبار الفهم السياقي

**الهدف:** فحص قدرة النموذج على فهم الأوصاف

**الخطوات:**
1. **Ask Question 2:** "احكي قصة عن حيوان له أذنان مثلثتان ويموء"
2. **Evaluator 2:** تقييم هل القصة عن "قطة"؟

**النتيجة المتوقعة:** ✅ PASS

---

## 📊 كيفية التشغيل

### الطريقة 1: تشغيل يدوي

```
Prompt 1 → Ask Question 1 → Evaluator 1
Prompt 2 → Ask Question 2 → Evaluator 2
```

### الطريقة 2: تشغيل Collection كاملة

1. انقر بزر الماوس الأيمن على الـ Collection
2. اختر **Run collection**
3. تأكد من اختيار الـ Environment الصحيح
4. اضغط **Run**

### الطريقة 3: Postman Monitor (اختياري)

- أنشئ Monitor للـ Collection
- حدد الجدول الزمني (يومي، أسبوعي، إلخ)
- تتبع النتائج تلقائياً

---

## 🧩 بنية المشروع

```
QA-LLM/
│
├── Postman collection.json    # جميع الطلبات والاختبارات
├── environment.json            # المتغيرات والـ API Key
├── Recording-Demo-Video.mp4   # فيديو توضيحي
└── README.md                  # هذا الملف
```

---

## 🔧 التقنيات المستخدمة

| التقنية | الاستخدام |
|---------|-----------|
| **Postman** | إدارة الطلبات والاختبارات |
| **Gemini API** | نموذج اللغة الكبيرة |
| **JavaScript** | كتابة اختبارات ما بعد الطلب |
| **Environment Variables** | تخزين البيانات والنتائج |

---

## 📈 مثال على النتائج

```javascript
// نتائج الاختبارات
✅ Status code is 200
✅ Response has candidates array
✅ Text content exists
✅ Model answer stored
✅ Evaluation result: PASS

// إحصائيات
Total Tests: 16
Passed: 16 (100%)
Failed: 0 (0%)
```

---

## 🎓 ما تعلمته من هذا المشروع

- اختبار APIs باستخدام Postman
- كتابة Test Scripts بـ JavaScript
- التعامل مع Environment Variables
- أتمتة سير عمل الاختبارات
- تقييم جودة مخرجات LLM
- استخدام Postman Monitors

---

## 🔐 ملاحظات الأمان

⚠️ **مهم جداً:**
- **لا تشارك** الـ `GEMINI_API_KEY` علناً
- استخدم `.gitignore` لاستبعاد الملفات الحساسة
- استخدم **Postman Vault** لتخزين الـ API Keys بأمان

---

## 🚧 التحسينات المستقبلية

- [ ] إضافة المزيد من سيناريوهات الاختبار
- [ ] دعم نماذج LLM أخرى (GPT, Claude, إلخ)
- [ ] تقارير HTML للنتائج
- [ ] تكامل مع CI/CD Pipelines
- [ ] Dashboard لعرض الإحصائيات

---

## 🤝 المساهمة

المساهمات مرحب بها! إذا كان لديك اقتراحات:

1. Fork المشروع
2. أنشئ Branch جديد (`git checkout -b feature/AmazingFeature`)
3. Commit التغييرات (`git commit -m 'Add some AmazingFeature'`)
4. Push للـ Branch (`git push origin feature/AmazingFeature`)
5. افتح Pull Request

---

## 📝 الترخيص

هذا المشروع مفتوح المصدر تحت رخصة [MIT](LICENSE).

---

## 👤 المطور

**Ahmad ELManaseer**

- GitHub: [@Ahmad-ELManaseer03](https://github.com/Ahmad-ELManaseer03)
- LinkedIn: www.linkedin.com/in/ahmad-elmanaseer03
- Email: ahmad1manaseer@gmail.com

---

## ⭐ إذا أعجبك المشروع

أعطه ⭐ على GitHub!

---

**📺 شاهد الفيديو التوضيحي:** [`Recording-Demo-Video.mp4`](Recording-Demo-Video.mp4)

---

<div align="center">

صُنع بـ ❤️ للمهتمين بـ QA و AI Testing

</div>
