---
title: خوارزمية برادلي
linktitle: خوارزمية برادلي
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل مستند PDF باستخدام خوارزمية Bradley مع Aspose.PDF for .NET.
type: docs
weight: 30
url: /ar/net/programming-with-images/bradley-algorithm/
---
يوضح هذا الدليل التفصيلي كيفية استخدام خوارزمية برادلي مع Aspose.PDF لـ .NET. تأكد من قيامك بالفعل بإعداد بيئتك واتبع الخطوات التالية:

## الخطوة 1: تحديد دليل المستند

 قبل أن تبدأ ، تأكد من تعيين الدليل الصحيح للمستندات. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار إلى الدليل حيث يوجد مستند PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

في هذه الخطوة ، سنفتح مستند PDF باستخدام امتداد`Document` فئة Aspose.PDF. استخدم ال`Document` منشئ ومرر المسار إلى وثيقة PDF.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## الخطوة 3: تحديد ملفات الإخراج

 حدد أسماء ملفات الإخراج للصورة الناتجة والصورة الثنائية. يستبدل`"resultant_out.tif"` و`"37116-bin_out.tif"` مع الأسماء المطلوبة لملفات الإخراج.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## الخطوة 4: إنشاء كائن القرار

 إنشاء`Resolution`لتعيين دقة صورة TIFF. في هذا المثال ، نستخدم دقة 300 نقطة في البوصة.

```csharp
Resolution resolution = new Resolution(300);
```

## الخطوة 5: قم بإنشاء كائن TiffSettings

 إنشاء`TiffSettings`لتحديد إعدادات ملف TIFF الناتج. في هذا المثال ، نستخدم ضغط LZW وعمق اللون 1 بت لكل بكسل (تنسيق 1 bpp).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## الخطوة 6: قم بإنشاء جهاز TIFF

 قم بإنشاء جهاز TIFF باستخدام ملف`TiffDevice` كائن ، مع تحديد الدقة وإعدادات TIFF.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## الخطوة 7: قم بتحويل الصفحة المحددة وحفظ الصورة

 استخدم ال`Process` طريقة جهاز TIFF لتحويل صفحة معينة من مستند PDF وحفظ الصورة في ملف TIFF. حدد مسار إخراج الملف.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## الخطوة 8: قم بتكوين صورة ثنائية ثنائية باستخدام خوارزمية برادلي

 استخدم ال`BinarizeBradley` طريقة جهاز TIFF لترميز الصورة باستخدام خوارزمية برادلي. تأخذ هذه الطريقة دفق إدخال من الصورة الأصلية وتدفق إخراج للصورة الثنائية. حدد حد الترميز الثنائي (0.1 في هذا المثال).

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

### عينة من التعليمات البرمجية المصدر لخوارزمية برادلي باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// إنشاء كائن القرار
Resolution resolution = new Resolution(300);
// إنشاء كائن TiffSettings
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// قم بإنشاء جهاز TIFF
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
//قم بتحويل صفحة معينة وحفظ الصورة للدفق
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

تهنئة ! لقد أكملت التحويل بنجاح باستخدام خوارزمية برادلي مع Aspose.PDF لـ .NET. يمكنك الآن استخدام الصور الناتجة في مشاريعك أو تطبيقاتك.

### التعليمات

#### س: ما هي خوارزمية برادلي وما علاقتها بـ Aspose.PDF لـ .NET؟

ج: خوارزمية برادلي هي تقنية لمعالجة الصور تستخدم لتحسين جودة الصورة ووضوحها. يوفر Aspose.PDF for .NET طريقة ملائمة لتطبيق خوارزمية برادلي على مستندات PDF ، مما يؤدي إلى تحسين الصور.

#### س: كيف أقوم بإعداد بيئتي لاستخدام خوارزمية برادلي مع Aspose.PDF لـ .NET؟

ج: قبل أن تبدأ ، تأكد من تثبيت Aspose.PDF for .NET بشكل صحيح وتهيئة بيئة التطوير لديك.

#### س: ما أهمية تحديد دليل المستند في عملية خوارزمية برادلي؟

ج: يعد تحديد دليل المستند الصحيح أمرًا بالغ الأهمية لضمان وجود مستند PDF في المسار الصحيح للمعالجة.

#### س: كيف يمكنني فتح مستند PDF باستخدام Aspose.PDF لـ .NET في خوارزمية Bradley؟

 ج: استخدم ملف`Document` فئة لفتح مستند PDF ، والذي يعمل كمدخل لعملية خوارزمية برادلي.

#### س: ما هو الغرض من تحديد أسماء ملفات الإخراج للصورة والصورة الثنائية في عملية خوارزمية برادلي؟

ج: يتيح لك تحديد أسماء ملفات الإخراج تحديد مكان حفظ الصورة الناتجة والصورة الثنائية بعد تطبيق خوارزمية برادلي.

#### س: كيف يؤثر إعداد الدقة على جودة صورة TIFF في عملية خوارزمية برادلي؟

ج: يحدد إعداد الدقة مستوى التفاصيل والوضوح في صورة TIFF الناتجة بعد تطبيق خوارزمية برادلي.

#### س: ما هي الإعدادات التي يمكنني تخصيصها لإخراج صورة TIFF في عملية خوارزمية برادلي؟
ج: يمكنك تخصيص إعدادات مثل نوع الضغط وعمق اللون لتحقيق الإخراج المطلوب لصورة TIFF.

#### س: كيف يساهم جهاز TIFF في عملية خوارزمية برادلي؟

ج: يعمل جهاز TIFF كأداة لمعالجة الصور وتطبيق خوارزمية برادلي ، مما يؤدي إلى تحسين جودة الصورة.

#### س: كيف يمكنني تحويل صفحة معينة من مستند PDF إلى صورة TIFF في عملية Bradley Algorithm؟

 ج: استخدم ملف`Process` طريقة جهاز TIFF لتحويل صفحة معينة من مستند PDF إلى صورة TIFF ، والتي يمكن معالجتها بعد ذلك باستخدام خوارزمية برادلي.