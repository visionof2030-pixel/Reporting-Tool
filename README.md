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
  --shadow: 0 2px 8px rgba(10, 59, 64, 0.08);
  --shadow-hover: 0 4px 12px rgba(10, 59, 64, 0.12);
  --radius: 8px;
  --transition: all 0.3s ease;
}

body{
  font-family: 'KufamLocal', 'Segoe UI', sans-serif;
  background: #f8fbfa;
  margin: 0;
  padding: 15px;
  color: var(--text-color);
  line-height: 1.5;
}

/* ===== الهيدر الجديد المصغر ===== */
.tool-container {
  max-width: 1000px;
  margin: 0 auto 20px;
}

.tool-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 15px;
  padding: 8px 12px;
  background: #0a3b40;
  border-radius: 6px;
  box-shadow: var(--shadow);
}

.header-left {
  display: flex;
  align-items: center;
  gap: 10px;
}

.header-logo {
  width: 35px;
  height: 35px;
  object-fit: contain;
  filter: brightness(0) invert(1);
}

.header-title {
  font-size: 14px;
  font-weight: 700;
  color: white;
}

.header-right {
  font-size: 12px;
  color: rgba(255, 255, 255, 0.9);
}

.tool{
  background: white;
  padding: 20px;
  border-radius: var(--radius);
  box-shadow: var(--shadow);
}

/* ===== تحسين الحقول ===== */
.form-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 15px;
  margin-bottom: 20px;
}

@media (max-width: 768px) {
  .form-grid {
    grid-template-columns: 1fr;
  }
}

.form-group {
  margin-bottom: 15px;
  position: relative;
}

.form-group label{
  display: block;
  font-weight: 700;
  margin-bottom: 6px;
  color: var(--primary-color);
  font-size: 13px;
}

.form-group input,
.form-group textarea,
.form-group select {
  width: 100%;
  padding: 10px 12px;
  border: 1px solid var(--border-color);
  border-radius: 6px;
  font-family: inherit;
  font-size: 14px;
  background-color: white;
  transition: var(--transition);
  box-sizing: border-box;
}

.form-group input:focus,
.form-group textarea:focus,
.form-group select:focus {
  outline: none;
  border-color: var(--accent-color);
  box-shadow: 0 0 0 2px rgba(65, 191, 179, 0.1);
}

.form-group textarea{
  resize: vertical;
  min-height: 80px;
  font-size: 13px;
}

.form-group select {
  cursor: pointer;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='10' height='10' fill='%230a3b40' viewBox='0 0 16 16'%3E%3Cpath d='M7.247 11.14 2.451 5.658C1.885 5.013 2.345 4 3.204 4h9.592a1 1 0 0 1 .753 1.659l-4.796 5.48a1 1 0 0 1-1.506 0z'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: left 12px center;
  background-size: 10px;
  padding-right: 12px;
}

/* ===== أزرار النصوص الافتراضية ===== */
.default-text-buttons {
  display: flex;
  gap: 6px;
  margin-top: 6px;
  flex-wrap: wrap;
}

.default-btn {
  padding: 5px 10px;
  background: var(--light-gray);
  border: 1px solid var(--border-color);
  border-radius: 4px;
  font-size: 11px;
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
  padding: 5px 10px;
  background: #ffebee;
  border: 1px solid #ffcdd2;
  border-radius: 4px;
  font-size: 11px;
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
  margin-top: 4px;
}

.counter{
  font-size: 11px;
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
  gap: 10px;
  margin-top: 20px;
}

@media (max-width: 768px) {
  .buttons-container {
    flex-direction: column;
  }
}

.btn {
  flex: 1;
  padding: 12px 20px;
  border: none;
  border-radius: 6px;
  font-size: 14px;
  font-weight: 700;
  cursor: pointer;
  transition: var(--transition);
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
}

.btn-primary {
  background: var(--primary-color);
  color: white;
}

.btn-primary:hover {
  background: var(--secondary-color);
  transform: translateY(-2px);
}

.btn-secondary {
  background: #7f8c8d;
  color: white;
}

.btn-secondary:hover {
  background: #6c7b7d;
  transform: translateY(-2px);
}

.btn-icon {
  font-size: 16px;
}

