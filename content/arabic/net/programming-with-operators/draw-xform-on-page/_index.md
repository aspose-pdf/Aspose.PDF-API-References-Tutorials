---
title: ارسم XForm على الصفحة
linktitle: ارسم XForm على الصفحة
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: دليل خطوة بخطوة لرسم نموذج XForm على صفحة PDF باستخدام Aspose.PDF لـ .NET. أضف النموذج وضعه على الصفحة.
type: docs
weight: 10
url: /ar/net/programming-with-operators/draw-xform-on-page/
---
في هذا البرنامج التعليمي، سنزودك بدليل خطوة بخطوة حول كيفية رسم نموذج XForm على صفحة باستخدام Aspose.PDF لـ .NET. Aspose.PDF هي مكتبة قوية تتيح لك إنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا. باستخدام المشغلات التي يوفرها Aspose.PDF، يمكنك إضافة نموذج XForm ووضعه على صفحة PDF موجودة.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. تم تثبيت Visual Studio مع إطار عمل .NET.
2. مكتبة Aspose.PDF لـ .NET.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع جديد في Visual Studio وأضف مرجعًا إلى مكتبة Aspose.PDF for .NET. يمكنك تنزيل المكتبة من موقع Aspose الرسمي وتثبيتها على جهازك.

## الخطوة 2: استيراد المساحات الاسمية الضرورية

في ملف الكود C# الخاص بك، قم باستيراد المساحات الأساسية المطلوبة للوصول إلى الفئات والطرق التي يوفرها Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## الخطوة 3: تعيين مسارات الملفات

قم بتحديد مسارات الملفات لصورة الخلفية وملف PDF المدخل وملف PDF المخرج:

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
// يستخدم الكود التالي مشغلي GSave/GRestore
// يستخدم الكود عامل ContatenateMatrix لتحديد موضع XForm
// يستخدم الكود عامل Do لرسم XForm على الصفحة
// يقوم مشغلو GSave/GRestore بتغليف المحتوى الموجود
//يتم ذلك للحصول على حالة الرسومات الأولية في نهاية المحتوى الموجود
// وإلا فقد تكون هناك تحولات غير مرغوب فيها متبقية في نهاية سلسلة المشغلين الحاليين
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// أضف عامل GSave لإعادة تعيين حالة الرسومات بشكل صحيح بعد الأوامر الجديدة
pageContents. Add(new GSave());

// إنشاء XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// ضبط عرض وارتفاع الصورة
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// تحميل الصورة في تيار
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// أضف الصورة إلى مجموعة صور موارد XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// استخدام عامل Do: يرسم هذا العامل الصورة
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// ضع نموذج X عند الإحداثيات x=100 وy=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// ارسم نموذج X باستخدام عامل Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// ضع نموذج X عند الإحداثيات x=100 وy=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// ارسم نموذج X باستخدام عامل Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// استعادة حالة الرسومات باستخدام GRestore بعد GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

تأكد من تحديد مسارات الملفات الفعلية وضبط رقم الصفحة ومواضع XForm حسب الحاجة.

### عينة من كود المصدر لـ Draw XForm On Page باستخدام Aspose.PDF لـ .NET
 
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
	// استخدام مشغلي GSave/GRestore
	// استخدام عامل ContatenateMatrix لتحديد موضع xForm
	//هل تستخدم المشغل لرسم xForm على الصفحة
	// لف المحتويات الموجودة باستخدام زوج مشغلي GSave/GRestore
	// هذا للحصول على حالة الرسومات الأولية في نهاية المحتويات الموجودة
	// وإلا فقد تظل هناك بعض التحولات غير المرغوب فيها في نهاية سلسلة المشغلين الحالية
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// إضافة عامل حفظ حالة الرسومات لمسح حالة الرسومات بشكل صحيح بعد الأوامر الجديدة
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// إنشاء نموذج xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// تحديد عرض الصورة وارتفاعها
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// تحميل الصورة إلى الدفق
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	// إضافة صورة إلى مجموعة الصور الخاصة بموارد XForm
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// استخدام عامل Do: يقوم هذا العامل برسم الصورة
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// ضع النموذج على إحداثيات x=100 وy=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// رسم نموذج باستخدام عامل Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// ضع النموذج على إحداثيات x=100 وy=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// رسم نموذج باستخدام عامل Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// استعادة حالة الرسومات باستخدام GRestore بعد GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية رسم نموذج XForm على صفحة PDF باستخدام Aspose.PDF for .NET. باتباع الخطوات الموضحة، ستتمكن من إضافة نموذج XForm ووضعه على صفحة موجودة، وبالتالي إضفاء المزيد من المرونة على مستندات PDF الخاصة بك.

