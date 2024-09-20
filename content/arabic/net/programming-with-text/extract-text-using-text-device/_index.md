---
title: استخراج النص باستخدام أداة النص
linktitle: استخراج النص باستخدام أداة النص
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخراج النص من مستند PDF باستخدام جهاز النص في Aspose.PDF لـ .NET.
type: docs
weight: 210
url: /ar/net/programming-with-text/extract-text-using-text-device/
---
## مقدمة

قد يكون استخراج النص من ملف PDF أمرًا صعبًا، وخاصة عند التعامل مع مستندات ذات تنسيقات مختلفة أو خطوط مضمنة أو تخطيطات معقدة. ولكن مع Aspose.PDF لـ .NET، تصبح هذه العملية سهلة للغاية! سواء كنت تريد تحويل صفحات ملف PDF إلى نص عادي لمزيد من التحليل أو كنت بحاجة ببساطة إلى استخراج أقسام معينة، فإن Aspose.PDF يغطيك. في هذا البرنامج التعليمي، سنوضح خطوة بخطوة كيفية استخراج النص من ملف PDF باستخدام فئة TextDevice في Aspose.PDF. وسنقدم أيضًا تفسيرات واضحة، حتى تتمكن من تطبيق نفس الأساليب على مشاريعك الخاصة بسهولة.

## المتطلبات الأساسية

قبل أن ننتقل إلى التعليمات البرمجية، تأكد من أن كل شيء جاهز للمتابعة. إليك ما ستحتاج إليه:

1.  Aspose.PDF لـ .NET: قم بتنزيل أحدث إصدار من[صفحة تنزيل Aspose.PDF لـ .NET](https://releases.aspose.com/pdf/net/).
2. بيئة التطوير: Visual Studio أو أي بيئة تطوير C# أخرى.
3. .NET Framework: تأكد من أن مشروعك يستهدف .NET Framework 4.x أو أعلى.
4. ملف PDF المدخل: ملف PDF الذي ستستخدمه لاستخراج النص. ضع هذا الملف في دليل على جهازك (سنشير إليه باسم`YOUR DOCUMENT DIRECTORY`).

## استيراد الحزم

في الجزء العلوي من الكود الخاص بك، ستحتاج إلى استيراد المساحات الأساسية اللازمة للعمل مع Aspose.PDF:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## الخطوة 1: قم بتحميل مستند PDF الخاص بك

 قبل استخراج النص، نحتاج إلى تحميل مستند PDF إلى الذاكرة. في هذه الخطوة، ستفتح ملف PDF باستخدام Aspose.PDF`Document` سيسمح لك هذا بالوصول إلى كافة الصفحات والمحتوى داخل الملف.

```csharp
// حدد المسار إلى مستند PDF الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

// تحميل مستند PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 هنا، نحن نستخدم`Document pdfDocument = new Document(dataDir + "input.pdf");` لتحميل ملف PDF.`dataDir` يحتوي المتغير على مسار الدليل لملف PDF الخاص بك. سيتيح لنا هذا الوصول إلى المستند بالكامل، مما يسمح لنا بالتنقل عبر الصفحات واستخراج المحتوى.

## الخطوة 2: إعداد منشئ سلسلة لتخزين النصوص

 الآن بعد تحميل المستند، نحتاج إلى طريقة لتخزين النص المستخرج. لهذا، سنستخدم`StringBuilder` الذي يسمح بتسلسل السلسلة بكفاءة.

```csharp
// StringBuilder لحفظ النص المستخرج
StringBuilder builder = new StringBuilder();
```

 نحن نقوم بتهيئة`StringBuilder`مثال، والذي سيجمع النص المستخرج من كل صفحة. إنها طريقة أكثر كفاءة للتعامل مع السلاسل الكبيرة مقارنة بتسلسل السلاسل العادي في حلقة.

## الخطوة 3: التنقل عبر صفحات PDF

 بعد ذلك، ننتقل عبر كل صفحة من مستند PDF لاستخراج النص. وسنقوم بمعالجة كل صفحة على حدة باستخدام`TextDevice` الفئة المسؤولة عن تحويل محتوى PDF إلى تنسيق نصي.

```csharp
// قم بالتنقل عبر جميع الصفحات في ملف PDF
foreach (Page pdfPage in pdfDocument.Pages)
{
    // معالجة كل صفحة لاستخراج النص
}
```

تمر هذه الحلقة عبر كل صفحة من ملف PDF (`pdfDocument.Pages` ). لكل صفحة، سنقوم باستخراج النص وإضافته إلى`StringBuilder`.

## الخطوة 4: استخراج النص من كل صفحة

 الآن، قمنا بإعداد عملية استخراج النص لكل صفحة. هنا، سنقوم بإنشاء`TextDevice` الكائن واستخدامه لمعالجة صفحات PDF.`TextDevice` يستخرج النص الخام أو المنسق استنادًا إلى خيارات الاستخراج التي قمنا بتعيينها.

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    // إنشاء جهاز نصي لاستخراج النص
    TextDevice textDevice = new TextDevice();
    
    // تعيين خيارات استخراج النص إلى الوضع "الخالص"
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    //استخراج النص من الصفحة الحالية وحفظه في مجرى الذاكرة
    textDevice.Process(pdfPage, textStream);

    // تحويل تدفق الذاكرة إلى نص
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    // إضافة النص المستخرج إلى StringBuilder
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();` : ال`TextDevice` يتم استخدام الفئة لاستخراج النص من ملف PDF.
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);` :يستخرج هذا الخيار النص الخام دون الاحتفاظ بأي تنسيق مثل الخطوط أو المواضع. يمكنك أيضًا استخدام`TextFormattingMode.Raw` إذا كنت بحاجة إلى مزيد من التحكم في التنسيق.
- `textDevice.Process(pdfPage, textStream);` :تعمل هذه العملية على معالجة كل صفحة من ملف PDF وتخزين النص المستخرج في`MemoryStream`.
-  وأخيرًا، نقوم بتحويل النص من`MemoryStream` إلى سلسلة وإضافتها إلى`StringBuilder`.

## الخطوة 5: حفظ النص المستخرج في ملف

 بعد معالجة كافة الصفحات، يتم تخزين النص في`StringBuilder`الخطوة الأخيرة هي حفظ هذا النص المستخرج في ملف.

```csharp
// تحديد مسار الإخراج لملف النص
dataDir = dataDir + "input_Text_Extracted_out.txt";