/* ===== تحسين تحميل الصور ===== */
.file-upload {
  position: relative;
  margin-top: 6px;
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
  padding: 10px;
  background-color: var(--light-gray);
  border: 1px dashed var(--border-color);
  border-radius: 6px;
  text-align: center;
  color: var(--primary-color);
  font-weight: 600;
  cursor: pointer;
  transition: var(--transition);
  z-index: 1;
  position: relative;
  font-size: 13px;
}

.file-upload label:hover {
  background-color: #e0ecea;
  border-color: var(--accent-color);
}

.file-upload .file-info {
  margin-top: 6px;
  font-size: 11px;
  color: #6a8a85;
  text-align: center;
}

/* ===== التقرير (لطباعة PDF - تم تحسينه) ===== */
.report{display:none;}
@page{size:A4;margin:8mm;}

@media print{
  body{
    background:white;
    padding:0;
    margin:0;
    font-size: 11px;
  }
  
  .tool{display:none}
  .report{
    display:block;
    width:100%;
    height:100%;
    margin:0;
    padding:0;
  }

  /* ===== الهيدر المصغر ===== */
  .header{
    background:#0a3b40;
    color:white;
    padding:2px 3px;
    border-radius:3px;
    text-align:center;
    font-size:9px;
    margin-bottom:3px;
    page-break-inside: avoid;
  }

  /* ===== معلومات التقرير (مصغّرة) ===== */
  .info-grid{
    display:grid;
    grid-template-columns:repeat(5,1fr);
    gap:2px;
    margin-bottom:3px;
    page-break-inside: avoid;
  }
  .info-box{
    border:1px solid var(--border-color);
    border-radius:4px;
    padding:2px;
    text-align:center;
    font-size:8px;
    min-height: 30px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    page-break-inside: avoid;
  }
  .info-box span{
    display:block;
    background:#0a3b40;
    color:white;
    border-radius:2px;
    padding:1px;
    font-weight:700;
    font-size:7px;
    margin-bottom:1px;
    page-break-inside: avoid;
  }

  /* ===== المحتوى ===== */
  .grid-desc{
    display:flex;
    gap:4px;
    margin-bottom:4px;
    page-break-inside: avoid;
  }

  .desc-box{
    border:1px solid var(--border-color);
    border-radius:5px;
    padding:4px 5px;
    background:#f9fbfb;
    font-size:9px;
    display:flex;
    flex-direction:column;
    min-height: 70px;
    page-break-inside: avoid;
  }
  .desc-box.big{
    flex:1;
    min-height: 70px;
    page-break-inside: avoid;
  }
  .desc-box.small{
    flex:1;
    min-height: 60px;
    page-break-inside: avoid;
  }

  .desc-box strong{
    border-bottom:1px dashed var(--border-color);
    padding-bottom:2px;
    margin-bottom:3px;
    color:#0a3b40;
    font-size:9px;
    page-break-inside: avoid;
  }
  .desc-box p{
    white-space:pre-line;
    flex:1;
    margin:0;
    font-size:8.5px;
    page-break-inside: avoid;
  }

  .vertical{
    width:18px;
    background:#eef3f1;
    border-radius:4px;
    display:flex;
    align-items:center;
    justify-content:center;
    font-weight:700;
    font-size:9px;
    page-break-inside: avoid;
  }

  /* ===== الصور ===== */
  .images{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:5px;
    margin-top:6px;
    page-break-inside: avoid;
  }
  .images img{
    width:100%;
    height:80px;
    object-fit:cover;
    border-radius:4px;
    page-break-inside: avoid;
  }

  /* ===== التوقيعات ===== */
  .signatures{
    margin-top:12px;
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:20px;
    border-top:1px solid var(--border-color);
    padding-top:8px;
    page-break-inside: avoid;
    page-break-before: avoid;
  }
  .signature-box{
    text-align:center;
    font-size:9px;
    page-break-inside: avoid;
  }
  .signature-line{
    border-bottom:1px solid #000;
    height:18px;
    margin:4px 0;
    page-break-inside: avoid;
  }
  
  /* منع انبثاق صفحة جديدة */
  .report * {
    page-break-inside: avoid;
    page-break-after: avoid;
    page-break-before: avoid;
  }
  
  .report {
    page-break-inside: avoid;
    orphans: 4;
    widows: 4;
  }
}
</style>
</head>

