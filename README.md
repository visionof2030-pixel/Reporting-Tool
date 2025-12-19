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

/* ===== الأداة المحسنة ===== */
.tool-container {
  max-width: 1000px;
  margin: 0 auto 40px;
}

.tool-header {
  text-align: center;
  margin-bottom: 30px;
  padding: 20px;
  background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
  color: white;
  border-radius: var(--radius);
  box-shadow: var(--shadow);
}

.tool-header h1 {
  margin: 0 0 10px;
  font-size: 28px;
}

.tool-header p {
  margin: 0;
  opacity: 0.9;
  font-size: 16px;
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
  <div class="tool-header">
    <h1>أداة إعداد التقارير المدرسية</h1>
    <p>أداة متكاملة لإنشاء تقارير احترافية بسهولة وسرعة</p>
  </div>

  <div class="tool">
    <div class="form-grid">
      <div class="form-group">
        <label for="edu">إدارة التعليم</label>
        <select id="edu" oninput="sync('edu',this.value)">
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

      <div class="form-group">
        <label for="school">اسم المدرسة</label>
        <input id="school" type="text" placeholder="أدخل اسم المدرسة" oninput="sync('school',this.value)">
      </div>

      <div class="form-group">
        <label for="axis">البند التربوي</label>
        <input id="axis" type="text" placeholder="أدخل البند التربوي" oninput="sync('axis',this.value)">
      </div>

      <div class="form-group">
        <label for="title">عنوان التقرير</label>
        <input id="title" type="text" placeholder="أدخل عنوان التقرير" oninput="sync('title',this.value)">
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

    <div class="form-group">
      <label>وصف مختصر (15 كلمة)</label>
      <textarea id="desc1Input" placeholder="أدخل وصف مختصر للتقرير (15 كلمة كحد أقصى)" oninput="limitWords(this,'desc1','c1')"></textarea>
      <div class="counter-container">
        <div class="counter" id="c1">0 / 15 كلمة</div>
        <div class="counter">الكلمات المتبقية: <span id="c1-remaining">15</span></div>
      </div>
    </div>

    <div class="form-group">
      <label>إجراءات التنفيذ (15 كلمة)</label>
      <textarea id="desc2Input" placeholder="أدخل إجراءات التنفيذ (15 كلمة كحد أقصى)" oninput="limitWords(this,'desc2','c2')"></textarea>
      <div class="counter-container">
        <div class="counter" id="c2">0 / 15 كلمة</div>
        <div class="counter">الكلمات المتبقية: <span id="c2-remaining">15</span></div>
      </div>
    </div>

    <div class="form-group">
      <label>النتائج (15 كلمة)</label>
      <textarea id="desc3Input" placeholder="أدخل النتائج المتحققة (15 كلمة كحد أقصى)" oninput="limitWords(this,'desc3','c3')"></textarea>
      <div class="counter-container">
        <div class="counter" id="c3">0 / 15 كلمة</div>
        <div class="counter">الكلمات المتبقية: <span id="c3-remaining">15</span></div>
      </div>
    </div>

    <div class="form-group">
      <label>التوصيات (15 كلمة)</label>
      <textarea id="desc4Input" placeholder="أدخل التوصيات المقترحة (15 كلمة كحد أقصى)" oninput="limitWords(this,'desc4','c4')"></textarea>
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
function sync(id,val){
  document.getElementById(id).textContent = val;
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
  const requiredFields = ['edu', 'school', 'axis', 'title', 'date'];
  let missingFields = [];
  
  requiredFields.forEach(fieldId => {
    const field = document.getElementById(fieldId);
    if (!field.value && fieldId !== 'edu') {
      missingFields.push(field.previousElementSibling.textContent);
    }
    
    // معالجة خاصية للقائمة المنسدلة
    if (fieldId === 'edu' && field.tagName === 'SELECT' && !field.value) {
      missingFields.push('إدارة التعليم');
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
  
  // إعادة التركيز على أول حقل
  document.getElementById('edu').focus();
}
</script>

</body>
</html>
