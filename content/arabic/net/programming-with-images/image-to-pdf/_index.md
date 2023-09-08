---
title: الصورة إلى PDF
linktitle: الصورة إلى PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل الصورة بسهولة إلى PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 180
url: /ar/net/programming-with-images/image-to-pdf/
---
Aspose.PDF for .NET هي مكتبة قوية تتيح للمطورين إنشاء مستندات PDF ومعالجتها وتحويلها باستخدام لغة C# أو أي لغة .NET. في هذا البرنامج التعليمي، سنرشدك خلال عملية تحويل صورة إلى PDF باستخدام Aspose.PDF لـ .NET.

## الخطوة 1: إعداد البيئة

قبل أن نبدأ، تأكد من تثبيت Aspose.PDF for .NET على نظامك. يمكنك تنزيله وتثبيته من موقع Aspose الرسمي. بمجرد التثبيت، قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.

## الخطوة 2: استيراد المكتبات المطلوبة

لاستخدام Aspose.PDF لـ .NET في مشروعك، تحتاج إلى استيراد المكتبات الضرورية. أضف عبارات الاستخدام التالية في بداية ملف C# الخاص بك:

```csharp
using Aspose.Pdf;
using System.IO;
using System.Drawing;
```

## الخطوة 3: تهيئة كائن المستند

 في كود C#، الخطوة الأولى هي تهيئة ملف`Document` هدف. يمثل هذا الكائن مستند PDF الذي سنقوم بإنشائه. أضف الكود التالي إلى مشروعك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"`بالمسار الفعلي الذي تريد حفظ ملف PDF فيه.

## الخطوة 4: إضافة صفحة إلى المستند

 بعد ذلك، نحتاج إلى إضافة صفحة إلى المستند. يتم تمثيل الصفحة بواسطة`Page` فصل. استخدم الكود التالي لإضافة صفحة إلى المستند:

```csharp
Page page = doc.Pages.Add();
```

 يقوم هذا الرمز بإنشاء صفحة جديدة وإضافتها إلى ملف`Pages` جمع الوثيقة.

## الخطوة 5: تحميل ملف الصورة

 لتحويل صورة إلى PDF، نحتاج أولاً إلى تحميل ملف الصورة المصدر. في هذا المثال، نفترض أن ملف الصورة مسمى`aspose-logo.jpg` ويقع في نفس الدليل الذي يوجد به ملف C# الخاص بك. استخدم الكود التالي لتحميل ملف الصورة:

```csharp
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
```

 تأكد من استبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي لملف الصورة.

## الخطوة 6: تحديد الهوامش ومربع الاقتصاص

قبل إضافة الصورة إلى صفحة PDF، يمكننا تخصيص تخطيط الصفحة. على سبيل المثال، يمكننا ضبط الهوامش ومربع الاقتصاص ليناسب أبعاد الصورة. استخدم الكود التالي لضبط إعدادات الصفحة:

```csharp
Bitmap b = new Bitmap(mystream);
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page

.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
```

تضمن هذه الإعدادات ملاءمة الصورة للصفحة دون أي هوامش إضافية.

## الخطوة 7: إنشاء كائن صورة

الآن، دعونا نقوم بإنشاء`Aspose.Pdf.Image` كائن للاحتفاظ ببيانات الصورة. أضف الكود التالي إلى مشروعك:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

سيمثل هذا الكائن الصورة التي نريد إضافتها إلى صفحة PDF.

## الخطوة 8: إضافة الصورة إلى الصفحة

 لإضافة الصورة إلى صفحة PDF، نحتاج إلى تعيين بيانات الصورة إلى ملف`ImageStream` ملكية`Aspose.Pdf.Image` هدف. استخدم الكود التالي لإضافة الصورة:

```csharp
image1.ImageStream = mystream;
page.Paragraphs.Add(image1);
```

 هنا، نقوم بتعيين دفق الصورة إلى`ImageStream` الخاصية ثم قم بإضافة كائن الصورة إلى`Paragraphs` مجموعة من الصفحة.

## الخطوة 9: حفظ ملف PDF

بمجرد إضافة الصورة إلى صفحة PDF، يمكننا حفظ ملف PDF الناتج. استخدم الكود التالي لحفظ الملف:

