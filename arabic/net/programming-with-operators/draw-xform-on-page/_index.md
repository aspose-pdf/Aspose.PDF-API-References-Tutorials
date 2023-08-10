---
title: ارسم XForm على الصفحة
linktitle: ارسم XForm على الصفحة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لرسم نموذج XForm على صفحة PDF باستخدام Aspose.PDF for .NET. إضافة ووضع النموذج على الصفحة.
type: docs
weight: 10
url: /ar/net/programming-with-operators/draw-xform-on-page/
---
في هذا البرنامج التعليمي ، سنزودك بدليل خطوة بخطوة حول كيفية رسم XForm على صفحة باستخدام Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تسمح لك بإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام عوامل التشغيل التي يوفرها Aspose.PDF ، يمكنك إضافة نموذج XForm ووضعه في صفحة PDF موجودة.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من توفر المتطلبات الأساسية التالية:

1. Visual Studio مثبت مع .NET framework.
2. مكتبة Aspose.PDF لـ .NET.

## الخطوة 1: إعداد المشروع

للبدء ، أنشئ مشروعًا جديدًا في Visual Studio وأضف مرجعًا إلى Aspose.PDF لمكتبة .NET. يمكنك تنزيل المكتبة من موقع Aspose الرسمي وتثبيتها على جهازك.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

في ملف كود C # الخاص بك ، قم باستيراد مساحات الأسماء المطلوبة للوصول إلى الفئات والطرق التي يوفرها Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## الخطوة 3: ضبط مسارات الملفات

حدد مسارات الملفات لصورة الخلفية وملف إدخال PDF وملف PDF الناتج:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

تأكد من تحديد مسارات الملفات الفعلية على جهازك.

## الخطوة 4: تحميل ملف PDF المدخل

استخدم الكود التالي لتحميل ملف PDF المدخل:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// يستخدم الكود التالي عوامل تشغيل GSave / GRestore
// يستخدم الكود عامل التشغيل ContatenateMatrix لوضع XForm
// يستخدم الكود عامل التشغيل Do لرسم XForm على الصفحة
// يلتف مشغلو GSave / GRestore المحتوى الموجود
// يتم ذلك للحصول على حالة الرسومات الأولية في نهاية المحتوى الحالي
// وإلا فقد تكون هناك تحويلات غير مرغوب فيها في نهاية سلسلة المشغلين الحاليين
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// أضف عامل تشغيل GSave لإعادة تعيين حالة الرسومات بشكل صحيح بعد الأوامر الجديدة
pageContents. Add(new GSave());

// قم بإنشاء ملف XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// اضبط عرض الصورة وارتفاعها
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// تحميل الصورة في دفق
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// أضف الصورة إلى مجموعة صور مورد XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// باستخدام عامل التشغيل Do: يرسم هذا العامل الصورة
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//ضع XForm عند الإحداثيات x = 100 و y = 500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// ارسم XForm باستخدام عامل التشغيل Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// ضع XForm عند الإحداثيات x = 100 و y = 300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// ارسم XForm باستخدام عامل التشغيل Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// استعادة حالة الرسومات باستخدام GRestore بعد GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

تأكد من تحديد مسارات الملفات الفعلية وضبط رقم الصفحة ومواضع XForm حسب الحاجة.

### نموذج التعليمات البرمجية المصدر لـ Draw XForm On Page باستخدام Aspose.PDF for .NET
 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// العينة توضح
	// استخدام مشغلي GSave / GRestore
	// استخدام عامل ContatenateMatrix لوضع xForm
	// استخدم عامل التشغيل لرسم xForm على الصفحة
	// لف المحتويات الموجودة بزوج مشغلي GSave / GRestore
	// هذا للحصول على حالة الرسومات الأولية في والمحتويات الموجودة
	// وإلا فقد تظل هناك بعض التحولات غير المرغوب فيها في نهاية سلسلة المشغلين الحالية
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// أضف عامل حفظ حالة الرسومات لمسح حالة الرسومات بشكل صحيح بعد أوامر جديدة
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// قم بإنشاء xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// تحديد عرض الصورة والارتفاع
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// تحميل الصورة في تيار
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//أضف صورة إلى مجموعة الصور لموارد XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// باستخدام عامل التشغيل: يقوم هذا العامل برسم الصورة
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// ضع النموذج على إحداثيات x = 100 y = 500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// ارسم النموذج باستخدام عامل التشغيل Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// ضع النموذج على إحداثيات x = 100 y = 300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// ارسم النموذج باستخدام عامل التشغيل Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// استعادة حالة grahics مع GRestore بعد GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية رسم نموذج XForm على صفحة PDF باستخدام Aspose.PDF for .NET. باتباع الخطوات الموضحة ، ستتمكن من إضافة نموذج XForm ووضعه على صفحة موجودة ، مما يمنحك مزيدًا من المرونة لمستندات PDF الخاصة بك.