<body>

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
        <select id="education-department" oninput="syncValue('edu', this.value)">
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
        <input id="school" type="text" placeholder="أدخل اسم المدرسة" oninput="syncValue('school',this.value)">
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
        <select id="report-title-select" onchange="syncValue('title', this.value)">
          <option value="">اختر عنوان التقرير بعد اختيار البند التربوي</option>
        </select>
      </div>

      <div class="form-group">
        <label for="date">تاريخ التنفيذ</label>
        <input id="date" type="text" placeholder="يوم/شهر/سنة" oninput="syncValue('date',this.value)" value="١٤٤٦/٠٧/٢٠">
      </div>

      <div class="form-group">
        <label for="target">المستهدفون</label>
        <input id="target" type="text" placeholder="الطلاب - الفئة العمرية - الصف" oninput="syncValue('target',this.value)" value="طلاب الصف السادس">
      </div>

      <div class="form-group">
        <label for="count">عدد المستفيدين</label>
        <input id="count" type="text" placeholder="أدخل العدد" oninput="syncValue('count',this.value)" value="٣٠">
      </div>

      <div class="form-group">
        <label for="teacher">اسم المعلم</label>
        <input id="teacher" type="text" placeholder="أدخل اسم المعلم" oninput="syncValue('teacher',this.value)" value="أحمد بن محمد السعيد">
      </div>

      <div class="form-group">
        <label for="principal">اسم مدير المدرسة</label>
        <input id="principal" type="text" placeholder="أدخل اسم مدير المدرسة" oninput="syncValue('principal',this.value)" value="سعود بن عبدالله الحربي">
      </div>
    </div>

    <!-- وصف مختصر مع نصوص افتراضية -->
    <div class="form-group">
      <label for="desc1Input">وصف مختصر (15 كلمة)</label>
      <textarea id="desc1Input" placeholder="أدخل وصف مختصر للتقرير (15 كلمة كحد أقصى)" oninput="limitWords(this,'desc1','c1')"></textarea>
      <div class="default-text-buttons">
        <button class="default-btn" onclick="pasteDefaultText('desc1Input', defaultTexts.desc1[0])">نص ١</button>
        <button class="default-btn" onclick="pasteDefaultText('desc1Input', defaultTexts.desc1[1])">نص ٢</button>
        <button class="default-btn" onclick="pasteDefaultText('desc1Input', defaultTexts.desc1[2])">نص ٣</button>
        <button class="clear-btn" onclick="clearText('desc1Input', 'desc1', 'c1')">مسح</button>
      </div>
      <div class="counter-container">
        <div class="counter" id="c1">0 / 15 كلمة</div>
      </div>
    </div>

    <!-- إجراءات التنفيذ مع نصوص افتراضية -->
    <div class="form-group">
      <label for="desc2Input">إجراءات التنفيذ (15 كلمة)</label>
      <textarea id="desc2Input" placeholder="أدخل إجراءات التنفيذ (15 كلمة كحد أقصى)" oninput="limitWords(this,'desc2','c2')"></textarea>
      <div class="default-text-buttons">
        <button class="default-btn" onclick="pasteDefaultText('desc2Input', defaultTexts.desc2[0])">نص ١</button>
        <button class="default-btn" onclick="pasteDefaultText('desc2Input', defaultTexts.desc2[1])">نص ٢</button>
        <button class="default-btn" onclick="pasteDefaultText('desc2Input', defaultTexts.desc2[2])">نص ٣</button>
        <button class="clear-btn" onclick="clearText('desc2Input', 'desc2', 'c2')">مسح</button>
      </div>
      <div class="counter-container">
        <div class="counter" id="c2">0 / 15 كلمة</div>
      </div>
    </div>

    <!-- النتائج مع نصوص افتراضية -->
    <div class="form-group">
      <label for="desc3Input">النتائج (15 كلمة)</label>
      <textarea id="desc3Input" placeholder="أدخل النتائج المتحققة (15 كلمة كحد أقصى)" oninput="limitWords(this,'desc3','c3')"></textarea>
      <div class="default-text-buttons">
        <button class="default-btn" onclick="pasteDefaultText('desc3Input', defaultTexts.desc3[0])">نص ١</button>
        <button class="default-btn" onclick="pasteDefaultText('desc3Input', defaultTexts.desc3[1])">نص ٢</button>
        <button class="default-btn" onclick="pasteDefaultText('desc3Input', defaultTexts.desc3[2])">نص ٣</button>
        <button class="clear-btn" onclick="clearText('desc3Input', 'desc3', 'c3')">مسح</button>
      </div>
      <div class="counter-container">
        <div class="counter" id="c3">0 / 15 كلمة</div>
      </div>
    </div>

    <!-- التوصيات مع نصوص افتراضية -->
    <div class="form-group">
      <label for="desc4Input">التوصيات (15 كلمة)</label>
      <textarea id="desc4Input" placeholder="أدخل التوصيات المقترحة (15 كلمة كحد أقصى)" oninput="limitWords(this,'desc4','c4')"></textarea>
      <div class="default-text-buttons">
        <button class="default-btn" onclick="pasteDefaultText('desc4Input', defaultTexts.desc4[0])">نص ١</button>
        <button class="default-btn" onclick="pasteDefaultText('desc4Input', defaultTexts.desc4[1])">نص ٢</button>
        <button class="default-btn" onclick="pasteDefaultText('desc4Input', defaultTexts.desc4[2])">نص ٣</button>
        <button class="clear-btn" onclick="clearText('desc4Input', 'desc4', 'c4')">مسح</button>
      </div>
      <div class="counter-container">
        <div class="counter" id="c4">0 / 15 كلمة</div>
      </div>
    </div>

    <div class="form-group">
      <label>إرفاق الصور (صورتان كحد أقصى)</label>
      <div class="file-upload">
        <input type="file" id="imagesInput" multiple accept="image/*">
        <label for="imagesInput">
          <span class="btn-icon">📷</span>
          <span>انقر لاختيار الصور (صورتان كحد أقصى)</span>
        </label>
        <div class="file-info" id="fileInfo">لم يتم اختيار أي صور</div>
      </div>
    </div>

    <div class="buttons-container">
      <button class="btn btn-primary" onclick="preparePrint()">
        <span class="btn-icon">📄</span>
        <span>تصدير PDF</span>
      </button>
      <button class="btn btn-secondary" onclick="resetForm()">
        <span class="btn-icon">🔄</span>
        <span>مسح الكل</span>
      </button>
    </div>
  </div>