### الأسئلة الشائعة حول رسم XForm على الصفحة

#### س: ما هو XForm في Aspose.PDF؟

ج: XForm هو كائن رسومي قابل لإعادة الاستخدام في مستند PDF. يسمح لك بتحديد ورسم رسومات معقدة أو صور أو نصوص يمكن إعادة استخدامها عدة مرات على صفحات مختلفة.

#### س: كيف يمكنني استيراد المساحات الأسماء اللازمة لـ Aspose.PDF؟

 أ: في ملف الكود C# الخاص بك، استخدم`using` التوجيه لاستيراد المساحات المطلوبة للوصول إلى الفئات والطرق التي يوفرها Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### س: ما هو الغرض من مشغلي GSave و GRestore؟

 أ: ال`GSave` و`GRestore` تُستخدم المشغلات في Aspose.PDF لحفظ حالة الرسومات واستعادتها. وهي تساعد في ضمان عدم تأثير التحويلات والإعدادات المطبقة على قسم واحد من المحتوى على الأقسام اللاحقة.

#### س: كيف أقوم بتعريف XForm باستخدام Aspose.PDF؟

 أ: لإنشاء نموذج XForm، استخدم`XForm.CreateNewForm` الطريقة وأضفها إلى`Resources.Forms` مجموعة من صفحة معينة. يمكنك بعد ذلك إضافة محتوى إلى XForm`Contents` ملكية.

#### س: كيف يمكنني رسم صورة داخل XForm؟

أ: قم بتحميل الصورة إلى مجرى وأضفها إلى`Resources.Images` مجموعة من XForm. استخدم`Do` المشغل داخل XForm`Contents` لرسم الصورة.

#### س: كيف يمكنني وضع XForm على صفحة PDF؟

 أ: لوضع نموذج XForm على صفحة، استخدم`ConcatenateMatrix` عامل داخل الصفحة`Contents`. قم بضبط معلمات المصفوفة لتحديد الترجمة (الموضع) وقياس XForm.

#### س: هل يمكنني رسم نماذج XForms متعددة على نفس الصفحة؟

 ج: نعم، يمكنك رسم نماذج XForms متعددة على نفس الصفحة عن طريق ضبط`ConcatenateMatrix` المعلمات لتحديد موضع كل XForm في إحداثيات مختلفة.

#### س: هل يمكنني تعديل محتوى XForm بعد إنشائه؟

 ج: نعم، يمكنك تعديل محتويات XForm بعد إنشائه عن طريق إضافة مشغلات إضافية إليه`Contents` ملكية.

#### س: ماذا يحدث إذا قمت بحذف مشغلي GSave وGRestore؟

ج: قد يؤدي حذف مشغلي GSave وGRestore إلى تطبيق تحويلات أو إعدادات غير مرغوب فيها على المحتوى اللاحق. يساعد استخدامهما في الحفاظ على حالة رسومية نظيفة.

#### س: هل يمكنني إعادة استخدام XForms عبر صفحات مختلفة من مستند PDF؟

 ج: نعم، يمكنك إعادة استخدام XForms على صفحات متعددة عن طريق إضافة نفس XForm إلى`Resources.Forms` مجموعة من الصفحات المختلفة.

#### س: هل هناك حد لعدد XForms التي يمكنني إنشاؤها؟

ج: على الرغم من عدم وجود حد صارم لعدد نماذج XForms التي يمكنك إنشاؤها، ضع في اعتبارك أن إنشاء عدد كبير جدًا من نماذج XForms قد يؤثر على الأداء واستخدام الذاكرة. استخدمها بحكمة.

#### س: هل يمكنني تدوير XForm أو تطبيق تحويلات أخرى؟

 ج: نعم، يمكنك استخدام`ConcatenateMatrix` عامل لتطبيق التحويلات مثل التدوير والتدرج والترجمة إلى XForm.