```csharp
dataDir = dataDir + "ImageToPDF_out.pdf";
doc.Save(dataDir);
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع دليل الإخراج المطلوب واسم الملف.

## الخطوة 10: إغلاق دفق الذاكرة

بعد حفظ ملف PDF، من المهم إغلاق تدفق الذاكرة لتحرير موارد النظام. أضف الكود التالي لإغلاق دفق الذاكرة:

```csharp
mystream. Close();
```

## تشغيل الكود والتحقق من المخرجات

لقد أكملت الآن تنفيذ التعليمات البرمجية. قم بتشغيل الكود وتحقق من أن الصورة قد تم تحويلها بنجاح إلى PDF. يجب حفظ ملف الإخراج في الدليل المحدد.


### نموذج التعليمات البرمجية المصدر لصورة إلى PDF باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل لكائن المستند
Document doc = new Document();
// إضافة صفحة إلى مجموعة صفحات الوثيقة
Page page = doc.Pages.Add();
// قم بتحميل ملف الصورة المصدر إلى كائن الدفق
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
// إنشاء كائن BitMap مع دفق الصور المحملة
Bitmap b = new Bitmap(mystream);
// قم بتعيين الهوامش بحيث تناسب الصورة، وما إلى ذلك.
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
// إنشاء كائن الصورة
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// إضافة الصورة إلى مجموعة فقرات القسم
page.Paragraphs.Add(image1);
// ضبط دفق ملف الصورة
image1.ImageStream = mystream;
dataDir = dataDir + "ImageToPDF_out.pdf";
// حفظ ملف PDF الناتج
doc.Save(dataDir);
// أغلق كائن دفق الذاكرة
mystream.Close();
Console.WriteLine("\nImage converted to pdf successfully.\nFile saved at " + dataDir); 
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تحويل صورة إلى PDF باستخدام Aspose.PDF لـ .NET. لقد قمنا بتغطية العملية خطوة بخطوة، بما في ذلك إعداد البيئة، واستيراد المكتبات، وتهيئة كائن المستند، وتحميل ملف الصورة، وتعيين الهوامش ومربع الاقتصاص، وإضافة الصورة إلى الصفحة، وحفظ ملف PDF، وإغلاق الملف. تيار الذاكرة. باتباع هذه الخطوات، يمكنك بسهولة تحويل الصور إلى PDF في تطبيقات .NET الخاصة بك.

### الأسئلة الشائعة

#### س: ما هو Aspose.PDF لـ .NET، وكيف يساعد في العمل مع مستندات PDF؟

ج: Aspose.PDF for .NET هي مكتبة قوية تمكن المطورين من إنشاء مستندات PDF ومعالجتها وتحويلها باستخدام لغة C# أو أي لغة .NET. إنه يبسط المهام المتعلقة بإنشاء PDF وتعديله وتحويله داخل تطبيقات .NET.

#### س: ما هو الغرض من تحويل صورة إلى PDF باستخدام Aspose.PDF لـ .NET؟

ج: يتيح لك تحويل صورة إلى PDF دمج الصور في مستند PDF، مما يتيح لك إدارة المستندات ومشاركتها وإمكانيات الطباعة بشكل أفضل.

####  س: لماذا`using` statements necessary in the C# code?

 ج: ال`using` تستورد البيانات مساحات الأسماء المطلوبة، مما يسمح لك باستخدام الفئات والأساليب من مساحات الأسماء هذه دون تأهيلها بشكل كامل. وهذا يعزز التعليمات البرمجية الأنظف والأكثر إيجازًا.

####  س5: ما هو الدور الذي يقوم به`Document` object play in the image-to-PDF conversion process?
 ج: ال`Document` يمثل الكائن مستند PDF الذي ستقوم بإنشائه. إنه بمثابة حاوية للصفحات والفقرات وعناصر PDF المختلفة.

#### س: كيف يتم تحميل الصورة في مستند PDF باستخدام Aspose.PDF لـ .NET؟

 ج: يتم تحميل الصورة في مستند PDF عن طريق إنشاء ملف`Aspose.Pdf.Image` الكائن وتعيين بيانات الصورة له`ImageStream` ملكية. ثم يتم إضافة هذا الكائن إلى`Paragraphs` مجموعة من صفحة PDF.

#### س: ما هي الخطوات المتضمنة في ضبط تخطيط الصفحة قبل إضافة الصورة إلى صفحة PDF؟

ج: يسمح لك الكود بتعيين الهوامش وأبعاد مربع الاقتصاص لتخصيص تخطيط الصفحة. وهذا يضمن أن الصورة تناسب الصفحة دون هوامش إضافية.

#### س: لماذا من المهم إغلاق تدفق الذاكرة بعد حفظ ملف PDF؟

ج: يؤدي إغلاق تدفق الذاكرة إلى تحرير موارد النظام المرتبطة ببيانات الصورة، مما يمنع تسرب الذاكرة ويحسن استخدام الموارد.

#### س: هل يمكن استخدام رمز تحويل الصورة إلى PDF هذا لصور متعددة داخل مستند PDF واحد؟

ج: نعم، يمكن تعديل هذا الرمز لتحويل صور متعددة إلى مستند PDF واحد. يمكنك تكرار العملية لكل صورة، أو إضافتها إلى صفحات منفصلة أو ترتيبها حسب الحاجة.

#### س: كيف يمكن للمطورين الاستفادة من استخدام Aspose.PDF لـ .NET لتحويل الصور إلى PDF؟

ج: يمكن للمطورين تبسيط عملية إضافة الصور إلى مستندات PDF، وتعزيز إمكانات عرض المستندات ومشاركتها وأرشفتها. تعتبر هذه الإمكانية ذات قيمة لإنشاء تقارير وعروض تقديمية ووثائق غنية بالصور.