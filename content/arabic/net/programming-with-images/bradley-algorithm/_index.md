---
title: خوارزمية برادلي
linktitle: خوارزمية برادلي
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: قم بتحويل مستند PDF باستخدام خوارزمية Bradley مع Aspose.PDF لـ .NET.
type: docs
weight: 30
url: /ar/net/programming-with-images/bradley-algorithm/
---
يوضح هذا الدليل خطوة بخطوة كيفية استخدام خوارزمية برادلي مع Aspose.PDF لـ .NET. تأكد من إعداد البيئة الخاصة بك بالفعل واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستندات

قبل البدء، تأكد من تعيين الدليل الصحيح للمستندات. استبدل`"YOUR DOCUMENT DIRECTORY"` في الكود مع المسار إلى الدليل الذي يوجد به مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

 في هذه الخطوة سوف نقوم بفتح مستند PDF باستخدام`Document` فئة Aspose.PDF. استخدم`Document` منشئ ومرر المسار إلى مستند PDF.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## الخطوة 3: تحديد ملفات الإخراج

 قم بتحديد أسماء ملفات الإخراج للصورة الناتجة والصورة الثنائية. استبدل`"resultant_out.tif"` و`"37116-bin_out.tif"` مع الأسماء المطلوبة لملفات الإخراج.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## الخطوة 4: إنشاء كائن الدقة

 إنشاء`Resolution` كائن لتعيين دقة صورة TIFF. في هذا المثال، نستخدم دقة 300 نقطة في البوصة.

```csharp
Resolution resolution = new Resolution(300);
```

## الخطوة 5: إنشاء كائن TiffSettings

 إنشاء`TiffSettings` كائن لتحديد الإعدادات لملف TIFF الناتج. في هذا المثال، نستخدم ضغط LZW وعمق ألوان يبلغ 1 بت لكل بكسل (تنسيق 1 بت لكل بكسل).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## الخطوة 6: إنشاء جهاز TIFF

 إنشاء جهاز TIFF باستخدام`TiffDevice` الكائن، الذي يحدد الدقة وإعدادات TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## الخطوة 7: تحويل الصفحة المحددة وحفظ الصورة

 استخدم`Process` طريقة جهاز TIFF لتحويل صفحة معينة من مستند PDF وحفظ الصورة في ملف TIFF. حدد مسار إخراج الملف.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## الخطوة 8: تحويل الصورة إلى صورة ثنائية باستخدام خوارزمية برادلي

 استخدم`BinarizeBradley`طريقة جهاز TIFF لتحويل الصورة إلى صيغة ثنائية باستخدام خوارزمية برادلي. تأخذ هذه الطريقة تيار إدخال من الصورة الأصلية ودفق إخراج للصورة الثنائية. حدد عتبة التحويل إلى صيغة ثنائية (0.1 في هذا المثال).

```csharp
using (FileStream

  inStream = new FileStream(outputImageFile, FileMode.Open))
{
using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
{
tiffDevice. Binarize Bradley(inStream, outStream, 0.1);
}
}
```

### عينة من كود المصدر لخوارزمية برادلي باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// إنشاء كائن الدقة
Resolution resolution = new Resolution(300);
// إنشاء كائن TiffSettings
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// إنشاء جهاز TIFF
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// تحويل صفحة معينة وحفظ الصورة للبث
tiffDevice.Process(pdfDocument, outputImageFile);
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
	using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
	{
		tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
	}
}
System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```

## خاتمة

تهانينا! لقد أكملت بنجاح عملية التحويل باستخدام خوارزمية برادلي مع Aspose.PDF لـ .NET. يمكنك الآن استخدام الصور الناتجة في مشاريعك أو تطبيقاتك.

### الأسئلة الشائعة

#### س: ما هي خوارزمية برادلي وكيف ترتبط بـ Aspose.PDF لـ .NET؟

ج: خوارزمية برادلي هي تقنية معالجة الصور المستخدمة لتحسين جودة الصورة ووضوحها. يوفر برنامج Aspose.PDF for .NET طريقة ملائمة لتطبيق خوارزمية برادلي على مستندات PDF، مما يؤدي إلى تحسين الصور.

#### س: كيف أقوم بإعداد البيئة الخاصة بي لاستخدام خوارزمية برادلي مع Aspose.PDF لـ .NET؟

ج: قبل أن تبدأ، تأكد من تثبيت Aspose.PDF لـ .NET بشكل صحيح وتكوين بيئة التطوير لديك.

#### س: ما أهمية تحديد دليل المستندات في عملية خوارزمية برادلي؟

أ: يعد تحديد دليل المستند الصحيح أمرًا بالغ الأهمية لضمان وجود مستند PDF في المسار الصحيح للمعالجة.

#### س: كيف أقوم بفتح مستند PDF باستخدام Aspose.PDF لـ .NET في خوارزمية Bradley؟

 أ: استخدم`Document` فئة لفتح مستند PDF، والذي يعمل كمدخل لعملية خوارزمية برادلي.

#### س: ما هو الغرض من تحديد أسماء ملفات الإخراج للصورة والصورة الثنائية في عملية خوارزمية برادلي؟

أ: يتيح لك تحديد أسماء ملفات الإخراج تحديد المكان الذي سيتم فيه حفظ الصورة الناتجة والصورة الثنائية بعد تطبيق خوارزمية برادلي.

#### س: كيف يؤثر إعداد الدقة على جودة صورة TIFF في عملية خوارزمية برادلي؟

أ: يحدد إعداد الدقة مستوى التفاصيل والوضوح في صورة TIFF الناتجة بعد تطبيق خوارزمية برادلي.

#### س: ما هي الإعدادات التي يمكنني تخصيصها لصورة TIFF الناتجة في عملية خوارزمية برادلي؟
ج: يمكنك تخصيص الإعدادات مثل نوع الضغط وعمق اللون لتحقيق النتيجة المطلوبة لصورة TIFF.

#### س: كيف يساهم جهاز TIFF في عملية خوارزمية برادلي؟

ج: يعمل جهاز TIFF كأداة لمعالجة الصور وتطبيق خوارزمية برادلي، مما يؤدي إلى تحسين جودة الصورة.

#### س: كيف أقوم بتحويل صفحة معينة من مستند PDF إلى صورة TIFF في عملية خوارزمية برادلي؟

 أ: استخدم`Process` طريقة جهاز TIFF لتحويل صفحة معينة من مستند PDF إلى صورة TIFF، والتي يمكن معالجتها بعد ذلك باستخدام خوارزمية برادلي.