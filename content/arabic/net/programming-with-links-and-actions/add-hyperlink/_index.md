---
title: إضافة ارتباط تشعبي في ملف PDF
linktitle: إضافة ارتباط تشعبي في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك بسهولة إضافة ارتباطات تشعبية تفاعلية في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-links-and-actions/add-hyperlink/
---
تتيح لك إضافة ارتباطات تشعبية في ملف PDF إنشاء ارتباطات تشعبية تفاعلية لصفحات أو مواقع ويب أو وجهات أخرى في المستند. باستخدام Aspose.PDF for .NET، يمكنك بسهولة إضافة ارتباطات تشعبية باتباع التعليمات البرمجية المصدرية التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ، عليك استيراد المكتبات اللازمة لمشروع C# الخاص بك. إليك تعليمات الاستيراد اللازمة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## الخطوة 2: تعيين المسار إلى مجلد المستندات

 في هذه الخطوة، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد إضافة ارتباط تشعبي إليه. استبدل`"YOUR DOCUMENT DIRECTORY"` في الكود التالي مع المسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 3: افتح مستند PDF

الآن سوف نقوم بفتح ملف PDF الذي نريد إضافة رابط تشعبي إليه باستخدام الكود التالي:

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## الخطوة 4: إنشاء رابط

 في هذه الخطوة، سنقوم بإنشاء ارتباط تشعبي باستخدام`LinkAnnotation` الشرح التوضيحي. سنحدد تفاصيل الاتصال ومنطقة الرابط ونوع الرابط ومحتوى الرابط. هذا هو الكود المقابل:

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

 بالإضافة إلى الارتباط التشعبي، يمكننا أيضًا إضافة نص إضافي باستخدام`FreeTextAnnotation` الشرح التوضيحي. سوف نحدد الإحداثيات ومظهر النص ومحتوى النص. هذا هو الكود المقابل:

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## الخطوة 6: احفظ الملف المحدث

الآن دعنا نحفظ ملف PDF المحدث باستخدام`Save` طريقة`document` الكائن. هذا هو الكود المقابل:

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### عينة من كود المصدر لإضافة ارتباط تشعبي باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document document = new Document(dataDir + "AddHyperlink.pdf");
// إنشاء رابط
Page page = document.Pages[1];
// إنشاء كائن تعليق الارتباط
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// إنشاء كائن حدود لـ LinkAnnotation
Border border = new Border(link);
// تعيين قيمة عرض الحدود إلى 0
border.Width = 0;
// تعيين الحدود لـ LinkAnnotation
link.Border = border;
// حدد نوع الرابط كعنوان URI بعيد
link.Action = new GoToURIAction("www.aspose.com");
// إضافة تعليق ارتباط إلى مجموعة التعليقات التوضيحية للصفحة الأولى من ملف PDF
page.Annotations.Add(link);
// إنشاء تعليقات توضيحية للنص مجانًا
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
// سلسلة سيتم إضافتها كنص حر
textAnnotation.Contents = "Link to Aspose website";
// تعيين الحدود للتعليق النصي المجاني
textAnnotation.Border = border;
// إضافة تعليق FreeText إلى مجموعة التعليقات التوضيحية للصفحة الأولى من المستند
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
// حفظ المستند المحدث
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## خاتمة

تهانينا! لديك الآن دليل خطوة بخطوة لإضافة ارتباطات تشعبية باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الكود لإنشاء روابط تفاعلية في مستندات PDF الخاصة بك.

### الأسئلة الشائعة حول إضافة ارتباط تشعبي في ملف PDF

#### س: لماذا يجب أن أفكر في إضافة ارتباطات تشعبية إلى ملفات PDF الخاصة بي؟

ج: إن إضافة ارتباطات تشعبية إلى ملفات PDF الخاصة بك تعمل على تحسين تجربة المستخدم من خلال السماح للقراء بالتنقل بسهولة إلى صفحات أو مواقع ويب أو وجهات أخرى داخل المستند. كما توفر طريقة سلسة للوصول إلى الموارد الإضافية أو المعلومات ذات الصلة.

#### س: هل Aspose.PDF لـ .NET مناسب للمبتدئين؟

ج: نعم، يعد برنامج Aspose.PDF for .NET مناسبًا للمبتدئين. يعمل البرنامج التعليمي خطوة بخطوة المقدم في هذا الدليل على تبسيط عملية إضافة ارتباطات تشعبية إلى ملفات PDF، مما يجعلها في متناول المطورين من مختلف مستويات المهارة.

#### س: هل يمكنني تخصيص مظهر الروابط التشعبية؟

ج: بالتأكيد! يوفر Aspose.PDF for .NET خيارات تخصيص لمظهر الارتباط التشعبي، بما في ذلك لون النص والأسلوب والتنسيق. يتيح لك هذا مطابقة الارتباطات التشعبية مع التصميم العام للمستند.

#### س: هل يتم دعم الارتباطات التشعبية في جميع أنواع مستندات PDF؟

ج: نعم، يمكن إضافة ارتباطات تشعبية إلى أنواع مختلفة من مستندات PDF، بما في ذلك المستندات النصية والصور والملفات الغنية بالوسائط المتعددة. يضمن Aspose.PDF for .NET أن تكون الارتباطات التشعبية وظيفية عبر تنسيقات PDF المختلفة.

#### س: ما هي الوظائف الأخرى التي يقدمها Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET عبارة عن مكتبة قوية توفر مجموعة واسعة من الميزات، بما في ذلك إنشاء ملفات PDF ومعالجتها وتحويلها واستخراجها. وهي تدعم العمل مع النصوص والصور والتعليقات التوضيحية والمزيد، مما يجعلها أداة متعددة الاستخدامات للمهام المتعلقة بملفات PDF.

#### س: هل من الممكن إضافة ارتباطات تشعبية إلى أقسام محددة داخل المستند؟

 أ: نعم، باستخدام`LinkAnnotation` من خلال التعليقات التوضيحية، يمكنك إنشاء ارتباطات تشعبية توجه المستخدمين إلى أقسام معينة داخل مستند PDF. هذه الميزة مفيدة بشكل خاص لإنشاء جدول محتويات تفاعلي أو روابط مرجعية.

#### س: هل هناك أي قيود على إضافة الروابط التشعبية في ملفات PDF؟

ج: على الرغم من أن Aspose.PDF for .NET يوفر وظائف شاملة للارتباط التشعبي، فمن المهم التأكد من إمكانية الوصول إلى المحتوى المرتبط وتحديثه. يجب التحقق من الارتباطات التشعبية لمواقع الويب الخارجية بانتظام لتجنب الروابط المعطلة.

#### س: هل يمكنني إنشاء ارتباطات تشعبية إلى ملفات خارجية باستخدام Aspose.PDF لـ .NET؟

ج: نعم، بالإضافة إلى عناوين URL للويب، يمكنك إنشاء ارتباطات تشعبية تؤدي إلى ملفات خارجية، مثل مستندات PDF الأخرى أو الصور أو ملفات الوسائط المتعددة. يوفر Aspose.PDF لـ .NET المرونة اللازمة للارتباط بأنواع مختلفة من الموارد.