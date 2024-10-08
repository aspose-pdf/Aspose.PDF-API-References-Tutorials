---
title: خوارزمية برادلي
linktitle: خوارزمية برادلي
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تحويل ملف PDF إلى TIFF باستخدام خوارزمية Bradley في Aspose.PDF لـ .NET. دليل خطوة بخطوة، ومتطلبات أساسية، وأسئلة شائعة للتحويل السلس.
type: docs
weight: 30
url: /ar/net/programming-with-images/bradley-algorithm/
---
## مقدمة

قد يتطلب العمل مع ملفات PDF في بعض الأحيان أكثر من مجرد قراءتها أو تحريرها، فقد تحتاج إلى تحويلها إلى صور. إحدى الطرق القوية لتحويل ملفات PDF إلى صور TIFF هي استخدام خوارزمية برادلي من خلال مكتبة Aspose.PDF for .NET. تضمن هذه الطريقة صورًا ثنائية عالية الجودة، وهي مثالية لأرشفة المستندات وحالات الاستخدام المتخصصة الأخرى.

سيرشدك هذا البرنامج التعليمي خلال عملية مفصلة وسهلة المتابعة لتحويل صفحة PDF إلى صورة TIFF باستخدام خوارزمية Bradley Binarization. يبسط Aspose.PDF for .NET هذه المهمة، مما يوفر لك القدرة على أتمتة وتبسيط سير عمل المستندات الخاصة بك.

## المتطلبات الأساسية

قبل أن نتعمق في الكود، دعنا نتأكد من أنك حصلت على كل ما تحتاج إليه للمتابعة:

-  Aspose.PDF for .NET: ستحتاج إلى المكتبة. قم بتنزيلها من[هنا](https://releases.aspose.com/pdf/net/).
- Visual Studio (أو أي C# IDE).
- المعرفة الأساسية بلغة C#.
-  رخصة سارية المفعول أو[رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) من Aspose.

## استيراد الحزم

أولاً وقبل كل شيء، تأكد من استيراد المساحات الأساسية اللازمة إلى مشروعك. ستوفر لك هذه المكتبات الأدوات اللازمة للتعامل مع مستندات PDF وتحويلها إلى تنسيق TIFF وتطبيق خوارزمية التثنية Bradley.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

دعنا نقسم العملية إلى خطوات سهلة لضمان إمكانية متابعتها بسلاسة. بحلول نهاية هذا الدليل، ستتمكن بنجاح من تحويل صفحة PDF إلى صورة TIFF ثنائية باستخدام خوارزمية برادلي.

## الخطوة 1: تعيين دليل المستندات

الخطوة الأولى هي تحديد المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك. كما ستحدد مسارات الإخراج لصور TIFF التي سيتم إنشاؤها.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // المسار إلى ملف PDF الخاص بك
```

هذا هو المكان الذي يمكنك تخزين كل من ملفات PDF المصدر وملفات TIFF المحولة فيه. تأكد من ضبط الدليل بشكل صحيح حتى يتمكن الكود من قراءة الملفات وكتابتها دون أخطاء.

## الخطوة 2: افتح مستند PDF

الآن بعد تحديد المسار، حان الوقت لفتح مستند PDF الذي تريد تحويله. يجعل Aspose.PDF for .NET من السهل تحميل مستند لمزيد من المعالجة.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

 هنا،`PageToTIFF.pdf` هذا هو ملف العينة. يمكنك استبداله بأي ملف PDF من اختيارك. يحتوي كائن المستند الآن على ملف PDF لمزيد من المعالجة.

## الخطوة 3: تحديد مسارات الإخراج للصور

بعد ذلك، ستقوم بتحديد مسارات الإخراج لملفات TIFF المُنشأة، بما في ذلك ملف TIFF القياسي والإصدار الثنائي.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

من خلال فصل هذه المسارات، سيكون لديك ملف واحد لتحويل TIFF القياسي وملف آخر للصورة الثنائية بعد تطبيق خوارزمية برادلي.

## الخطوة 4: إنشاء كائن الدقة

عند تحويل ملفات PDF إلى TIFF، تلعب الدقة دورًا مهمًا في تحديد جودة الصورة. ولأغراضنا، سنضبطها على 300 نقطة في البوصة لضمان جودة عالية في الإخراج.

```csharp
Resolution resolution = new Resolution(300);
```

إن ارتفاع معدل DPI يعني وضوحًا أفضل للصورة، خاصة عند التعامل مع المستندات التي سيتم طباعتها أو أرشفتها.

## الخطوة 5: تكوين إعدادات TIFF

بعد ذلك، ستحتاج إلى تكوين الإعدادات لصورة TIFF. هنا، سنستخدم ضغط LZW ونضبط عمق اللون على 1bpp (بت واحد لكل بكسل) للحصول على صورة ثنائية.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

من خلال ضبط العمق إلى 1bpp، نقوم بإعداد الصورة لإخراج ثنائي. تم اختيار ضغط LZW لكفاءته في تقليل حجم الملف دون فقدان الجودة.

## الخطوة 6: إنشاء جهاز TIFF

الآن، ستحتاج إلى إنشاء جهاز TIFF الذي سيتولى عملية التحويل. يستخدم هذا الجهاز الدقة وإعدادات TIFF المحددة مسبقًا.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

يعد جهاز TIFF هو جوهر هذه العملية. فهو يأخذ مستند PDF ويحول كل صفحة إلى صورة TIFF، استنادًا إلى الإعدادات المحددة مسبقًا.

## الخطوة 7: تحويل صفحة PDF إلى TIFF

 لقد حان الوقت لمعالجة ملف PDF وتحويل الصفحة الأولى إلى صورة TIFF.`Process` تتيح لك هذه الطريقة تحويل صفحات محددة أو المستند بأكمله. في هذا المثال، نقوم بتحويل الصفحة الأولى.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

بمجرد اكتمال الطريقة، سيكون لديك صورة TIFF محفوظة في الموقع الذي حددته مسبقًا.

## الخطوة 8: تطبيق خوارزمية برادلي الثنائية

الآن يأتي السحر - خوارزمية برادلي! تقوم هذه الخوارزمية بتحويل صورة TIFF ذات التدرج الرمادي إلى صورة ثنائية، مما يؤدي إلى تحسينها لأنظمة التعرف على المستندات.

```csharp
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
    using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
    {
        tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
    }
}
```

 تأخذ طريقة BinarizeBradley تيارين من الملفات (الإدخال والإخراج)، بالإضافة إلى قيمة عتبة (هنا،`0.1`) الذي يحدد مستوى التثنية. بعد التنفيذ، سيكون لديك صورة ثنائية مثالية جاهزة للاستخدام.

## الخطوة 9: تأكيد التحويل الناجح

أخيرًا، من الجيد إعلام المستخدم بنجاح العملية. يمكنك القيام بذلك باستخدام إخراج بسيط من وحدة التحكم.

```csharp
System.Console.WriteLine("Conversion using Bradley algorithm performed successfully!");
```

بمجرد طباعة هذا، ستعرف أن صفحة PDF الخاصة بك تم تحويلها بنجاح إلى صورة TIFF ثنائية!

## خاتمة

هذا كل ما في الأمر! لقد تعلمت للتو كيفية تحويل صفحة PDF إلى صورة TIFF وتطبيق خوارزمية التثنية Bradley باستخدام Aspose.PDF لـ .NET. هذه العملية ضرورية لأرشفة المستندات والتعرف الضوئي على الحروف (OCR) والتطبيقات المهنية الأخرى. بفضل الدقة العالية والضغط الفعّال، يمكنك ضمان وضوح صور المستندات الخاصة بك وسهولة التحكم في حجمها.

## الأسئلة الشائعة

### ما هي خوارزمية برادلي؟
خوارزمية برادلي هي تقنية ثنائية تقوم بتحويل الصور ذات التدرج الرمادي إلى صور ثنائية (أبيض وأسود) من خلال تحديد عتبة تكيفية لكل بكسل بناءً على محيطه.

### هل يمكنني تحويل عدة صفحات PDF إلى TIFF باستخدام هذه الطريقة؟
 نعم يمكنك تعديل`Process` طريقة لتحويل جميع الصفحات عن طريق التنقل عبر الصفحات الموجودة في المستند.

### ما هو الدقة الأمثل لتحويل ملفات PDF إلى TIFF؟
للحصول على صور عالية الجودة، يوصى عمومًا باستخدام دقة 300 نقطة في البوصة. ومع ذلك، يمكنك ضبط هذه القيمة وفقًا لاحتياجاتك.

### ماذا يعني 1bpp في عمق اللون؟
1bpp (بت واحد لكل بكسل) يعني أن الصورة ستكون بالأبيض والأسود، حيث يكون كل بكسل إما أسود بالكامل أو أبيض بالكامل.

### هل خوارزمية برادلي مناسبة للتعرف الضوئي على الحروف؟
نعم، غالبًا ما يتم استخدام خوارزمية برادلي في معالجة OCR المسبقة لأنها تعمل على تعزيز تباين النص في المستندات الممسوحة ضوئيًا.