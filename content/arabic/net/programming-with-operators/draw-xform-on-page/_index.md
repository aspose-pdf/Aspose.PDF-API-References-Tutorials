---
title: رسم XForm على الصفحة
linktitle: رسم XForm على الصفحة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لرسم نموذج XForm على صفحة PDF باستخدام Aspose.PDF لـ .NET. قم بإضافة النموذج ووضعه على الصفحة.
type: docs
weight: 10
url: /ar/net/programming-with-operators/draw-xform-on-page/
---
في هذا البرنامج التعليمي، سنزودك بدليل خطوة بخطوة حول كيفية رسم XForm على صفحة باستخدام Aspose.PDF لـ .NET. Aspose.PDF هي مكتبة قوية تتيح لك إنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام عوامل التشغيل التي يوفرها Aspose.PDF، يمكنك إضافة نموذج XForm ووضعه على صفحة PDF موجودة.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

1. تم تثبيت Visual Studio مع إطار عمل .NET.
2. مكتبة Aspose.PDF لـ .NET.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع جديد في Visual Studio وقم بإضافة مرجع إلى مكتبة Aspose.PDF لـ .NET. يمكنك تنزيل المكتبة من موقع Aspose الرسمي وتثبيتها على جهازك.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

في ملف التعليمات البرمجية C# الخاص بك، قم باستيراد مساحات الأسماء المطلوبة للوصول إلى الفئات والأساليب التي يوفرها Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## الخطوة 3: تحديد مسارات الملفات

حدد مسارات الملف لصورة الخلفية وملف PDF المدخل وملف PDF الناتج:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

تأكد من تحديد مسارات الملفات الفعلية على جهازك.

## الخطوة 4: تحميل ملف PDF الإدخال

استخدم الكود التالي لتحميل ملف PDF المدخل:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// يستخدم التعليمة البرمجية التالية عوامل تشغيل GSave/GRestore
// يستخدم الكود عامل التشغيل ContatenateMatrix لتحديد موضع XForm
// يستخدم الكود عامل التشغيل Do لرسم XForm على الصفحة
// يقوم مشغلو GSave/GRestore بتغليف المحتوى الموجود
// ويتم ذلك للحصول على حالة الرسومات الأولية في نهاية المحتوى الموجود
// وإلا فقد تكون هناك تحولات غير مرغوب فيها متبقية في نهاية سلسلة المشغلين الحاليين
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// أضف عامل تشغيل GSave لإعادة ضبط حالة الرسومات بشكل صحيح بعد الأوامر الجديدة
pageContents. Add(new GSave());

// قم بإنشاء XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// ضبط عرض وارتفاع الصورة
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// تحميل الصورة في دفق
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// أضف الصورة إلى مجموعة صور موارد XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// استخدام عامل التشغيل Do: يقوم هذا العامل برسم الصورة
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//ضع XForm عند الإحداثيات x=100 وy=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// ارسم XForm باستخدام عامل التشغيل Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// ضع XForm عند الإحداثيات x=100 وy=300
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

### نموذج التعليمات البرمجية المصدر لـ Draw XForm On Page باستخدام Aspose.PDF لـ .NET
 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// توضح العينة
	// استخدام مشغلي GSave/GRestore
	// استخدام مشغل ContatenateMatrix لتحديد موضع xForm
	// قم باستخدام عامل التشغيل لرسم xForm على الصفحة
	// لف المحتويات الموجودة باستخدام زوج مشغلي GSave/GRestore
	// هذا للحصول على حالة الرسومات الأولية للمحتويات الموجودة
	// وإلا فقد تظل هناك بعض التحولات غير المرغوب فيها في نهاية سلسلة المشغلين الحاليين
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// أضف عامل حفظ حالة الرسومات لمسح حالة الرسومات بشكل صحيح بعد الأوامر الجديدة
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// إنشاء إكسفورم
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// تحديد عرض الصورة وارتفاعها
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// تحميل الصورة في الدفق
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//أضف صورة إلى مجموعة الصور الخاصة بموارد XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// استخدام عامل التشغيل Do: يقوم هذا العامل برسم الصورة
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// ضع النموذج على إحداثيات x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// ارسم النموذج باستخدام عامل التشغيل Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// ضع النموذج على إحداثيات x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// ارسم النموذج باستخدام عامل التشغيل Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// استعادة حالة الرسومات باستخدام GRestore بعد GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية رسم نموذج XForm على صفحة PDF باستخدام Aspose.PDF لـ .NET. باتباع الخطوات الموضحة، ستتمكن من إضافة نموذج XForm ووضعه على صفحة موجودة، مما يوفر المزيد من المرونة لمستندات PDF الخاصة بك.