### الأسئلة الشائعة لرسم XForm على الصفحة

#### س: ما هو XForm في Aspose.PDF؟

ج: XForm هو كائن رسومي يمكن إعادة استخدامه في مستند PDF. يتيح لك تحديد ورسم رسومات أو صور أو نصوص معقدة يمكن إعادة استخدامها عدة مرات على صفحات مختلفة.

#### س: كيف يمكنني استيراد مساحات الأسماء الضرورية لـ Aspose.PDF؟

 ج: في ملف كود C # ، استخدم الامتداد`using` توجيه لاستيراد مساحات الأسماء المطلوبة للوصول إلى الفئات والطرق التي يوفرها Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### س: ما هو الغرض من مشغلي GSave و GRestore؟

 ج: إن`GSave` و`GRestore`يتم استخدام العوامل في Aspose.PDF لحفظ واستعادة حالة الرسومات. إنها تساعد على ضمان أن التحويلات والإعدادات المطبقة على قسم واحد من المحتوى لا تؤثر على الأقسام التالية.

#### س: كيف يمكنني تعريف XForm باستخدام Aspose.PDF؟

 ج: لإنشاء XForm ، استخدم ملف`XForm.CreateNewForm` الطريقة وإضافته إلى ملف`Resources.Forms` مجموعة من صفحة معينة. يمكنك بعد ذلك إضافة محتوى إلى XForm's`Contents` ملكية.

#### س: كيف يمكنني رسم صورة داخل XForm؟

 ج: قم بتحميل الصورة في دفق وأضفها إلى ملف`Resources.Images` جمع XForm. استخدم ال`Do` عامل داخل XForm`Contents` لرسم الصورة.

#### س: كيف يمكنني وضع XForm على صفحة PDF؟

 ج: لوضع XForm على الصفحة ، استخدم ملف`ConcatenateMatrix` عامل داخل الصفحة`Contents`. اضبط معلمات المصفوفة لتحديد الترجمة (الموضع) وقياس XForm.

#### س: هل يمكنني رسم عدة XForms على نفس الصفحة؟

 ج: نعم ، يمكنك رسم عدة أشكال XForms على نفس الصفحة عن طريق ضبط ملف`ConcatenateMatrix`معلمات لوضع كل XForm في إحداثيات مختلفة.

#### س: هل يمكنني تعديل محتوى XForm بعد إنشائه؟

 ج: نعم ، يمكنك تعديل محتويات XForm بعد الإنشاء عن طريق إضافة عوامل تشغيل إضافية إليه`Contents` ملكية.

#### س: ماذا يحدث إذا حذفت مشغلي GSave و GRestore؟

ج: قد يؤدي حذف مشغلي GSave و GRestore إلى تطبيق تحويلات أو إعدادات غير مرغوب فيها على المحتوى اللاحق. يساعد استخدامها في الحفاظ على حالة رسومات نظيفة.

#### س: هل يمكنني إعادة استخدام XForms عبر صفحات مختلفة من مستند PDF؟

 ج: نعم ، يمكنك إعادة استخدام XForms على صفحات متعددة عن طريق إضافة نفس XForm إلى ملف`Resources.Forms` مجموعة من الصفحات المختلفة.

#### س: هل هناك حد لعدد XForms التي يمكنني إنشاؤها؟

ج: بينما لا يوجد حد صارم لعدد XForms التي يمكنك إنشاؤها ، ضع في اعتبارك أن عددًا كبيرًا جدًا من XForms قد يؤثر على الأداء واستخدام الذاكرة. استخدمها بحكمة.

#### س: هل يمكنني تدوير XForm أو تطبيق تحويلات أخرى؟

 ج: نعم ، يمكنك استخدام ملف`ConcatenateMatrix`المشغل لتطبيق تحويلات مثل التدوير والقياس والترجمة إلى XForm.