// حفظ النص المستخرج في ملف
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());` :هذا يكتب المحتوى الكامل لـ`StringBuilder` إلى ملف نصي.
- يتم تعيين مسار ملف الإخراج عن طريق إضافة اسم الملف (`"input_Text_Extracted_out.txt"` ) إلى`dataDir` طريق.

## خاتمة

إن استخراج النص من ملف PDF باستخدام Aspose.PDF for .NET هو عملية بسيطة وفعالة. باتباع الخطوات الموضحة في هذا الدليل، يمكنك بسهولة فتح مستندات PDF، والتنقل بين الصفحات، واستخراج النص إلى ملف نصي. وهذا مفيد بشكل خاص لمعالجة كميات كبيرة من بيانات PDF، أو إجراء تحليل نصي، أو تحويل المستندات لمزيد من المعالجة.

مع Aspose.PDF، لن تقتصر قدراتك على استخراج النصوص فحسب، بل يمكنك أيضًا التعامل مع التعليقات التوضيحية، أو معالجة الصور، أو حتى تحويل ملفات PDF إلى تنسيقات أخرى مثل HTML أو Word. إن مرونة وقوة هذه المكتبة تجعلها أداة لا تقدر بثمن لإدارة ملفات PDF في تطبيقات .NET.

## الأسئلة الشائعة

### هل يمكن لـ Aspose.PDF استخراج النص من ملفات PDF القائمة على الصور؟
لا، تم تصميم Aspose.PDF لاستخراج النص من ملفات PDF المستندة إلى المحتوى. بالنسبة لملفات PDF المستندة إلى الصور، هناك حاجة إلى تقنية التعرف الضوئي على الحروف.

### هل يحتفظ Aspose.PDF بالتنسيق عند استخراج النص؟
بشكل افتراضي، يتم استخراج النص دون تنسيق، ولكن يمكنك تعديل خيارات الاستخراج إذا كنت تريد الاحتفاظ ببعض التنسيق.

### هل يمكنني استخراج النص من نطاق صفحة محددة؟
نعم، يمكنك تعديل الكود ليتم تكراره على نطاق محدد من الصفحات بدلاً من جميع الصفحات.

### ما هي أوضاع استخراج النص في Aspose.PDF؟
يوفر Aspose.PDF وضعين: Raw وPure. يحاول الوضع Raw الاحتفاظ بالتخطيط الأصلي، بينما يستخرج الوضع Pure النص فقط دون تنسيق.

### هل Aspose.PDF for .NET متوافق مع .NET Core؟
نعم، Aspose.PDF لـ .NET متوافق تمامًا مع .NET Core و.NET Framework.