</div>

<!-- قسم التقرير للطباعة -->
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

// النصوص الافتراضية المحسنة (بدون ذكر مواد دراسية)
const defaultTexts = {
  desc1: [
    "تم تنفيذ نشاط تربوي لتعزيز المهارات الأساسية لدى الطلاب وتحسين مستوى التحصيل الدراسي بشكل عام.",
    "نفذت مبادرة تعليمية هادفة لتنمية التفكير الناقد وحل المشكلات عند الطلاب المشاركين في البرنامج.",
    "تم تطبيق استراتيجيات تعليمية مبتكرة لتحسين نواتج التعلم وزيادة تفاعل الطلاب داخل البيئة التعليمية."
  ],
  desc2: [
    "تخطيط البرنامج بدقة وتحديد الأهداف. توزيع المهام على المجموعات. استخدام وسائل تعليمية متنوعة. المتابعة المستمرة للأداء.",
    "تحضير المواد التعليمية المناسبة. تطبيق أساليب التعلم النشط. توفير بيئة تعليمية محفزة. تقييم التقدم بشكل دوري.",
    "تعزيز العمل الجماعي والتعاوني. تنويع أساليب العرض والتقديم. التركيز على المهارات التطبيقية. تقديم التغذية الراجعة الفورية."
  ],
  desc3: [
    "تحسن واضح في مستوى التحصيل الدراسي. زيادة المشاركة الإيجابية للطلاب. ارتفاع نسبة التفاعل مع الأنشطة المقدمة.",
    "تحقيق الأهداف التعليمية المخطط لها. تفاعل إيجابي من المشاركين. تحسن في نتائج التقييمات والتقارير المقدمة.",
    "زيادة دافعية الطلاب نحو التعلم. تنمية المهارات الأساسية المستهدفة. نجاح في تحقيق نواتج التعلم المرجوة."
  ],
  desc4: [
    "الاستمرار في تطبيق البرامج الإثرائية الناجحة. تعميم التجارب المتميزة. تنظيم ورش عمل لتبادل الخبرات.",
    "تطوير الوسائل التعليمية المستخدمة. توسيع نطاق البرامج ليشمل فئات أكثر. تعزيز التعاون مع الجهات ذات العلاقة.",
    "توثيق الممارسات التعليمية الناجحة. الاستفادة من التغذية الراجعة للتحسين. التخطيط لبرامج مستقبلية مماثلة."
  ]
};

