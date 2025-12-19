<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>أداة إعداد التقارير المدرسية</title>

<style>
@font-face{
  font-family:'KufamLocal';
  src:url('static/Kufam-Regular.ttf') format('truetype');
}

:root {
  --primary-color: #0a3b40;
  --secondary-color: #2a8c82;
  --accent-color: #41bfb3;
  --light-color: #f2f7f6;
  --light-gray: #e8f1f0;
  --text-color: #1a3c40;
  --border-color: #b8d4d0;
  --error-color: #e74c3c;
  --success-color: #27ae60;
  --shadow: 0 4px 12px rgba(10, 59, 64, 0.08);
  --shadow-hover: 0 6px 16px rgba(10, 59, 64, 0.12);
  --radius: 12px;
  --transition: all 0.3s ease;
}

body{
  font-family: 'KufamLocal', 'Segoe UI', sans-serif;
  background: linear-gradient(135deg, #f2f7f6 0%, #e8f1f0 100%);
  margin: 0;
  padding: 20px;
  color: var(--text-color);
  line-height: 1.6;
}

/* ===== الهيدر الجديد المصغر ===== */
.tool-container {
  max-width: 1000px;
  margin: 0 auto 40px;
}

.tool-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 20px;
  padding: 10px 15px;
  background: white;
  border-radius: 10px;
  box-shadow: var(--shadow);
}

.header-left {
  display: flex;
  align-items: center;
  gap: 15px;
}

.header-logo {
  width: 50px;
  height: 50px;
  object-fit: contain;
}

.header-title {
  font-size: 18px;
  font-weight: 700;
  color: var(--primary-color);
}

.header-right {
  font-size: 14px;
  color: var(--text-color);
  opacity: 0.8;
}

.tool{
  background: white;
  padding: 30px;
  border-radius: var(--radius);
  box-shadow: var(--shadow);
  transition: var(--transition);
}

.tool:hover {
  box-shadow: var(--shadow-hover);
}

/* ===== تحسين الحقول ===== */
.form-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  margin-bottom: 25px;
}

@media (max-width: 768px) {
  .form-grid {
    grid-template-columns: 1fr;
  }
}

.form-group {
  margin-bottom: 20px;
  position: relative;
}

.form-group label{
  display: block;
  font-weight: 700;
  margin-bottom: 8px;
  color: var(--primary-color);
  font-size: 15px;
}

.form-group input,
.form-group textarea,
.form-group select {
  width: 100%;
  padding: 14px;
  border: 2px solid var(--border-color);
  border-radius: 10px;
  font-family: inherit;
  font-size: 15px;
  background-color: white;
  transition: var(--transition);
  box-sizing: border-box;
}

.form-group input:focus,
.form-group textarea:focus,
.form-group select:focus {
  outline: none;
  border-color: var(--accent-color);
  box-shadow: 0 0 0 3px rgba(65, 191, 179, 0.1);
}

.form-group textarea{
  resize: vertical;
  min-height: 100px;
}

.form-group select {
  cursor: pointer;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' fill='%230a3b40' viewBox='0 0 16 16'%3E%3Cpath d='M7.247 11.14 2.451 5.658C1.885 5.013 2.345 4 3.204 4h9.592a1 1 0 0 1 .753 1.659l-4.796 5.48a1 1 0 0 1-1.506 0z'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: left 15px center;
  background-size: 12px;
  padding-right: 15px;
}

/* ===== أزرار النصوص الافتراضية ===== */
.default-text-buttons {
  display: flex;
  gap: 8px;
  margin-top: 8px;
  flex-wrap: wrap;
}

.default-btn {
  padding: 6px 12px;
  background: var(--light-gray);
  border: 1px solid var(--border-color);
  border-radius: 6px;
  font-size: 12px;
  cursor: pointer;
  transition: var(--transition);
  color: var(--text-color);
}

.default-btn:hover {
  background: var(--accent-color);
  color: white;
  border-color: var(--accent-color);
}

.clear-btn {
  padding: 6px 12px;
  background: #ffebee;
  border: 1px solid #ffcdd2;
  border-radius: 6px;
  font-size: 12px;
  cursor: pointer;
  transition: var(--transition);
  color: #c62828;
}

.clear-btn:hover {
  background: #ffcdd2;
}

/* ===== عداد الكلمات ===== */
.counter-container {
  display: flex;
  justify-content: space-between;
  margin-top: 6px;
}

.counter{
  font-size: 13px;
  color: #6a8a85;
  font-weight: 500;
}