### الأسئلة الشائعة حول رسم XForm على الصفحة

#### س: ما هو XForm في Aspose.PDF؟

ج: إن XForm هو كائن رسومي قابل لإعادة الاستخدام في مستند PDF. يتيح لك تحديد ورسم الرسومات أو الصور أو النصوص المعقدة التي يمكن إعادة استخدامها عدة مرات على صفحات مختلفة.

#### س: كيف يمكنني استيراد مساحات الأسماء الضرورية لـ Aspose.PDF؟

 ج: في ملف التعليمات البرمجية C# الخاص بك، استخدم ملف`using` توجيه لاستيراد مساحات الأسماء المطلوبة للوصول إلى الفئات والأساليب التي يوفرها Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### س: ما هو الغرض من مشغلي GSave وGRestore؟

 ج: ال`GSave` و`GRestore`يتم استخدام عوامل التشغيل في Aspose.PDF لحفظ حالة الرسومات واستعادتها. فهي تساعد على التأكد من أن التحويلات والإعدادات المطبقة على قسم واحد من المحتوى لا تؤثر على الأقسام اللاحقة.

#### س: كيف يمكنني تعريف XForm باستخدام Aspose.PDF؟

 ج: لإنشاء XForm، استخدم ملف`XForm.CreateNewForm` الطريقة وإضافتها إلى`Resources.Forms` مجموعة من صفحة معينة. يمكنك بعد ذلك إضافة محتوى إلى XForm`Contents` ملكية.

#### س: كيف يمكنني رسم صورة داخل XForm؟

 ج: قم بتحميل الصورة في دفق وأضفها إلى ملف`Resources.Images` مجموعة من XForm. استخدم ال`Do` المشغل داخل XForm`Contents` لرسم الصورة.

#### س: كيف يمكنني وضع XForm على صفحة PDF؟

 ج: لوضع XForm على الصفحة، استخدم الأمر`ConcatenateMatrix` عامل داخل الصفحة`Contents`. اضبط معلمات المصفوفة لتحديد الترجمة (الموضع) وقياس XForm.

#### س: هل يمكنني رسم نماذج XForms متعددة في نفس الصفحة؟

 ج: نعم، يمكنك رسم XForms متعددة على نفس الصفحة عن طريق ضبط`ConcatenateMatrix`المعلمات لوضع كل XForm في إحداثيات مختلفة.

#### س: هل يمكنني تعديل محتوى XForm بعد إنشائه؟

 ج: نعم، يمكنك تعديل محتويات XForm بعد إنشائه عن طريق إضافة عوامل تشغيل إضافية إليه`Contents` ملكية.

#### س: ماذا يحدث إذا قمت بحذف مشغلي GSave وGRestore؟

ج: قد يؤدي حذف عاملي GSave وGRestore إلى تحويلات أو إعدادات غير مرغوب فيها يتم تطبيقها على المحتوى اللاحق. يساعد استخدامها في الحفاظ على حالة رسومات نظيفة.

#### س: هل يمكنني إعادة استخدام XForms عبر صفحات مختلفة من مستند PDF؟

 ج: نعم، يمكنك إعادة استخدام XForms على صفحات متعددة عن طريق إضافة نفس XForm إلى ملف`Resources.Forms` مجموعة من الصفحات المختلفة.

#### س: هل هناك حد لعدد XForms الذي يمكنني إنشاؤه؟

ج: على الرغم من عدم وجود حد صارم لعدد XForms التي يمكنك إنشاؤها، ضع في اعتبارك أن عددًا كبيرًا جدًا من XForms قد يؤثر على الأداء واستخدام الذاكرة. استخدامها بحكمة.

#### س: هل يمكنني تدوير XForm أو تطبيق تحويلات أخرى؟

 ج: نعم، يمكنك استخدام`ConcatenateMatrix`عامل التشغيل لتطبيق التحويلات مثل التدوير والقياس والترجمة إلى XForm.