// دالة مزامنة القيم (تم إصلاحها)
function syncValue(id, value) {
  // تحديث العنصر في قسم التقرير
  const element = document.getElementById(id);
  if (element) {
    element.textContent = value;
  }
  
  // تحديث خاص للبند التربوي
  if (id === 'title') {
    const educationItem = document.getElementById('education-item');
    if (educationItem && educationItem.value) {
      const axisElement = document.getElementById('axis');
      if (axisElement) {
        axisElement.textContent = educationItem.value;
      }
    }
  }
}

// دالة تحديث عناوين التقارير
function updateReportTitles() {
  const educationItem = document.getElementById('education-item');
  const reportTitleSelect = document.getElementById('report-title-select');
  const selectedCategory = educationItem.value;
  
  // تحديث حقل البند التربوي في التقرير
  syncValue('axis', selectedCategory);
  
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

// دالة لصق النص الافتراضي
function pasteDefaultText(textareaId, text) {
  const textarea = document.getElementById(textareaId);
  if (!textarea) return;
  
  // مسح النص الحالي
  textarea.value = text;
  
  // تشغيل حدث oninput يدوياً لتحديث العداد
  const event = new Event('input', { bubbles: true });
  textarea.dispatchEvent(event);
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
}

// دالة عد الكلمات مع إصلاح
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
  if (counter) {
    counter.textContent = `${words.length} / 15 كلمة`;
    counter.classList.toggle('limit', words.length === 15);
  }
  
  const targetElement = document.getElementById(target);
  if (targetElement) {
    targetElement.textContent = text;
  }
}

// إعداد الصور
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

// دالة مزامنة جميع الحقول قبل الطباعة
function syncAllFields() {
  // قائمة بجميع الحقول التي يجب مزامنتها
  const fields = [
    { inputId: 'education-department', targetId: 'edu' },
    { inputId: 'school', targetId: 'school' },
    { inputId: 'education-item', targetId: 'axis' },
    { inputId: 'report-title-select', targetId: 'title' },
    { inputId: 'date', targetId: 'date' },
    { inputId: 'target', targetId: 'target' },
    { inputId: 'count', targetId: 'count' },
    { inputId: 'teacher', targetId: 'teacher' },
    { inputId: 'principal', targetId: 'principal' }
  ];
  
  fields.forEach(field => {
    const inputElement = document.getElementById(field.inputId);
    if (inputElement && inputElement.value) {
      syncValue(field.targetId, inputElement.value);
    }
  });
}

// دالة إعداد الطباعة
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
  
  // مزامنة جميع الحقول قبل الطباعة
  syncAllFields();
  
  // بدء عملية الطباعة مباشرة
  window.print();
}

// دالة إعادة تعيين النموذج
function resetForm(){
  if(!confirm('هل أنت متأكد من رغبتك في مسح جميع الخانات؟')) return;
  
  // مسح جميع حقول الإدخال
  document.querySelectorAll('input[type="text"], input[type="file"], textarea, select').forEach(e => {
    if (e.id === 'date') {
      e.value = '١٤٤٦/٠٧/٢٠'; // إعادة تعيين التاريخ الهجري
    } else if (e.id === 'target') {
      e.value = 'طلاب الصف السادس'; // قيمة افتراضية للمستهدفين
    } else if (e.id === 'count') {
      e.value = '٣٠'; // قيمة افتراضية للعدد
    } else if (e.id === 'teacher') {
      e.value = 'أحمد بن محمد السعيد'; // قيمة افتراضية لاسم المعلم
    } else if (e.id === 'principal') {
      e.value = 'سعود بن عبدالله الحربي'; // قيمة افتراضية لاسم المدير
    } else {
      e.value = '';
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
  
  // إعادة تعيين الصور
  imagesContainer.innerHTML = '';
  fileInfo.textContent = 'لم يتم اختيار أي صور';
  fileInfo.style.color = '#6a8a85';
  
  // إعادة تعيين قائمة عناوين التقارير
  document.getElementById('report-title-select').innerHTML = '<option value="">اختر عنوان التقرير بعد اختيار البند التربوي</option>';
  
  // مزامنة القيم الافتراضية
  syncAllFields();
  
  // إعادة التركيز على أول حقل
  document.getElementById('education-department').focus();
}

// تهيئة القيم الافتراضية عند تحميل الصفحة
document.addEventListener('DOMContentLoaded', function() {
  // مزامنة القيم الافتراضية عند تحميل الصفحة
  setTimeout(() => {
    syncAllFields();
  }, 100);
});
</script>

</body>
</html>