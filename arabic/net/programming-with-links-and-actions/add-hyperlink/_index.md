---
title: إضافة ارتباط تشعبي في ملف PDF
linktitle: إضافة ارتباط تشعبي في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: أضف ارتباطات تشعبية تفاعلية بسهولة في ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-links-and-actions/add-hyperlink/
---
تسمح لك إضافة ارتباطات تشعبية في ملف PDF بإنشاء ارتباطات تشعبية تفاعلية لصفحات أو مواقع ويب أو وجهات أخرى في المستند. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة إضافة ارتباطات تشعبية باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد إضافة ارتباط تشعبي إليه. يستبدل`"YOUR DOCUMENT DIRECTORY"`في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنفتح الآن مستند PDF الذي نريد إضافة ارتباط تشعبي إليه باستخدام الكود التالي:

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## الخطوة 4: إنشاء ارتباط

 في هذه الخطوة ، سننشئ ارتباطًا تشعبيًا باستخدام الامتداد`LinkAnnotation` حاشية. ملاحظة. سنحدد تفاصيل الاتصال ومنطقة الارتباط ونوع الارتباط ومحتوى الارتباط. هذا هو الكود المقابل:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## الخطوة 5: أضف نصًا إضافيًا

 بالإضافة إلى الارتباط التشعبي ، يمكننا أيضًا إضافة نص إضافي باستخدام الامتداد`FreeTextAnnotation` حاشية. ملاحظة. سنحدد الإحداثيات ومظهر النص ومحتوى النص. هذا هو الكود المقابل:

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## الخطوة 6: احفظ الملف المحدث

 الآن دعنا نحفظ ملف PDF المحدث باستخدام امتداد`Save` طريقة`document` هدف. هذا هو الكود المقابل:

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لإضافة ارتباط تشعبي باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document document = new Document(dataDir + "AddHyperlink.pdf");
// إنشاء رابط
Page page = document.Pages[1];
// إنشاء رابط التعليق التوضيحي
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// إنشاء كائن حد لـ LinkAnnotation
Border border = new Border(link);
// اضبط قيمة عرض الحد على 0
border.Width = 0;
// قم بتعيين حدود LinkAnnotation
link.Border = border;
// حدد نوع الارتباط كعنوان URI بعيد
link.Action = new GoToURIAction("www.aspose.com");
//أضف تعليقًا توضيحيًا للرابط إلى مجموعة التعليقات التوضيحية للصفحة الأولى من ملف PDF
page.Annotations.Add(link);
// قم بإنشاء تعليق توضيحي مجاني للنص
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
// ستتم إضافة سلسلة كنص مجاني
textAnnotation.Contents = "Link to Aspose website";
// قم بتعيين الحدود للتعليق التوضيحي للنص الحر
textAnnotation.Border = border;
// أضف تعليقًا توضيحيًا لـ FreeText إلى مجموعة التعليقات التوضيحية للصفحة الأولى من المستند
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
// احفظ المستند المحدث
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## خاتمة

تهنئة ! لديك الآن دليل خطوة بخطوة لإضافة ارتباطات تشعبية باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لإنشاء روابط تفاعلية في مستندات PDF الخاصة بك.

### الأسئلة الشائعة حول إضافة ارتباط تشعبي في ملف PDF

#### س: لماذا يجب أن أفكر في إضافة ارتباطات تشعبية إلى ملفات PDF الخاصة بي؟

ج: تعمل إضافة ارتباطات تشعبية إلى ملفات PDF على تحسين تجربة المستخدم من خلال السماح للقراء بالتنقل بسهولة إلى صفحات أو مواقع ويب أو وجهات أخرى داخل المستند. يوفر طريقة سلسة للوصول إلى موارد إضافية أو المعلومات ذات الصلة.

#### س: هل Aspose.PDF for .NET مناسب للمبتدئين؟

ج: نعم ، Aspose.PDF for .NET صديق للمبتدئين. يعمل البرنامج التعليمي خطوة بخطوة المقدم في هذا الدليل على تبسيط عملية إضافة الارتباطات التشعبية إلى ملفات PDF ، مما يجعلها في متناول المطورين من مختلف مستويات المهارة.

#### س: هل يمكنني تخصيص مظهر الارتباطات التشعبية؟

ج: إطلاقا! يوفر Aspose.PDF for .NET خيارات تخصيص لمظهر الارتباط التشعبي ، بما في ذلك لون النص والنمط والتنسيق. هذا يسمح لك بمطابقة الارتباطات التشعبية مع التصميم العام للمستند الخاص بك.

#### س: هل الارتباطات التشعبية مدعومة في جميع أنواع مستندات PDF؟

ج: نعم ، يمكن إضافة الارتباطات التشعبية إلى أنواع مختلفة من مستندات PDF ، بما في ذلك المستندات النصية والصور وملفات الوسائط المتعددة الغنية. يضمن Aspose.PDF for .NET عمل الارتباطات التشعبية عبر تنسيقات PDF المختلفة.

#### س: ما هي الوظائف الأخرى التي يوفرها Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET مكتبة قوية توفر مجموعة واسعة من الميزات ، بما في ذلك إنشاء ملفات PDF ومعالجتها وتحويلها واستخراجها. وهو يدعم العمل مع النصوص والصور والتعليقات التوضيحية والمزيد ، مما يجعله أداة متعددة الاستخدامات للمهام المتعلقة بـ PDF.

#### س: هل يمكن إضافة الارتباطات التشعبية إلى أقسام معينة داخل المستند؟

 ج: نعم ، باستخدام ملف`LinkAnnotation` التعليق التوضيحي ، يمكنك إنشاء ارتباطات تشعبية توجه المستخدمين إلى أقسام معينة داخل مستند PDF. هذه الميزة مفيدة بشكل خاص لإنشاء جدول محتويات تفاعلي أو روابط مرجعية.

#### س: هل هناك أي قيود على إضافة الارتباطات التشعبية في ملفات PDF؟

ج: بينما يقدم Aspose.PDF for .NET وظائف ارتباط تشعبي شاملة ، من المهم التأكد من أن المحتوى المرتبط يظل متاحًا ومحدّثًا. يجب التحقق من الارتباطات التشعبية إلى مواقع الويب الخارجية بانتظام لتجنب الروابط المعطلة.

#### س: هل يمكنني إنشاء ارتباطات تشعبية لملفات خارجية باستخدام Aspose.PDF for .NET؟

ج: نعم ، بالإضافة إلى عناوين URL على الويب ، يمكنك إنشاء ارتباطات تشعبية تؤدي إلى ملفات خارجية ، مثل مستندات PDF الأخرى أو الصور أو ملفات الوسائط المتعددة. يوفر Aspose.PDF for .NET المرونة في الارتباط بأنواع مختلفة من الموارد.