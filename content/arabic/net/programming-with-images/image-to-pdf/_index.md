---
title: الصورة إلى PDF
linktitle: الصورة إلى PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك تحويل الصورة إلى PDF بسهولة باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 180
url: /ar/net/programming-with-images/image-to-pdf/
---
Aspose.PDF for .NET هي مكتبة قوية تتيح للمطورين إنشاء مستندات PDF ومعالجتها وتحويلها باستخدام C# أو أي لغة .NET. في هذا البرنامج التعليمي، سنرشدك خلال عملية تحويل صورة إلى PDF باستخدام Aspose.PDF for .NET.

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

 في كود C#، الخطوة الأولى هي تهيئة`Document` الكائن. يمثل هذا الكائن مستند PDF الذي سننشئه. أضف الكود التالي إلى مشروعك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"`مع المسار الفعلي الذي تريد حفظ ملف PDF فيه.

## الخطوة 4: إضافة صفحة إلى المستند

 بعد ذلك، نحتاج إلى إضافة صفحة إلى المستند. يتم تمثيل الصفحة بواسطة`Page` استخدم الكود التالي لإضافة صفحة إلى المستند:

```csharp
Page page = doc.Pages.Add();
```

 يقوم هذا الكود بإنشاء صفحة جديدة وإضافتها إلى`Pages` مجموعة الوثيقة.

## الخطوة 5: تحميل ملف الصورة

 لتحويل صورة إلى PDF، نحتاج أولاً إلى تحميل ملف الصورة المصدر. في هذا المثال، نفترض أن اسم ملف الصورة هو`aspose-logo.jpg` ويقع في نفس الدليل الذي يوجد به ملف C# الخاص بك. استخدم الكود التالي لتحميل ملف الصورة:

```csharp
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
```

 تأكد من الاستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي لملف الصورة.

## الخطوة 6: ضبط الهوامش ومربع الاقتصاص

قبل إضافة الصورة إلى صفحة PDF، يمكننا تخصيص تخطيط الصفحة. على سبيل المثال، يمكننا ضبط الهوامش ومربع الاقتصاص لتناسب أبعاد الصورة. استخدم الكود التالي لضبط إعدادات الصفحة:

```csharp
Bitmap b = new Bitmap(mystream);
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page

.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
```

تضمن هذه الإعدادات أن الصورة سوف تتناسب مع الصفحة دون أي هوامش إضافية.

## الخطوة 7: إنشاء كائن صورة

 الآن، دعونا ننشئ`Aspose.Pdf.Image` الكائن الذي يحمل بيانات الصورة. أضف الكود التالي إلى مشروعك:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

سيمثل هذا الكائن الصورة التي نريد إضافتها إلى صفحة PDF.

## الخطوة 8: إضافة الصورة إلى الصفحة

 لإضافة الصورة إلى صفحة PDF، نحتاج إلى تعيين بيانات الصورة إلى`ImageStream` ممتلكات`Aspose.Pdf.Image` الكائن. استخدم الكود التالي لإضافة الصورة:

```csharp
image1.ImageStream = mystream;
page.Paragraphs.Add(image1);
```

 هنا، نقوم بتعيين تدفق الصورة إلى`ImageStream` الخاصية ثم قم بإضافة كائن الصورة إلى`Paragraphs` مجموعة من الصفحات.

## الخطوة 9: حفظ ملف PDF

بمجرد إضافة الصورة إلى صفحة PDF، يمكننا حفظ ملف PDF الناتج. استخدم الكود التالي لحفظ الملف:

