---
title: إضافة ارتباط تشعبي في ملف PDF
linktitle: إضافة ارتباط تشعبي في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بإضافة الارتباطات التشعبية التفاعلية بسهولة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-links-and-actions/add-hyperlink/
---
تتيح لك إضافة الارتباطات التشعبية في ملف PDF إنشاء ارتباطات تشعبية تفاعلية لصفحات أو مواقع ويب أو وجهات أخرى في المستند. باستخدام Aspose.PDF for .NET، يمكنك بسهولة إضافة ارتباطات تشعبية باتباع التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C# الخاص بك. فيما يلي توجيه الاستيراد الضروري:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## الخطوة 2: تعيين المسار إلى مجلد المستندات

في هذه الخطوة، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد إضافة رابط تشعبي إليه. يستبدل`"YOUR DOCUMENT DIRECTORY"`في الكود التالي مع المسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

سنقوم الآن بفتح مستند PDF الذي نريد إضافة رابط تشعبي إليه باستخدام الكود التالي:

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## الخطوة 4: إنشاء رابط

 في هذه الخطوة، سنقوم بإنشاء رابط تشعبي باستخدام ملف`LinkAnnotation` حاشية. ملاحظة. سنحدد تفاصيل الاتصال ومساحة الرابط ونوع الرابط ومحتوى الرابط. هنا هو الكود المقابل:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## الخطوة 5: إضافة نص إضافي

 بالإضافة إلى الارتباط التشعبي، يمكننا أيضًا إضافة نص إضافي باستخدام`FreeTextAnnotation` حاشية. ملاحظة. سنحدد الإحداثيات ومظهر النص ومحتوى النص. هنا هو الكود المقابل:

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## الخطوة 6: احفظ الملف المحدث

 الآن دعونا نحفظ ملف PDF المحدث باستخدام ملف`Save` طريقة`document` هدف. هنا هو الكود المقابل:

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
// إنشاء كائن تعليق توضيحي للارتباط
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// قم بإنشاء كائن حدودي لـ LinkAnnotation
Border border = new Border(link);
// قم بتعيين قيمة عرض الحدود على 0
border.Width = 0;
// قم بتعيين الحدود لـ LinkAnnotation
link.Border = border;
// حدد نوع الارتباط كـ URI البعيد
link.Action = new GoToURIAction("www.aspose.com");
//أضف تعليقًا توضيحيًا للارتباط إلى مجموعة التعليقات التوضيحية للصفحة الأولى من ملف PDF
page.Annotations.Add(link);
// إنشاء تعليق توضيحي نصي مجاني
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
// السلسلة المراد إضافتها كنص مجاني
textAnnotation.Contents = "Link to Aspose website";
// قم بتعيين الحدود للتعليق التوضيحي للنص الحر
textAnnotation.Border = border;
// أضف تعليقًا توضيحيًا FreeText إلى مجموعة التعليقات التوضيحية للصفحة الأولى من المستند
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
// حفظ المستند المحدث
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## خاتمة

تهنئة ! لديك الآن دليل خطوة بخطوة لإضافة الارتباطات التشعبية باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الرمز لإنشاء روابط تفاعلية في مستندات PDF الخاصة بك.

### الأسئلة الشائعة لإضافة ارتباط تشعبي في ملف PDF

#### س: لماذا يجب أن أفكر في إضافة ارتباطات تشعبية إلى ملفات PDF الخاصة بي؟

ج: تعمل إضافة الارتباطات التشعبية إلى ملفات PDF الخاصة بك على تحسين تجربة المستخدم من خلال السماح للقراء بالانتقال بسهولة إلى الصفحات أو مواقع الويب أو الوجهات الأخرى داخل المستند. فهو يوفر طريقة سلسة للوصول إلى موارد إضافية أو المعلومات ذات الصلة.

#### س: هل Aspose.PDF for .NET مناسب للمبتدئين؟

ج: نعم، Aspose.PDF for .NET مناسب للمبتدئين. يعمل البرنامج التعليمي خطوة بخطوة المقدم في هذا الدليل على تبسيط عملية إضافة الارتباطات التشعبية إلى ملفات PDF، مما يجعلها في متناول المطورين ذوي مستويات المهارة المختلفة.

#### س: هل يمكنني تخصيص مظهر الارتباطات التشعبية؟

ج: بالتأكيد! يوفر Aspose.PDF for .NET خيارات تخصيص لمظهر الارتباط التشعبي، بما في ذلك لون النص والنمط والتنسيق. يتيح لك ذلك مطابقة الارتباطات التشعبية مع التصميم العام للمستند الخاص بك.

#### س: هل الارتباطات التشعبية مدعومة في جميع أنواع مستندات PDF؟

ج: نعم، يمكن إضافة الارتباطات التشعبية إلى أنواع مختلفة من مستندات PDF، بما في ذلك المستندات النصية والصور والملفات الغنية بالوسائط المتعددة. يضمن Aspose.PDF for .NET أن الارتباطات التشعبية تعمل عبر تنسيقات PDF المختلفة.

#### س: ما هي الوظائف الأخرى التي يقدمها Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET هي مكتبة قوية توفر نطاقًا واسعًا من الميزات، بما في ذلك إنشاء PDF ومعالجته وتحويله واستخراجه. وهو يدعم العمل مع النصوص والصور والتعليقات التوضيحية والمزيد، مما يجعله أداة متعددة الاستخدامات للمهام المتعلقة بملفات PDF.

#### س: هل يمكن إضافة الارتباطات التشعبية إلى أقسام معينة داخل المستند؟

 ج: نعم باستخدام`LinkAnnotation` التعليق التوضيحي، يمكنك إنشاء ارتباطات تشعبية توجه المستخدمين إلى أقسام معينة داخل مستند PDF. هذه الميزة مفيدة بشكل خاص لإنشاء جدول محتويات تفاعلي أو روابط مرجعية.

#### س: هل هناك أي قيود على إضافة الارتباطات التشعبية في ملفات PDF؟

ج: بينما يوفر Aspose.PDF for .NET وظيفة الارتباط التشعبي الشاملة، فمن المهم التأكد من أن المحتوى المرتبط يظل قابلاً للوصول ومحدثًا. يجب التحقق بانتظام من الارتباطات التشعبية لمواقع الويب الخارجية لتجنب الروابط المعطلة.

#### س: هل يمكنني إنشاء ارتباطات تشعبية لملفات خارجية باستخدام Aspose.PDF لـ .NET؟

ج: نعم، بالإضافة إلى عناوين URL على الويب، يمكنك إنشاء ارتباطات تشعبية تؤدي إلى ملفات خارجية، مثل مستندات PDF أو صور أو ملفات وسائط متعددة أخرى. يوفر Aspose.PDF for .NET المرونة اللازمة للارتباط بأنواع مختلفة من الموارد.