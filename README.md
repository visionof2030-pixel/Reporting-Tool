<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<title>أداة إعداد التقارير التعليمية</title>
<script src="https://cdn.jsdelivr.net/npm/umalqura@2.0.0/umalqura.min.js"></script>
<style>
@font-face{
  font-family:'KufamLocal';
  src:url('static/Kufam-Regular.ttf') format('truetype');
}

:root {
  --primary: #0a3b40;
  --secondary: #2a7c6f;
  --accent: #4a9b8d;
  --light: #f2f7f6;
  --light-gray: #e8f1ef;
  --text: #1a3c3a;
  --border: #c5d5d2;
  --shadow: rgba(10, 59, 64, 0.08);
}

body{
  font-family:'KufamLocal', sans-serif;
  background: linear-gradient(135deg, #eef7f5 0%, #e1ecea 100%);
  margin:0;
  padding:20px;
  color: var(--text);
}

/* ===== الأداة ===== */
.tool{
  max-width:900px;
  margin: 30px auto;
  background:white;
  padding:35px;
  border-radius:22px;
  box-shadow: 0 10px 30px var(--shadow);
  border: 1px solid var(--border);
}

.tool h2{
  text-align:center;
  color:var(--primary);
  margin-bottom:25px;
  font-size:28px;
  padding-bottom:15px;
  border-bottom: 2px solid var(--light-gray);
  position: relative;
}

.tool h2:after {
  content: '';
  position: absolute;
  bottom: -2px;
  right: 50%;
  transform: translateX(50%);
  width: 100px;
  height: 4px;
  background: var(--secondary);
  border-radius: 2px;
}

.input-group {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  margin-bottom: 15px;
}

@media (max-width: 768px) {
  .input-group {
    grid-template-columns: 1fr;
  }
}

.form-section {
  background: var(--light);
  padding: 20px;
  border-radius: 15px;
  margin-bottom: 25px;
  border: 1px solid var(--border);
}

.form-section h3 {
  color: var(--secondary);
  margin-top: 0;
  margin-bottom: 18px;
  font-size: 18px;
  padding-right: 10px;
  border-right: 3px solid var(--accent);
}

label{
  font-weight:700;
  margin-top:15px;
  display:block;
  color: var(--text);
  font-size: 15px;
  margin-bottom: 6px;
}

select, input, textarea{
  width:100%;
  padding:14px;
  margin-top:6px;
  border-radius:10px;
  border:2px solid var(--border);
  font-family:inherit;
  font-size: 15px;
  background: white;
  transition: all 0.3s ease;
  box-sizing: border-box;
}

select:focus, input:focus, textarea:focus{
  outline:none;
  border-color:var(--accent);
  box-shadow: 0 0 0 3px rgba(74, 155, 141, 0.2);
}

textarea{
  resize:none;
  min-height: 100px;
}

.counter{
  font-size:13px;
  margin-top:5px;
  color:var(--secondary);
  text-align: left;
}

.counter.limit{
  color:#c62828;
  font-weight:700;
}

.auto-texts {
  background: white;
  border: 1px dashed var(--border);
  border-radius: 10px;
  padding: 15px;
  margin-top: 15px;
  margin-bottom: 20px;
}

.auto-texts h4 {
  color: var(--primary);
  margin-top: 0;
  margin-bottom: 12px;
  font-size: 15px;
}

.auto-text-btn {
  display: inline-block;
  background: var(--light);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 8px 12px;
  margin: 0 5px 8px 0;
  font-size: 13px;
  cursor: pointer;
  transition: all 0.2s ease;
}

.auto-text-btn:hover {
  background: var(--accent);
  color: white;
  border-color: var(--accent);
}

.button-group {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  margin-top: 30px;
}

@media (max-width: 600px) {
  .button-group {
    grid-template-columns: 1fr;
  }
}

button{
  padding:16px;
  background:var(--primary);
  color:white;
  border:none;
  border-radius:12px;
  font-size:16px;
  font-weight:700;
  cursor:pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
}

button:hover{
  background:var(--secondary);
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(10, 59, 64, 0.2);
}

button:active{
  transform: translateY(0);
}

.export-btn{
  background: linear-gradient(to right, var(--primary), var(--secondary));
}

.reset-btn{
  background:#7a8c89;
}

.reset-btn:hover{
  background:#5a6c69;
}

.file-input-container {
  position: relative;
  margin-top: 6px;
}

.file-input-container input[type="file"] {
  position: absolute;
  right: 0;
  top: 0;
  opacity: 0;
  width: 100%;
  height: 100%;
  cursor: pointer;
}

.file-input-label {
  display: block;
  padding: 14px;
  background: white;
  border: 2px solid var(--border);
  border-radius: 10px;
  text-align: center;
  color: var(--text);
  cursor: pointer;
  transition: all 0.3s ease;
}

.file-input-label:hover {
  border-color: var(--accent);
  background: var(--light);
}

.file-input-label:after {
  content: "📁";
  margin-right: 8px;
}

.date-group {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 15px;
}

.date-group .date-input {
  display: flex;
  flex-direction: column;
}

.date-input label {
  font-size: 14px;
  color: var(--secondary);
}

.date-convert-btn {
  grid-column: span 2;
  background: var(--light-gray);
  border: 1px solid var(--border);
  color: var(--text);
  padding: 10px;
  border-radius: 8px;
  font-size: 14px;
  cursor: pointer;
  transition: all 0.3s ease;
  margin-top: 5px;
}

.date-convert-btn:hover {
  background: var(--accent);
  color: white;
}

/* ===== التقرير للطباعة ===== */
.report{display:none;}
@page{size:A4;margin:14mm;}

@media print{
  body{background:white;padding:0}
  .tool{display:none}
  .report{display:block}
  
  /* ===== الهيدر المصغر ===== */
  .header{
    background:#0a3b40;
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
    grid-template-columns:repeat(6,1fr);
    gap:5px;
    margin-bottom:6px;
  }
  .info-box{
    border:2px solid #cfd8dc;
    border-radius:7px;
    padding:3px 4px;
    text-align:center;
    font-size:10px;
  }
  .info-box span{
    display:block;
    background:#0a3b40;
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
    border:2px solid #cfd8dc;
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
    border-bottom:1px dashed #cfd8dc;
    padding-bottom:4px;
    margin-bottom:6px;
    color:#0a3b40;
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
  
  /* ===== الصور مع الإطار ===== */
  .images-section {
    margin-top: 12px;
    border: 2px solid #cfd8dc;
    border-radius: 10px;
    padding: 10px;
    background: #f9fbfb;
  }
  
  .images-title {
    text-align: center;
    font-weight: 700;
    font-size: 12px;
    color: #0a3b40;
    margin-bottom: 8px;
    padding-bottom: 4px;
    border-bottom: 1px dashed #cfd8dc;
  }
  
  .images-grid{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:10px;
  }
  
  .image-container {
    border: 1px solid #ddd;
    border-radius: 8px;
    padding: 6px;
    background: white;
    text-align: center;
  }
  
  .images-grid img{
    width:100%;
    height:120px;
    object-fit:cover;
    border-radius:6px;
    display: block;
  }
  
  .image-caption {
    font-size: 9px;
    color: #666;
    margin-top: 4px;
    padding-top: 3px;
    border-top: 1px dotted #ddd;
  }
  
  /* ===== التوقيعات ===== */
  .signatures{
    margin-top:22px;
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:40px;
    border-top:2px solid #cfd8dc;
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

/* ===== تحسينات الواجهة ===== */
.hijri-info {
  background: #f0f7f5;
  border-radius: 8px;
  padding: 10px;
  margin-top: 10px;
  border-right: 3px solid var(--accent);
  font-size: 14px;
}

.hijri-info strong {
  color: var(--primary);
}

</style>
</head>

<body>

<div class="tool">
<h2>أداة إعداد التقارير التعليمية</h2>

<div class="form-section">
  <h3>المعلومات الأساسية</h3>
  <div class="input-group">
    <div>
      <label>إدارة التعليم</label>
      <select id="eduSelect" onchange="sync('edu',this.value)">
        <option value="">اختر إدارة التعليم</option>
        <option value="الإدارة العامة للتعليم بمنطقة مكة المكرمة">الإدارة العامة للتعليم بمنطقة مكة المكرمة</option>
        <option value="الإدارة العامة للتعليم بمنطقة الرياض">الإدارة العامة للتعليم بمنطقة الرياض</option>
        <option value="الإدارة العامة للتعليم بمنطقة المدينة المنورة">الإدارة العامة للتعليم بمنطقة المدينة المنورة</option>
        <option value="الإدارة العامة للتعليم بالمنطقة الشرقية">الإدارة العامة للتعليم بالمنطقة الشرقية</option>
        <option value="الإدارة العامة للتعليم بمنطقة القصيم">الإدارة العامة للتعليم بمنطقة القصيم</option>
        <option value="الإدارة العامة للتعليم بمنطقة عسير">الإدارة العامة للتعليم بمنطقة عسير</option>
        <option value="الإدارة العامة للتعليم بمنطقة تبوك">الإدارة العامة للتعليم بمنطقة تبوك</option>
        <option value="الإدارة العامة للتعليم بمنطقة حائل">الإدارة العامة للتعليم بمنطقة حائل</option>
        <option value="الإدارة العامة للتعليم بمنطقة الحدود الشمالية">الإدارة العامة للتعليم بمنطقة الحدود الشمالية</option>
        <option value="الإدارة العامة للتعليم بمنطقة جازان">الإدارة العامة للتعليم بمنطقة جازان</option>
        <option value="الإدارة العامة للتعليم بمنطقة نجران">الإدارة العامة للتعليم بمنطقة نجران</option>
        <option value="الإدارة العامة للتعليم بمنطقة الباحة">الإدارة العامة للتعليم بمنطقة الباحة</option>
        <option value="الإدارة العامة للتعليم بمنطقة الجوف">الإدارة العامة للتعليم بمنطقة الجوف</option>
        <option value="الإدارة العامة للتعليم بمحافظة الأحساء">الإدارة العامة للتعليم بمحافظة الأحساء</option>
        <option value="الإدارة العامة للتعليم بمحافظة الطائف">الإدارة العامة للتعليم بمحافظة الطائف</option>
        <option value="الإدارة العامة للتعليم بمحافظة جدة">الإدارة العامة للتعليم بمحافظة جدة</option>
      </select>
    </div>
    <div>
      <label>اسم المدرسة</label>
      <input oninput="sync('school',this.value)">
    </div>
  </div>
</div>

<div class="form-section">
  <h3>تفاصيل التقرير</h3>
  <div class="input-group">
    <div>
      <label>البند التربوي</label>
      <select id="axisSelect" onchange="updateReportTitles()">
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
    <div>
      <label>عنوان التقرير</label>
      <select id="titleSelect" onchange="sync('title',this.value); loadAutoTexts(this.value)">
        <option value="">اختر عنوان التقرير</option>
      </select>
    </div>
  </div>
  
  <div class="input-group">
    <div class="date-group">
      <div class="date-input">
        <label>تاريخ التنفيذ (ميلادي)</label>
        <input type="date" id="gregorianDate" oninput="updateHijriDate(); sync('date', getFormattedDate())">
      </div>
      <div class="date-input">
        <label>تاريخ التنفيذ (هجري)</label>
        <input type="text" id="hijriDate" placeholder="سيتم التحويل تلقائياً" oninput="sync('hijriDate', this.value)">
      </div>
      <button type="button" class="date-convert-btn" onclick="convertToHijri()">تحويل التاريخ إلى هجري</button>
    </div>
    <div>
      <label>المستهدفون</label>
      <input oninput="sync('target',this.value)">
    </div>
  </div>
  
  <div class="input-group">
    <div>
      <label>عدد المستفيدين</label>
      <input type="number" oninput="sync('count',this.value)">
    </div>
    <div>
      <label>اسم المعلم</label>
      <input oninput="sync('teacher',this.value)">
    </div>
  </div>
  
  <div>
    <label>اسم مدير المدرسة</label>
    <input oninput="sync('principal',this.value)">
  </div>
  
  <div class="hijri-info">
    <strong>ملاحظة:</strong> أدخل التاريخ الميلادي وسيتم تحويله تلقائياً إلى هجري، أو أدخل التاريخ الهجري يدوياً.
  </div>
</div>

<div class="form-section">
  <h3>النصوص التلقائية</h3>
  <div id="autoTextsContainer">
    <p>اختر عنوان التقرير أولاً لعرض النصوص التلقائية المناسبة</p>
  </div>
</div>

<div class="form-section">
  <h3>محتوى التقرير</h3>
  
  <div>
    <label>وصف مختصر (15 كلمة)</label>
    <textarea id="desc1Input" oninput="limitWords(this,'desc1','c1')"></textarea>
    <div class="counter" id="c1">0 / 15 كلمة</div>
  </div>
  
  <div>
    <label>إجراءات التنفيذ (15 كلمة)</label>
    <textarea id="desc2Input" oninput="limitWords(this,'desc2','c2')"></textarea>
    <div class="counter" id="c2">0 / 15 كلمة</div>
  </div>
  
  <div>
    <label>النتائج (15 كلمة)</label>
    <textarea id="desc3Input" oninput="limitWords(this,'desc3','c3')"></textarea>
    <div class="counter" id="c3">0 / 15 كلمة</div>
  </div>
  
  <div>
    <label>التوصيات (15 كلمة)</label>
    <textarea id="desc4Input" oninput="limitWords(this,'desc4','c4')"></textarea>
    <div class="counter" id="c4">0 / 15 كلمة</div>
  </div>
</div>

<div class="form-section">
  <h3>المرفقات</h3>
  <label>إرفاق الصور (صورتان كحد أقصى)</label>
  <div class="file-input-container">
    <input type="file" id="imagesInput" multiple accept="image/*">
    <div class="file-input-label">اختر الصور (حد أقصى صورتان)</div>
  </div>
  <div class="counter">يسمح بصورتين فقط</div>
</div>

<div class="button-group">
  <button class="export-btn" onclick="window.print()">
    <span>📄</span> تصدير PDF
  </button>
  <button class="reset-btn" onclick="resetForm()">
    <span>🗑️</span> مسح جميع الخانات
  </button>
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
    <div class="info-box"><span>التاريخ الميلادي</span><div id="date"></div></div>
    <div class="info-box"><span>التاريخ الهجري</span><div id="hijriDate"></div></div>
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

  <div class="images-section">
    <div class="images-title">شواهد الصور</div>
    <div class="images-grid" id="imagesContainer"></div>
  </div>

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
// بيانات التقارير
const reportData = {
  "تحسين نواتج التعلم والتحصيل الدراسي": [
    "تقرير نشاط إثرائي","تقرير تنفيذ اختبار تحسن","تقرير تحليل النتائج","تقرير مقارنة السلاسل الزمنية",
    "تقرير تصنيف الطلاب","تقرير تحفيز الطلاب","تقرير دراسة حالة","تقرير البحث الإجرائي",
    "تقرير نقل أثر التدريب","تقرير التدريب على الاختبارات المعيارية"
  ],
  "الدعم العلاجي والتدخلات التعليمية": [
    "تقرير خطة علاجية","تقرير سجل الخطط العلاجية","تقرير رعاية الطلاب المتأخرين دراسيًا",
    "تقرير كشف المتابعة","تقرير إشعار ولي الأمر عن مستوى ابنه"
  ],
  "التدريس والتعلم داخل الصف": [
    "تقرير أنشطة صفية","تقرير درس تم تنفيذه","تقرير تنفيذ درس تطبيقي","تقرير تعليم تعاوني بين الطلاب",
    "تقرير الفصول المقلوبة","تقرير توزيع وقت الحصة","تقرير تطوير البيئة الصفية","تقرير حصة النشاط"
  ],
  "التخطيط والتنظيم التعليمي": [
    "تقرير خطة أسبوعية","تقرير تفعيل الخطة الأسبوعية","تقرير توزيع المنهج","تقرير تفعيل حصص النشاط"
  ],
  "الأنشطة المدرسية واللاصفية": [
    "تقرير تنفيذ إذاعة مدرسية","تقرير الاحتفال باليوم الوطني","تقرير مبادرة تطوعية","تقرير المعلم الصغير"
  ],
  "التقويم والمتابعة والتوثيق": [
    "تقرير سجل الدرجات الإلكتروني","تقرير سجل التغذية الراجعة من الطلاب","تقرير سجل رعاية الموهوبين",
    "تقرير سجل التواصل مع أولياء الأمور","تقارير الجرد (للمختبرات وغرف المصادر)"
  ],
  "التواصل والشراكة مع الأسرة": [
    "تقرير التواصل مع ولي الأمر","تقرير حضور اجتماع أولياء الأمور",
    "تقرير إشعار ولي الأمر","تقرير سجل التواصل مع أولياء الأمور"
  ],
  "التطوير المهني وبناء القدرات": [
    "تقرير حضور دورات وورش تدريبية","تقرير الورش التدريبية التي قدمتها",
    "تقرير تبادل الزيارات","تقرير مجتمعات التعلم","تقرير المجتمعات المهنية"
  ],
  "التميز والجودة": [
    "تقرير عضوية لجنة التميز والجودة","تقرير متابعة مؤشرات الأداء","تقرير توثيق الممارسات المتميزة",
    "تقرير متابعة خطط التحسين","تقرير قياس رضا المستفيدين","تقرير مبادرات التميز"
  ],
  "التحول الرقمي والابتكار": [
    "تقرير تفعيل المنصات التعليمية","تقرير المحتوى الرقمي المنتج",
    "تقرير الاختبارات الذكية","تقرير توظيف الذكاء الاصطناعي","تقرير الوسائل التعليمية المبتكرة"
  ],
  "السلوك والإرشاد التربوي": [
    "تقرير تعزيز السلوك الإيجابي","تقرير حل مشكلة تربوية",
    "تقرير متابعة حالات سلوكية","تقرير جلسات إرشادية"
  ],
  "المبادرات والشراكات المجتمعية": [
    "تقرير مبادرة تعليمية","تقرير مبادرة تطوعية","تقرير شراكة مجتمعية تعليمية"
  ],
  "السلامة والصحة المدرسية": [
    "تقرير تنفيذ فرضية إخلاء","تقرير التوعية الصحية","تقرير إجراءات السلامة المدرسية"
  ]
};

// النصوص التلقائية لكل نوع تقرير
const autoTexts = {
  "تقرير نشاط إثرائي": {
    desc: [
      "نشاط إثرائي لتعزيز مهارات التفكير العليا لدى الطلاب المتفوقين من خلال أنشطة عملية وتفاعلية تنمي الإبداع.",
      "نشاط إثرائي مصمم لتطوير القدرات العلمية للطلاب المتميزين في مادة العلوم عبر تجارب عملية مبتكرة.",
      "برنامج إثرائي يهدف إلى تعميق فهم الطلاب في الرياضيات من خلال مسائل تحدي ونشاطات ذهنية محفزة.",
      "نشاط إثرائي في اللغة العربية يعزز مهارات التعبير الكتابي والإلقاء لدى الطلاب الموهوبين لغوياً.",
      "فعالية إثرائية تركز على تنمية المهارات القيادية والعمل الجماعي لدى الطلاب المتفوقين في الأنشطة الطلابية."
    ],
    procedures: [
      "تحديد الفئة المستهدفة من الطلاب المتفوقين وتصميم أنشطة تناسب مستواهم وقدراتهم التعليمية المتميزة.",
      "إعداد المواد التعليمية والأدوات اللازمة وتجهيز القاعة المناسبة لتنفيذ النشاط الإثرائي المخطط.",
      "تنفيذ الأنشطة العملية والتجارب التفاعلية تحت إشراف مباشر مع متابعة أداء كل طالب وتقييمه.",
      "تقسيم الطلاب إلى مجموعات عمل وتعيين مهام تتناسب مع قدرات كل طالب لتعزيز التعاون بينهم.",
      "تسجيل ملاحظات حول أداء الطلاب وتقديم تغذية راجعة فورية لتحسين مستوى تنفيذ النشاط."
    ],
    results: [
      "تحسن ملحوظ في مهارات التفكير النقدي والإبداعي لدى الطلاب المشاركين في النشاط الإثرائي المنفذ.",
      "زيادة دافعية الطلاب للتعلم وارتفاع مستوى مشاركتهم في الحصص الدراسية والأنشطة المدرسية.",
      "تطوير مهارات حل المشكلات والعمل الجماعي لدى الطلاب من خلال المهام والتحديات المقدمة لهم.",
      "ارتفاع مستوى الثقة بالنفس والتعبير عن الرأي لدى الطلاب المشاركين في البرنامج الإثرائي.",
      "تحقيق الأهداف التعليمية المخطط لها وملاحظة تقدم واضح في أداء الطلاب الأكاديمي والسلوكي."
    ],
    recommendations: [
      "توسيع نطاق الأنشطة الإثرائية لتشمل فئات أكثر من الطلاب ذوي المستويات والقدرات المختلفة.",
      "توفير موارد إضافية وأدوات تعليمية متطورة لتعزيز فعالية البرامج الإثرائية المستقبلية.",
      "تدريب المعلمين على أساليب تصميم وتنفيذ الأنشطة الإثرائية التي تلبي احتياجات الطلاب المتفوقين.",
      "إشراك أولياء الأمور في متابعة تقدم أبنائهم وتقديم الدعم المعنوي والمادي للأنشطة الإثرائية.",
      "توثيق نجاحات البرنامج ونشر النتائج الإيجابية لتحفيز تكرار التجربة في فصول ومدارس أخرى."
    ]
  },
  "تقرير خطة علاجية": {
    desc: [
      "خطة علاجية ممنهجة تستهدف الطلاب المتأخرين دراسياً في مادة الرياضيات من خلال أنشطة داعمة ومتابعة فردية.",
      "برنامج علاجي مصمم لمعالجة ضعف الطلاب في مهارات القراءة والكتابة عبر جلسات علاجية مكثفة ومنتظمة.",
      "خطة تدخل تعليمي لتحسين مستوى الطلاب في مادة العلوم من خلال شرح مبسط وتدريبات علاجية مستهدفة.",
      "برنامج علاجي يركز على تحسين مهارات الاستماع والتحدث في اللغة الإنجليزية للطلاب الضعاف في المادة.",
      "خطة علاج شاملة تستهدف الطلاب المتأخرين دراسياً عبر جلسات تقوية واختبارات تقييمية دورية لمتابعة التقدم."
    ],
    procedures: [
      "تشخيص نقاط الضعف لدى كل طالب من خلال تحليل نتائج الاختبارات والملاحظات الصفية اليومية.",
      "تصميم أنشطة علاجية فردية وجماعية تناسب مستوى كل طالب وتستهدف نقاط الضعف المحددة.",
      "تنفيذ جلسات التقوية والعلاج في أوقات مناسبة مع توفير المواد التعليمية المساندة اللازمة.",
      "متابعة تقدم كل طالب أسبوعياً وتسجيل الملاحظات حول التحسن في مستوى الفهم والأداء الأكاديمي.",
      "تعديل الخطة العلاجية بناءً على نتائج المتابعة وتقدم الطلاب لضمان فعالية البرنامج العلاجي."
    ],
    results: [
      "تحسن واضح في أداء الطلاب المستهدفين وارتفاع درجاتهم في الاختبارات التشخيصية والنهائية.",
      "زيادة ثقة الطلاب بأنفسهم وتحسن اتجاهاتهم نحو المادة الدراسية بعد المشاركة في البرنامج العلاجي.",
      "انخفاض نسبة الطلاب المتأخرين دراسياً وتراجع عدد حالات الضعف الشديد في المادة المستهدفة.",
      "تحسن مهارات التعلم الأساسية لدى الطلاب وازدياد قدرتهم على متابعة الدروس بشكل أفضل.",
      "تفاعل إيجابي من أولياء الأمور وملاحظتهم لتطور أداء أبنائهم بعد تطبيق الخطة العلاجية."
    ],
    recommendations: [
      "استمرار تنفيذ البرامج العلاجية مع تحديثها باستمرار لمواكبة احتياجات الطلاب المتغيرة.",
      "تخصيص موارد كافية للبرامج العلاجية وتوفير الأدوات التعليمية المساندة الضرورية لنجاحها.",
      "تدريب المعلمين على أحدث أساليب التشخيص والعلاج التعليمي لتحسين جودة البرامج المقدمة.",
      "تعزيز التعاون مع أولياء الأمور لمتابعة تقدم الطلاب خارج أوقات الدراسة ودعم استمرارية التحسن.",
      "توثيق نجاحات الخطط العلاجية ونشر أفضل الممارسات بين المعلمين لتعميم الفائدة على جميع الطلاب."
    ]
  },
  "تقرير أنشطة صفية": {
    desc: [
      "أنشطة صفية تفاعلية متنوعة تهدف إلى تنمية المهارات التعليمية وتحفيز المشاركة الإيجابية للطلاب داخل الفصل.",
      "مجموعة من الأنشطة الصفية المصممة لتعزيز فهم الطلاب لمف الدرس وجعل عملية التعلم أكثر متعة وفعالية.",
      "أنشطة تعليمية داخل الصف تجمع بين التعلم النظري والتطبيق العملي لترسيخ المعلومات وتحسين الاستيعاب.",
      "فعاليات صفية تعاونية تشجع العمل الجماعي وتنمية مهارات التواصل والتفكير النقدي لدى الطلاب.",
      "برنامج أنشطة صفية متكامل يدمج التقنية الحديثة لجعل البيئة التعليمية أكثر جاذبية وتحفيزاً للطلاب."
    ],
    procedures: [
      "تخطيط الأنشطة الصفية مسبقاً وربطها بأهداف الدرس التعليمية والمخرجات المتوقعة من الطلاب.",
      "تجهيز المواد والأدوات اللازمة للأنشطة وتنظيم بيئة الصف بما يناسب طبيعة النشاط المخطط له.",
      "تقسيم الطلاب إلى مجموعات عمل وتعليمات واضحة لكل مجموعة مع تحديد الأدوار والمهام المطلوبة.",
      "تنفيذ الأنشطة تحت إشراف مباشر مع توجيه الطلاب وتقديم الدعم اللازم عند الحاجة أثناء التنفيذ.",
      "تقييم نتائج الأنشطة ومناقشة مخرجاتها مع الطلاب لتعزيز الفائدة التعليمية من التجربة."
    ],
    results: [
      "زيادة ملحوظة في تفاعل الطلاب ومشاركتهم الفعالة خلال الحصة الدراسية مقارنة بالأساليب التقليدية.",
      "تحسن في استيعاب المفاهيم التعليمية وترسيخ المعلومات نتيجة دمج الجانب النظري مع التطبيق العملي.",
      "تنمية مهارات العمل الجماعي والتوcommunicate الفعال بين الطلاب من خلال الأنشطة التعاونية المطبقة.",
      "ارتفاع مستوى دافعية الطلاب للتعلم وتحسن اتجاهاتهم نحو المادة الدراسية والحصص الصفية.",
      "تطوير مهارات التفكير الإبداعي وحل المشكلات لدى الطلاب عبر الأنشطة التحدية المصممة لهم."
    ],
    recommendations: [
      "استمرار دمج الأنشطة التفاعلية في الخطط الدراسية وتنويعها لتناسب مختلف أنماط التعلم لدى الطلاب.",
      "تخصيص وقت كافي داخل الجدول الدراسي للأنشطة الصفية مع مراعاة التوازن بين النظرية والتطبيق.",
      "تدريب المعلمين على تصميم وتنفيذ الأنشطة الصفية الفعالة التي تحقق الأهداف التعليمية المطلوبة.",
      "توفير الموارد والأدوات اللازمة لدعم الأنشطة الصفية المبتكرة وضمان جودة تنفيذها.",
      "توثيق الأنشطة الناجحة ونشرها بين المعلمين لتبادل الخبرات وتعظيم الفائدة التعليمية للطلاب."
    ]
  }
};

// وظائف عامة
function sync(id, val) {
  document.getElementById(id).textContent = val;
}

function limitWords(el, target, counterId) {
  let words = el.value.trim().replace(/\s+/g, ' ').split(' ').filter(w => w);
  if (words.length > 15) {
    words = words.slice(0, 15);
    el.value = words.join(' ');
  }
  const c = document.getElementById(counterId);
  c.textContent = `${words.length} / 15 كلمة`;
  c.classList.toggle('limit', words.length === 15);
  document.getElementById(target).textContent = el.value;
}

// تحديث عناوين التقارير بناءً على البند التربوي
function updateReportTitles() {
  const axisSelect = document.getElementById('axisSelect');
  const titleSelect = document.getElementById('titleSelect');
  const selectedAxis = axisSelect.value;
  
  // مزامنة قيمة البند التربوي
  sync('axis', selectedAxis);
  
  // تحديث قائمة عناوين التقارير
  titleSelect.innerHTML = '<option value="">اختر عنوان التقرير</option>';
  
  if (selectedAxis && reportData[selectedAxis]) {
    reportData[selectedAxis].forEach(title => {
      const option = document.createElement('option');
      option.value = title;
      option.textContent = title;
      titleSelect.appendChild(option);
    });
  }
  
  // إفراغ النصوص التلقائية عند تغيير البند
  document.getElementById('autoTextsContainer').innerHTML = '<p>اختر عنوان التقرير أولاً لعرض النصوص التلقائية المناسبة</p>';
}

// تحميل النصوص التلقائية عند اختيار عنوان التقرير
function loadAutoTexts(reportTitle) {
  const container = document.getElementById('autoTextsContainer');
  
  if (!reportTitle || !autoTexts[reportTitle]) {
    container.innerHTML = '<p>لا توجد نصوص تلقائية متاحة لهذا التقرير</p>';
    return;
  }
  
  const texts = autoTexts[reportTitle];
  let html = `
    <div class="auto-texts">
      <h4>نصوص تلقائية للوصف المختصر</h4>
  `;
  
  texts.desc.forEach((text, index) => {
    html += `<button class="auto-text-btn" onclick="applyAutoText('desc1Input', 'desc1', 'c1', \`${text}\`)">النص ${index+1}</button>`;
  });
  
  html += `
      <h4>نصوص تلقائية لإجراءات التنفيذ</h4>
  `;
  
  texts.procedures.forEach((text, index) => {
    html += `<button class="auto-text-btn" onclick="applyAutoText('desc2Input', 'desc2', 'c2', \`${text}\`)">النص ${index+1}</button>`;
  });
  
  html += `
      <h4>نصوص تلقائية للنتائج</h4>
  `;
  
  texts.results.forEach((text, index) => {
    html += `<button class="auto-text-btn" onclick="applyAutoText('desc3Input', 'desc3', 'c3', \`${text}\`)">النص ${index+1}</button>`;
  });
  
  html += `
      <h4>نصوص تلقائية للتوصيات</h4>
  `;
  
  texts.recommendations.forEach((text, index) => {
    html += `<button class="auto-text-btn" onclick="applyAutoText('desc4Input', 'desc4', 'c4', \`${text}\`)">النص ${index+1}</button>`;
  });
  
  html += `</div>`;
  container.innerHTML = html;
}

// تطبيق النص التلقائي
function applyAutoText(inputId, targetId, counterId, text) {
  const input = document.getElementById(inputId);
  input.value = text;
  limitWords(input, targetId, counterId);
}

// تحويل التاريخ الميلادي إلى هجري
function convertToHijri() {
  const gregorianInput = document.getElementById('gregorianDate');
  const hijriInput = document.getElementById('hijriDate');
  
  if (!gregorianInput.value) {
    alert('الرجاء إدخال تاريخ ميلادي أولاً');
    return;
  }
  
  const date = new Date(gregorianInput.value);
  const year = date.getFullYear();
  const month = date.getMonth() + 1;
  const day = date.getDate();
  
  // استخدام مكتبة umalqura للتحويل
  try {
    const hijriDate = UmAlQura.GregorianToHijri(year, month, day);
    const hijriDateStr = `${hijriDate.hd} ${getHijriMonthName(hijriDate.hm)} ${hijriDate.hy} هـ`;
    hijriInput.value = hijriDateStr;
    sync('hijriDate', hijriDateStr);
  } catch (error) {
    // في حالة فشل التحويل، نستخدم طريقة تقريبية
    const hijriYear = Math.round((year - 622) * (33/32));
    const hijriMonth = getHijriMonthName(month);
    const hijriDay = day;
    const hijriDateStr = `${hijriDay} ${hijriMonth} ${hijriYear} هـ`;
    hijriInput.value = hijriDateStr;
    sync('hijriDate', hijriDateStr);
  }
}

// تحديث التاريخ الهجري تلقائياً عند تغيير الميلادي
function updateHijriDate() {
  const gregorianInput = document.getElementById('gregorianDate');
  if (gregorianInput.value) {
    convertToHijri();
  }
}

// الحصول على اسم الشهر الهجري
function getHijriMonthName(month) {
  const hijriMonths = [
    'محرم', 'صفر', 'ربيع الأول', 'ربيع الثاني', 
    'جمادى الأولى', 'جمادى الآخرة', 'رجب', 'شعبان', 
    'رمضان', 'شوال', 'ذو القعدة', 'ذو الحجة'
  ];
  return hijriMonths[month - 1] || '';
}

// تنسيق التاريخ لعرضه
function getFormattedDate() {
  const gregorianInput = document.getElementById('gregorianDate');
  if (!gregorianInput.value) return '';
  
  const date = new Date(gregorianInput.value);
  const options = { year: 'numeric', month: 'long', day: 'numeric' };
  return date.toLocaleDateString('ar-SA', options);
}

// معالجة رفع الصور
const imagesInput = document.getElementById('imagesInput');
const imagesContainer = document.getElementById('imagesContainer');

imagesInput.addEventListener('change', e => {
  imagesContainer.innerHTML = '';
  const files = [...e.target.files];
  if (files.length > 2) {
    alert('يسمح بإرفاق صورتين فقط');
    imagesInput.value = '';
    return;
  }
  
  files.forEach((f, index) => {
    const r = new FileReader();
    r.onload = ev => {
      const imageContainer = document.createElement('div');
      imageContainer.className = 'image-container';
      
      const img = document.createElement('img');
      img.src = ev.target.result;
      
      const caption = document.createElement('div');
      caption.className = 'image-caption';
      caption.textContent = `صورة ${index + 1}`;
      
      imageContainer.appendChild(img);
      imageContainer.appendChild(caption);
      imagesContainer.appendChild(imageContainer);
    };
    r.readAsDataURL(f);
  });
});

// إعادة تعيين النموذج
function resetForm() {
  if (!confirm('هل تريد مسح جميع الخانات؟')) return;
  
  // مسح حقول الإدخال
  document.querySelectorAll('input, textarea, select').forEach(e => {
    if (e.type !== 'button' && e.type !== 'submit') {
      e.value = '';
    }
  });
  
  // مسح محتوى التقرير
  document.querySelectorAll('[id]').forEach(e => {
    if (e.id && !e.classList.contains('tool') && !e.classList.contains('report')) {
      e.textContent = '';
    }
  });
  
  // إعادة تعيين القوائم المنسدلة
  document.getElementById('titleSelect').innerHTML = '<option value="">اختر عنوان التقرير</option>';
  document.getElementById('autoTextsContainer').innerHTML = '<p>اختر عنوان التقرير أولاً لعرض النصوص التلقائية المناسبة</p>';
  
  // مسح الصور
  imagesContainer.innerHTML = '';
  imagesInput.value = '';
  
  // إعادة تعيين العدادات
  ['c1', 'c2', 'c3', 'c4'].forEach(id => {
    document.getElementById(id).textContent = '0 / 15 كلمة';
    document.getElementById(id).classList.remove('limit');
  });
}

// تهيئة التاريخ الحالي
window.addEventListener('DOMContentLoaded', () => {
  const today = new Date();
  const formattedDate = today.toISOString().split('T')[0];
  document.getElementById('gregorianDate').value = formattedDate;
  updateHijriDate();
});
</script>
</body>
</html>