.counter.limit{
  color: var(--error-color);
  font-weight: 700;
}

/* ===== تحسين الأزرار ===== */
.buttons-container {
  display: flex;
  gap: 15px;
  margin-top: 30px;
}

@media (max-width: 768px) {
  .buttons-container {
    flex-direction: column;
  }
}

.btn {
  flex: 1;
  padding: 16px 24px;
  border: none;
  border-radius: 10px;
  font-size: 16px;
  font-weight: 700;
  cursor: pointer;
  transition: var(--transition);
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
}

.btn-primary {
  background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
  color: white;
}

.btn-primary:hover {
  transform: translateY(-3px);
  box-shadow: var(--shadow-hover);
}

.btn-secondary {
  background: linear-gradient(90deg, #7f8c8d, #95a5a6);
  color: white;
}

.btn-secondary:hover {
  background: linear-gradient(90deg, #6c7b7d, #7f8c8d);
  transform: translateY(-3px);
}

.btn-icon {
  font-size: 18px;
}

/* ===== تحسين تحميل الصور ===== */
.file-upload {
  position: relative;
  margin-top: 8px;
}

.file-upload input[type="file"] {
  position: absolute;
  width: 100%;
  height: 100%;
  opacity: 0;
  cursor: pointer;
  z-index: 2;
}

.file-upload label {
  display: block;
  padding: 14px;
  background-color: var(--light-gray);
  border: 2px dashed var(--border-color);
  border-radius: 10px;
  text-align: center;
  color: var(--primary-color);
  font-weight: 600;
  cursor: pointer;
  transition: var(--transition);
  z-index: 1;
  position: relative;
}

.file-upload label:hover {
  background-color: #e0ecea;
  border-color: var(--accent-color);
}

.file-upload .file-info {
  margin-top: 8px;
  font-size: 13px;
  color: #6a8a85;
  text-align: center;
}

/* ===== رسالة تأكيد ===== */
.confirmation {
  position: fixed;
  top: 20px;
  right: 20px;
  background: var(--success-color);
  color: white;
  padding: 15px 25px;
  border-radius: 10px;
  box-shadow: var(--shadow);
  z-index: 1000;
  opacity: 0;
  transform: translateY(-20px);
  transition: opacity 0.3s, transform 0.3s;
  display: none;
}

.confirmation.show {
  display: block;
  opacity: 1;
  transform: translateY(0);
}

/* ===== التقرير (لطباعة PDF - غير متغير) ===== */
.report{display:none;}
@page{size:A4;margin:14mm;}

@media print{
  body{background:white;padding:0}
  .tool{display:none}
  .report{display:block}

  /* ===== الهيدر المصغر ===== */
  .header{
    background:var(--primary-color);
    color:white;
    padding:4px 6px;
    border-radius:6px;
    text-align:center;
    font-size:11px;
    margin-bottom:6px;
  }

  /* ===== معلومات التقرير (مصغّرة) ===== */
  .info-grid{
    display:grid;
    grid-template-columns:repeat(5,1fr);
    gap:5px;
    margin-bottom:6px;
  }
  .info-box{
    border:2px solid var(--border-color);
    border-radius:7px;
    padding:3px 4px;
    text-align:center;
    font-size:10px;
  }
  .info-box span{
    display:block;
    background:var(--primary-color);
    color:white;
    border-radius:5px;
    padding:1px;
    font-weight:700;
    font-size:9px;
    margin-bottom:2px;
  }

  /* ===== المحتوى ===== */
  .grid-desc{
    display:flex;
    gap:8px;
    margin-bottom:8px;
  }

  .desc-box{
    border:2px solid var(--border-color);
    border-radius:10px;
    padding:8px;
    background:#f9fbfb;
    font-size:12px;
    display:flex;
    flex-direction:column;
  }
  .desc-box.big{min-height:110px;flex:1}
  .desc-box.small{min-height:80px;flex:1}

  .desc-box strong{
    border-bottom:1px dashed var(--border-color);
    padding-bottom:4px;
    margin-bottom:6px;
    color:var(--primary-color);
  }
  .desc-box p{white-space:pre-line;flex:1}

  .vertical{
    width:32px;
    background:#eef3f1;
    border-radius:8px;
    display:flex;
    align-items:center;
    justify-content:center;
    font-weight:700;
  }

  /* ===== الصور ===== */
  .images{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:10px;
    margin-top:12px;
  }
  .images img{
    width:100%;
    height:120px;
    object-fit:cover;
    border-radius:8px;
  }

  /* ===== التوقيعات ===== */
  .signatures{
    margin-top:22px;
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:40px;
    border-top:2px solid var(--border-color);
    padding-top:14px;
  }
  .signature-box{
    text-align:center;
    font-size:12px;
  }
  .signature-line{
    border-bottom:2px solid #000;
    height:26px;
    margin:8px 0;
  }
}
</style>
</head>

<body>

<div class="confirmation" id="confirmationMessage">
  ✓ تم إنشاء التقرير بنجاح، جاهز للطباعة
</div>

<div class="tool-container">
  <!-- الهيدر الجديد المصغر -->
  <div class="tool-header">
    <div class="header-left">
      <img src="https://i.ibb.co/2037zjqy/IMG-2102.jpg" alt="شعار وزارة التعليم" class="header-logo">
      <div class="header-title">وزارة التعليم</div>
    </div>
    <div class="header-right">أداة إعداد التقارير المدرسية</div>
  </div>

  <div class="tool">
    <div class="form-grid">
      <div class="form-group">
        <label for="education-department">إدارة التعليم</label>
        <select id="education-department" oninput="sync('edu', this.options[this.selectedIndex].text)">
          <option value="">اختر إدارة التعليم</option>
          <option>الإدارة العامة للتعليم بمنطقة مكة المكرمة</option>
          <option>الإدارة العامة للتعليم بمنطقة الرياض</option>
          <option>الإدارة العامة للتعليم بمنطقة المدينة المنورة</option>
          <option>الإدارة العامة للتعليم بالمنطقة الشرقية</option>
          <option>الإدارة العامة للتعليم بمنطقة القصيم</option>
          <option>الإدارة العامة للتعليم بمنطقة عسير</option>
          <option>الإدارة العامة للتعليم بمنطقة تبوك</option>
          <option>الإدارة العامة للتعليم بمنطقة حائل</option>
          <option>الإدارة العامة للتعليم بمنطقة الحدود الشمالية</option>
          <option>الإدارة العامة للتعليم بمنطقة جازان</option>
          <option>الإدارة العامة للتعليم بمنطقة نجران</option>
          <option>الإدارة العامة للتعليم بمنطقة الباحة</option>
          <option>الإدارة العامة للتعليم بمنطقة الجوف</option>
          <option>الإدارة العامة للتعليم بمحافظة الأحساء</option>
          <option>الإدارة العامة للتعليم بمحافظة الطائف</option>
          <option>الإدارة العامة للتعليم بمحافظة جدة</option>
        </select>
      </div>

      <div class="form-group">
        <label for="school">اسم المدرسة</label>
        <input id="school" type="text" placeholder="أدخل اسم المدرسة" oninput="sync('school',this.value)">
      </div>

      <div class="form-group">
        <label for="education-item">البند التربوي</label>
        <select id="education-item" onchange="updateReportTitles()">
          <option value="">اختر البند التربوي</option>
          <option value="تحسين نواتج التعلم والتحصيل الدراسي">تحسين نواتج التعلم والتحصيل الدراسي</option>
          <option value="الدعم العلاجي والتدخلات التعليمية">الدعم العلاجي والتدخلات التعليمية</option>
          <option value="التدريس والتعلم داخل الصف">التدريس والتعلم داخل الصف</option>
          <option value="التخطيط والتنظيم التعليمي">التخطيط والتنظيم التعليمي</option>
          <option value="الأنشطة المدرسية واللاصفية">الأنشطة المدرسية واللاصفية</option>
          <option value="التقويم والمتابعة والتوثيق">التقويم والمتابعة والتوثيق</option>
          <option value="التواصل والشراكة مع الأسرة">التواصل والشراكة مع الأسرة</option>
          <option value="التطوير المهني وبناء القدرات">التطوير المهني وبناء القدرات</option>
          <option value="التميز والجودة">التميز والجودة</option>
          <option value="التحول الرقمي والابتكار">التحول الرقمي والابتكار</option>
          <option value="السلوك والإرشاد التربوي">السلوك والإرشاد التربوي</option>
          <option value="المبادرات والشراكات المجتمعية">المبادرات والشراكات المجتمعية</option>
          <option value="السلامة والصحة المدرسية">السلامة والصحة المدرسية</option>
        </select>
      </div>

      <div class="form-group">
        <label for="report-title-select">عنوان التقرير</label>
        <select id="report-title-select" onchange="sync('title', this.value)">
          <option value="">اختر عنوان التقرير بعد اختيار البند التربوي</option>
        </select>
      </div>

      <div class="form-group">
        <label for="date">تاريخ التنفيذ</label>
        <input id="date" type="text" placeholder="يوم/شهر/سنة" oninput="sync('date',this.value)">
      </div>

      <div class="form-group">
        <label for="target">المستهدفون</label>
        <input id="target" type="text" placeholder="حدد الفئة المستهدفة" oninput="sync('target',this.value)">
      </div>

      <div class="form-group">
        <label for="count">عدد المستفيدين</label>
        <input id="count" type="text" placeholder="أدخل العدد" oninput="sync('count',this.value)">
      </div>

      <div class="form-group">
        <label for="teacher">اسم المعلم</label>
        <input id="teacher" type="text" placeholder="أدخل اسم المعلم" oninput="sync('teacher',this.value)">
      </div>

      <div class="form-group">
        <label for="principal">اسم مدير المدرسة</label>
        <input id="principal" type="text" placeholder="أدخل اسم مدير المدرسة" oninput="sync('principal',this.value)">
      </div>
    </div>

    <!-- وصف مختصر مع نصوص افتراضية -->
    <div class="form-group">
      <label for="desc1Input">وصف مختصر (15 كلمة)</label>
      <textarea id="desc1Input" placeholder="أدخل وصف مختصر للتقرير (15 كلمة كحد أقصى)" oninput="limitWords(this,'desc1','c1')"></textarea>
      <div class="default-text-buttons">
        <button class="default-btn" onclick="pasteDefaultText('desc1Input', defaultTexts.desc1[0])">لصق النص ١</button>
        <button class="default-btn" onclick="pasteDefaultText('desc1Input', defaultTexts.desc1[1])">لصق النص ٢</button>
        <button class="default-btn" onclick="pasteDefaultText('desc1Input', defaultTexts.desc1[2])">لصق النص ٣</button>
        <button class="clear-btn" onclick="clearText('desc1Input', 'desc1', 'c1')">مسح النص</button>
      </div>
      <div class="counter-container">
        <div class="counter" id="c1">0 / 15 كلمة</div>
        <div class="counter">الكلمات المتبقية: <span id="c1-remaining">15</span></div>
      </div>
    </div>

    <!-- إجراءات التنفيذ مع نصوص افتراضية -->
    <div class="form-group">
      <label for="desc2Input">إجراءات التنفيذ (15 كلمة)</label>
      <textarea id="desc2Input" placeholder="أدخل إجراءات التنفيذ (15 كلمة كحد أقصى)" oninput="limitWords(this,'desc2','c2')"></textarea>
      <div class="default-text-buttons">
        <button class="default-btn" onclick="pasteDefaultText('desc2Input', defaultTexts.desc2[0])">لصق النص ١</button>
        <button class="default-btn" onclick="pasteDefaultText('desc2Input', defaultTexts.desc2[1])">لصق النص ٢</button>
        <button class="default-btn" onclick="pasteDefaultText('desc2Input', defaultTexts.desc2[2])">لصق النص ٣</button>
        <button class="clear-btn" onclick="clearText('desc2Input', 'desc2', 'c2')">مسح النص</button>
      </div>
      <div class="counter-container">
        <div class="counter" id="c2">0 / 15 كلمة</div>
        <div class="counter">الكلمات المتبقية: <span id="c2-remaining">15</span></div>
      </div>
    </div>

    <!-- النتائج مع نصوص افتراضية -->
    <div class="form-group">
      <label for="desc3Input">النتائج (15 كلمة)</label>
      <textarea id="desc3Input" placeholder="أدخل النتائج المتحققة (15 كلمة كحد أقصى)" oninput="limitWords(this,'desc3','c3')"></textarea>
      <div class="default-text-buttons">
        <button class="default-btn" onclick="pasteDefaultText('desc3Input', defaultTexts.desc3[0])">لصق النص ١</button>
        <button class="default-btn" onclick="pasteDefaultText('desc3Input', defaultTexts.desc3[1])">لصق النص ٢</button>
        <button class="default-btn" onclick="pasteDefaultText('desc3Input', defaultTexts.desc3[2])">لصق النص ٣</button>
        <button class="clear-btn" onclick="clearText('desc3Input', 'desc3', 'c3')">مسح النص</button>
      </div>
      <div class="counter-container">
        <div class="counter" id="c3">0 / 15 كلمة</div>
        <div class="counter">الكلمات المتبقية: <span id="c3-remaining">15</span></div>
      </div>
    </div>

    <!-- التوصيات مع نصوص افتراضية -->
    <div class="form-group">
      <label for="desc4Input">التوصيات (15 كلمة)</label>
      <textarea id="desc4Input" placeholder="أدخل التوصيات المقترحة (15 كلمة كحد أقصى)" oninput="limitWords(this,'desc4','c4')"></textarea>
      <div class="default-text-buttons">
        <button class="default-btn" onclick="pasteDefaultText('desc4Input', defaultTexts.desc4[0])">لصق النص ١</button>
        <button class="default-btn" onclick="pasteDefaultText('desc4Input', defaultTexts.desc4[1])">لصق النص ٢</button>
        <button class="default-btn" onclick="pasteDefaultText('desc4Input', defaultTexts.desc4[2])">لصق النص ٣</button>
        <button class="clear-btn" onclick="clearText('desc4Input', 'desc4', 'c4')">مسح النص</button>
      </div>
      <div class="counter-container">
        <div class="counter" id="c4">0 / 15 كلمة</div>
        <div class="counter">الكلمات المتبقية: <span id="c4-remaining">15</span></div>
      </div>
    </div>

    <div class="form-group">
      <label>إرفاق الصور (صورتان كحد أقصى)</label>
      <div class="file-upload">
        <input type="file" id="imagesInput" multiple accept="image/*">
        <label for="imagesInput">
          <span class="btn-icon">📷</span>
          <span>انقر لاختيار الصور أو اسحبها هنا</span>
        </label>
        <div class="file-info" id="fileInfo">لم يتم اختيار أي صور</div>
      </div>
    </div>

    <div class="buttons-container">
      <button class="btn btn-primary" onclick="preparePrint()">
        <span class="btn-icon">📄</span>
        <span>تصدير تقرير PDF</span>
      </button>
      <button class="btn btn-secondary" onclick="resetForm()">
        <span class="btn-icon">🔄</span>
        <span>مسح جميع الخانات</span>
      </button>
    </div>
  </div>
</div>

<!-- قسم التقرير للطباعة (غير متغير) -->
<div class="report">

<div class="header">
<div id="edu"></div>
<div id="school"></div>
</div>

<div class="info-grid">
<div class="info-box"><span>البند</span><div id="axis"></div></div>
<div class="info-box"><span>العنوان</span><div id="title"></div></div>
<div class="info-box"><span>التاريخ</span><div id="date"></div></div>
<div class="info-box"><span>المستهدفون</span><div id="target"></div></div>
<div class="info-box"><span>عدد المستفيدين</span><div id="count"></div></div>
</div>

<div class="grid-desc">
<div class="desc-box big"><strong>وصف مختصر</strong><p id="desc1"></p></div>
<div class="vertical">⇄</div>
<div class="desc-box big"><strong>إجراءات التنفيذ</strong><p id="desc2"></p></div>
</div>

<div class="grid-desc">
<div class="desc-box small"><strong>النتائج</strong><p id="desc3"></p></div>
<div class="vertical">⇄</div>
<div class="desc-box small"><strong>التوصيات</strong><p id="desc4"></p></div>
</div>

<div class="images" id="imagesContainer"></div>

<div class="signatures">
<div class="signature-box">
اسم المعلم: <strong id="teacher"></strong>
<div class="signature-line"></div>
التوقيع
</div>
<div class="signature-box">
مدير المدرسة: <strong id="principal"></strong>
<div class="signature-line"></div>
التوقيع
</div>
</div>

</div>

<script>
// بيانات التقارير التربوية
const reportCategories = {
  "تحسين نواتج التعلم والتحصيل الدراسي": [
    "تقرير نشاط إثرائي",
    "تقرير تنفيذ اختبار تحسن",
    "تقرير تحليل النتائج",
    "تقرير مقارنة السلاسل الزمنية",
    "تقرير تصنيف الطلاب",
    "تقرير تحفيز الطلاب",
    "تقرير دراسة حالة",
    "تقرير البحث الإجرائي",
    "تقرير نقل أثر التدريب",
    "تقرير التدريب على الاختبارات المعيارية"
  ],
  "الدعم العلاجي والتدخلات التعليمية": [
    "تقرير خطة علاجية",
    "تقرير سجل الخطط العلاجية",
    "تقرير رعاية الطلاب المتأخرين دراسيًا",
    "تقرير كشف المتابعة",
    "تقرير إشعار ولي الأمر عن مستوى ابنه"
  ],
  "التدريس والتعلم داخل الصف": [
    "تقرير أنشطة صفية",
    "تقرير درس تم تنفيذه",
    "تقرير تنفيذ درس تطبيقي",
    "تقرير تعليم تعاوني بين الطلاب",
    "تقرير الفصول المقلوبة",
    "تقرير توزيع وقت الحصة",
    "تقرير تطوير البيئة الصفية",
    "تقرير حصة النشاط"
  ],
  "التخطيط والتنظيم التعليمي": [
    "تقرير خطة أسبوعية",
    "تقرير تفعيل الخطة الأسبوعية",
    "تقرير توزيع المنهج",
    "تقرير تفعيل حصص النشاط"
  ],
  "الأنشطة المدرسية واللاصفية": [
    "تقرير تنفيذ إذاعة مدرسية",
    "تقرير الاحتفال باليوم الوطني",
    "تقرير مبادرة تطوعية",
    "تقرير المعلم الصغير"
  ],
  "التقويم والمتابعة والتوثيق": [
    "تقرير سجل الدرجات الإلكتروني",
    "تقرير سجل التغذية الراجعة من الطلاب",
    "تقرير سجل رعاية الموهوبين",
    "تقرير سجل التواصل مع أولياء الأمور",
    "تقارير الجرد (للمختبرات وغرف المصادر)"
  ],
  "التواصل والشراكة مع الأسرة": [
    "تقرير التواصل مع ولي الأمر",
    "تقرير حضور اجتماع أولياء الأمور",
    "تقرير إشعار ولي الأمر",
    "تقرير سجل التواصل مع أولياء الأمور"
  ],
  "التطوير المهني وبناء القدرات": [
    "تقرير حضور دورات وورش تدريبية",
    "تقرير الورش التدريبية التي قدمتها",
    "تقرير تبادل الزيارات",
    "تقرير مجتمعات التعلم",
    "تقرير المجتمعات المهنية"
  ],
  "التميز والجودة": [
    "تقرير عضوية لجنة التميز والجودة",
    "تقرير متابعة مؤشرات الأداء",
    "تقرير توثيق الممارسات المتميزة",
    "تقرير متابعة خطط التحسين",
    "تقرير قياس رضا المستفيدين",
    "تقرير مبادرات التميز"
  ],
  "التحول الرقمي والابتكار": [
    "تقرير تفعيل المنصات التعليمية",
    "تقرير المحتوى الرقمي المنتج",
    "تقرير الاختبارات الذكية",
    "تقرير توظيف الذكاء الاصطناعي",
    "تقرير الوسائل التعليمية المبتكرة"
  ],
  "السلوك والإرشاد التربوي": [
    "تقرير تعزيز السلوك الإيجابي",
    "تقرير حل مشكلة تربوية",
    "تقرير متابعة حالات سلوكية",
    "تقرير جلسات إرشادية"
  ],
  "المبادرات والشراكات المجتمعية": [
    "تقرير مبادرة تعليمية",
    "تقرير مبادرة تطوعية",
    "تقرير شراكة مجتمعية تعليمية"
  ],
  "السلامة والصحة المدرسية": [
    "تقرير تنفيذ فرضية إخلاء",
    "تقرير التوعية الصحية",
    "تقرير إجراءات السلامة المدرسية"
  ]
};

// النصوص الافتراضية لكل خانة (3 نصوص لكل خانة)
const defaultTexts = {
  desc1: [
    "تم تنفيذ نشاط إثرائي لتحسين مستوى الطلاب في مادة الرياضيات. تضمن النشاط تمارين تفاعلية ومسابقات جماعية.",
    "نفذت حصة تطبيقية لتعزيز مهارات التفكير الناقد لدى الطلاب. ركزت على حل المشكلات والتحليل المنطقي.",
    "تم تنظيم ورشة عمل لتعزيز التعلم النشط. شارك فيها طلاب الصفوف العليا في أنشطة عملية وتجريبية."
  ],
  desc2: [
    "تقسيم الطلاب لمجموعات عمل صغيرة. توزيع المهام حسب القدرات. استخدام وسائل تعليمية متنوعة. متابعة الأداء بشكل فردي.",
    "تحضير الدروس مسبقاً مع الوسائل المناسبة. تنظيم بيئة صفية محفزة. تطبيق استراتيجيات تعليمية حديثة. تقييم فوري للإنجاز.",
    "تحديد الأهداف التعليمية بوضوح. اختيار الأنشطة المناسبة للمستويات. توفير المواد المساعدة. تنفيذ التغذية الراجعة المستمرة."
  ],
  desc3: [
    "تحسن ملحوظ في مستوى التحصيل الدراسي. ارتفاع معدلات المشاركة الصفية. زيادة تفاعل الطلاب مع الأنشطة.",
    "تحقيق الأهداف التعليمية المخطط لها. تفاعل إيجابي من الطلاب. تحسن في نتائج التقييمات المستمرة.",
    "زيادة دافعية الطلاب للتعلم. تحسن في المهارات الأساسية. نجاح في تحقيق نواتج التعلم المستهدفة."
  ],
  desc4: [
    "الاستمرار في تطبيق الأنشطة الإثرائية. تعميم التجربة على بقية الفصول. تنظيم دورات تدريبية للمعلمين.",
    "تطوير المزيد من الوسائل التعليمية. توسيع نطاق الأنشطة اللاصفية. تعزيز الشراكة مع أولياء الأمور.",
    "توثيق الممارسات الناجحة. الاستفادة من التغذية الراجعة. التخطيط لأنشطة مستقبلية مماثلة."
  ]
};

// دالة لصق النص الافتراضي
function pasteDefaultText(textareaId, text) {
  const textarea = document.getElementById(textareaId);
  if (!textarea) return;
  
  // مسح النص الحالي
  textarea.value = text;
  
  // تشغيل حدث oninput يدوياً لتحديث العداد
  const event = new Event('input', { bubbles: true });
  textarea.dispatchEvent(event);
  
  // إظهار رسالة تأكيد
  showMessage('تم لصق النص الافتراضي');
}

// دالة مسح النص
function clearText(textareaId, targetId, counterId) {
  const textarea = document.getElementById(textareaId);
  if (!textarea) return;
  
  // مسح النص
  textarea.value = '';
  
  // تشغيل حدث oninput يدوياً
  const event = new Event('input', { bubbles: true });
  textarea.dispatchEvent(event);
  
  // إظهار رسالة تأكيد
  showMessage('تم مسح النص');
}

// دالة إظهار رسالة
function showMessage(message) {
  const messageDiv = document.createElement('div');
  messageDiv.textContent = message;
  messageDiv.style.cssText = `
    position: fixed;
    top: 20px;
    left: 50%;
    transform: translateX(-50%);
    background: var(--accent-color);
    color: white;
    padding: 10px 20px;
    border-radius: 6px;
    z-index: 10000;
    font-size: 14px;
    box-shadow: var(--shadow);
  `;
  
  document.body.appendChild(messageDiv);
  
  setTimeout(() => {
    document.body.removeChild(messageDiv);
  }, 2000);
}

function sync(id,val){
  document.getElementById(id).textContent = val;
  
  // تحديث حقل البند التربوي في التقرير
  if (id === 'title') {
    // تحديث البند التربوي أيضاً عند اختيار عنوان التقرير
    const educationItem = document.getElementById('education-item');
    if (educationItem.value) {
      document.getElementById('axis').textContent = educationItem.value;
    }
  }
}

function updateReportTitles() {
  const educationItem = document.getElementById('education-item');
  const reportTitleSelect = document.getElementById('report-title-select');
  const selectedCategory = educationItem.value;
  
  // تحديث حقل البند التربوي في التقرير
  document.getElementById('axis').textContent = selectedCategory;
  
  // مسح القائمة الحالية
  reportTitleSelect.innerHTML = '<option value="">اختر عنوان التقرير</option>';
  
  // إضافة الخيارات المناسبة
  if (selectedCategory && reportCategories[selectedCategory]) {
    reportCategories[selectedCategory].forEach(report => {
      const option = document.createElement('option');
      option.value = report;
      option.textContent = report;
      reportTitleSelect.appendChild(option);
    });
  }
}

function limitWords(el, target, counterId){
  let text = el.value.trim();
  let words = text === '' ? [] : text.replace(/\s+/g, ' ').split(' ').filter(w => w);
  
  if(words.length > 15){
    words = words.slice(0, 15);
    el.value = words.join(' ');
    text = el.value;
    words = words.slice(0, 15);
  }
  
  const counter = document.getElementById(counterId);
  const remainingElement = document.getElementById(counterId.replace('c', 'c') + '-remaining');
  const remaining = 15 - words.length;
  
  counter.textContent = `${words.length} / 15 كلمة`;
  counter.classList.toggle('limit', words.length === 15);
  
  if (remainingElement) {
    remainingElement.textContent = remaining;
    remainingElement.style.color = remaining <= 3 ? '#e74c3c' : '#6a8a85';
    remainingElement.style.fontWeight = remaining <= 3 ? 'bold' : 'normal';
  }
  
  document.getElementById(target).textContent = text;
}

const imagesInput = document.getElementById('imagesInput');
const imagesContainer = document.getElementById('imagesContainer');
const fileInfo = document.getElementById('fileInfo');

imagesInput.addEventListener('change', e => {
  imagesContainer.innerHTML = '';
  const files = [...e.target.files];
  
  if(files.length > 2){
    alert('يسمح بإرفاق صورتين فقط');
    imagesInput.value = '';
    fileInfo.textContent = 'لم يتم اختيار أي صور';
    fileInfo.style.color = '#e74c3c';
    return;
  }
  
  if (files.length === 0) {
    fileInfo.textContent = 'لم يتم اختيار أي صور';
    fileInfo.style.color = '#6a8a85';
    return;
  }
  
  fileInfo.textContent = `تم اختيار ${files.length} صورة${files.length > 1 ? 'تين' : ''}`;
  fileInfo.style.color = '#27ae60';
  
  files.forEach(f => {
    const reader = new FileReader();
    reader.onload = ev => {
      const img = document.createElement('img');
      img.src = ev.target.result;
      imagesContainer.appendChild(img);
    };
    reader.readAsDataURL(f);
  });
});

// دالة إعداد الطباعة مع رسالة تأكيد
function preparePrint() {
  // التحقق من الحقول المطلوبة
  const requiredFields = ['education-department', 'school', 'education-item', 'report-title-select', 'date'];
  let missingFields = [];
  
  requiredFields.forEach(fieldId => {
    const field = document.getElementById(fieldId);
    const label = field.previousElementSibling ? field.previousElementSibling.textContent : fieldId;
    
    if (!field.value) {
      missingFields.push(label);
    }
  });
  
  if (missingFields.length > 0) {
    alert(`الرجاء تعبئة الحقول التالية:\n${missingFields.join('\n')}`);
    return;
  }
  
  // عرض رسالة التأكيد
  const confirmation = document.getElementById('confirmationMessage');
  confirmation.classList.add('show');
  
  // إخفاء الرسالة بعد 3 ثوان
  setTimeout(() => {
    confirmation.classList.remove('show');
  }, 3000);
  
  // بدء عملية الطباعة بعد تأخير قصير
  setTimeout(() => {
    window.print();
  }, 500);
}

function resetForm(){
  if(!confirm('هل أنت متأكد من رغبتك في مسح جميع الخانات؟')) return;
  
  // مسح جميع حقول الإدخال
  document.querySelectorAll('input[type="text"], input[type="file"], textarea, select').forEach(e => {
    e.value = '';
  });
  
  // مسح المحتوى النصي
  document.querySelectorAll('[id]').forEach(e => {
    if (!['c1', 'c2', 'c3', 'c4', 'c1-remaining', 'c2-remaining', 'c3-remaining', 'c4-remaining'].includes(e.id)) {
      e.textContent = '';
    }
  });
  
  // إعادة تعيين العدادات
  ['c1', 'c2', 'c3', 'c4'].forEach(counterId => {
    const counter = document.getElementById(counterId);
    if (counter) {
      counter.textContent = '0 / 15 كلمة';
      counter.classList.remove('limit');
    }
  });
  
  // إعادة تعيين العدادات المتبقية
  ['c1-remaining', 'c2-remaining', 'c3-remaining', 'c4-remaining'].forEach(id => {
    const remaining = document.getElementById(id);
    if (remaining) {
      remaining.textContent = '15';
      remaining.style.color = '#6a8a85';
      remaining.style.fontWeight = 'normal';
    }
  });
  
  imagesContainer.innerHTML = '';
  fileInfo.textContent = 'لم يتم اختيار أي صور';
  fileInfo.style.color = '#6a8a85';
  
  // إعادة تعيين قائمة عناوين التقارير
  document.getElementById('report-title-select').innerHTML = '<option value="">اختر عنوان التقرير بعد اختيار البند التربوي</option>';
  
  // إعادة التركيز على أول حقل
  document.getElementById('education-department').focus();
}
</script>

</body>
</html>