```csharp
dataDir = dataDir + "ImageToPDF_out.pdf";
doc.Save(dataDir);
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع دليل الإخراج المطلوب واسم الملف.

## الخطوة 10: إغلاق مجرى الذاكرة

بعد حفظ ملف PDF، من المهم إغلاق مجرى الذاكرة لتحرير موارد النظام. أضف الكود التالي لإغلاق مجرى الذاكرة:

```csharp
mystream. Close();
```

## تشغيل الكود والتحقق من الناتج

لقد أكملت الآن تنفيذ التعليمات البرمجية. قم بتشغيل التعليمات البرمجية وتأكد من تحويل الصورة بنجاح إلى ملف PDF. يجب حفظ ملف الإخراج في الدليل المحدد.


### عينة من كود المصدر لتحويل الصورة إلى PDF باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن مستند
Document doc = new Document();
// إضافة صفحة إلى مجموعة صفحات المستند
Page page = doc.Pages.Add();
// تحميل ملف الصورة المصدر إلى كائن Stream
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
// إنشاء كائن BitMap باستخدام دفق الصورة المحمّل
Bitmap b = new Bitmap(mystream);
// قم بتعيين الهوامش حتى تتناسب الصورة، وما إلى ذلك.
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
// إنشاء كائن صورة
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// أضف الصورة إلى مجموعة فقرات القسم
page.Paragraphs.Add(image1);
// تعيين تدفق ملف الصورة
image1.ImageStream = mystream;
dataDir = dataDir + "ImageToPDF_out.pdf";
// حفظ ملف PDF الناتج
doc.Save(dataDir);
// إغلاق كائن memoryStream
mystream.Close();
Console.WriteLine("\nImage converted to pdf successfully.\nFile saved at " + dataDir); 
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تحويل صورة إلى PDF باستخدام Aspose.PDF لـ .NET. قمنا بتغطية العملية خطوة بخطوة، بما في ذلك إعداد البيئة، واستيراد المكتبات، وتهيئة كائن المستند، وتحميل ملف الصورة، وتعيين الهوامش ومربع الاقتصاص، وإضافة الصورة إلى الصفحة، وحفظ ملف PDF، وإغلاق مجرى الذاكرة. باتباع هذه الخطوات، يمكنك بسهولة تحويل الصور إلى PDF في تطبيقات .NET الخاصة بك.

### الأسئلة الشائعة

#### س: ما هو Aspose.PDF لـ .NET، وكيف يساعد في العمل مع مستندات PDF؟

ج: Aspose.PDF for .NET هي مكتبة قوية تتيح للمطورين إنشاء مستندات PDF ومعالجتها وتحويلها باستخدام لغة C# أو أي لغة .NET. وهي تبسط المهام المتعلقة بإنشاء ملفات PDF وتعديلها وتحويلها داخل تطبيقات .NET.

#### س: ما هو الغرض من تحويل صورة إلى PDF باستخدام Aspose.PDF لـ .NET؟

أ: تحويل صورة إلى PDF يسمح لك بتضمين الصور في مستند PDF، مما يتيح لك إدارة المستندات ومشاركتها وإمكانيات الطباعة بشكل أفضل.

####  س: لماذا؟`using` statements necessary in the C# code?

 أ: ال`using` تستورد العبارات مساحات الأسماء المطلوبة، مما يسمح لك باستخدام الفئات والطرق من تلك المساحات دون تأهيلها بالكامل. وهذا يعزز من وضوح الكود وإيجازه.

####  س5: ما هو الدور الذي يلعبه`Document` object play in the image-to-PDF conversion process?
 أ: ال`Document` يمثل الكائن مستند PDF الذي ستقوم بإنشائه. ويعمل كحاوية للصفحات والفقرات وعناصر PDF المتنوعة.

#### س: كيف يتم تحميل الصورة في مستند PDF باستخدام Aspose.PDF لـ .NET؟

 أ: يتم تحميل الصورة في مستند PDF عن طريق إنشاء`Aspose.Pdf.Image` الكائن وتعيين بيانات الصورة له`ImageStream` الملكية. ثم يتم إضافة هذا الكائن إلى`Paragraphs` مجموعة من صفحات PDF.

#### س: ما هي الخطوات المتبعة لضبط تخطيط الصفحة قبل إضافة الصورة إلى صفحة PDF؟

ج: يسمح لك الكود بتعيين الهوامش وأبعاد مربعات القص لتخصيص تخطيط الصفحة. وهذا يضمن أن الصورة تتناسب مع الصفحة دون هوامش إضافية.

#### س: لماذا من المهم إغلاق مجرى الذاكرة بعد حفظ ملف PDF؟

أ: يؤدي إغلاق مجرى الذاكرة إلى تحرير موارد النظام المرتبطة ببيانات الصورة، مما يمنع تسرب الذاكرة ويحسن استخدام الموارد.

#### س: هل يمكن استخدام رمز تحويل الصورة إلى PDF هذا للصور المتعددة داخل مستند PDF واحد؟

ج: نعم، يمكن تعديل هذا الكود لتحويل صور متعددة إلى مستند PDF واحد. يمكنك تكرار العملية لكل صورة، وإضافتها إلى صفحات منفصلة أو ترتيبها حسب الحاجة.

#### س: كيف يمكن للمطورين الاستفادة من استخدام Aspose.PDF لـ .NET لتحويل الصور إلى PDF؟

ج: يمكن للمطورين تبسيط عملية إضافة الصور إلى مستندات PDF، وتحسين عرض المستندات ومشاركتها وإمكانيات الأرشفة. تعد هذه الإمكانية مفيدة لإنشاء التقارير والعروض التقديمية والوثائق الغنية بالصور.