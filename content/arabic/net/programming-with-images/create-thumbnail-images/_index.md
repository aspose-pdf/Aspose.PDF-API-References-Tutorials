---
title: إنشاء صور مصغرة في ملف PDF
linktitle: إنشاء صور مصغرة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: قم بإنشاء صور مصغرة لكل صفحة في ملف PDF الخاص بك بسهولة باستخدام Aspose.PDF for .NET. قم بتحسين تجربة معاينة المستندات الخاصة بك.
type: docs
weight: 100
url: /ar/net/programming-with-images/create-thumbnail-images/
---
## مقدمة

إن إنشاء صور مصغرة لكل صفحة في ملف PDF يمكن أن يكون مفيدًا بشكل لا يصدق لأي شخص يتطلع إلى معاينة المستندات بسرعة دون فتح الملف بالكامل. سواء كنت تقوم ببناء نظام إدارة مستندات أو كنت ترغب ببساطة في تبسيط التنقل عبر مجموعة من ملفات PDF، فإن هذه العملية يمكن أن توفر لك الوقت وتعزز تجربة المستخدم الخاصة بك. اليوم، سنشرح كيفية استخدام Aspose.PDF لـ .NET لإنشاء صور مصغرة تلقائيًا لكل صفحة في ملفات PDF الخاصة بك. لا يتعلق الأمر فقط بالترميز؛ بل يتعلق بتزويدك بالأدوات اللازمة لتبسيط سير عملك وتحسين إمكانية الوصول.

## المتطلبات الأساسية

قبل الغوص في الكود، هناك بعض المتطلبات الأساسية التي ستحتاج إلى الاهتمام بها لضمان إعداد سلس:

1. المعرفة الأساسية بلغة C# أو .NET: ستساعدك المعرفة بالبرمجة بلغة C# على فهم الكود بشكل أفضل أثناء تقدمنا.
2. تم تثبيت Visual Studio: ستحتاج إلى IDE لكتابة وتشغيل التعليمات البرمجية الخاصة بك. يعد Visual Studio خيارًا شائعًا لتطوير .NET.
3. مكتبة Aspose.PDF لـ .NET: تأكد من تثبيت مكتبة Aspose.PDF. يمكنك الحصول عليها من[توثيق Aspose.PDF](https://reference.aspose.com/pdf/net/).
4. ملفات PDF: قم بإعداد بعض ملفات PDF في دليل العمل المخصص لك للاختبار.

هل تريد البدء على الفور؟ رائع! لنبدأ أولاً باستيراد الحزم اللازمة.

## استيراد الحزم

للاستفادة من وظائف Aspose.PDF، يتعين عليك تضمين المساحات ذات الصلة في أعلى ملف C# الخاص بك. وإليك كيفية القيام بذلك:

```csharp
using Aspose.Pdf.Devices;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

يضمن تضمين هذه المساحات الاسمية أنك تتمتع بإمكانية الوصول إلى جميع الفئات والطرق الضرورية في Aspose للعمليات التي سنقوم بتنفيذها.

## الخطوة 1: إعداد دليل المستندات الخاص بك

الخطوة الأولى في عمليتنا هي تحديد المسار إلى دليل المستندات الذي يتم تخزين كافة ملفات PDF فيه. تحتاج إلى إخبار البرنامج بالمكان الذي يبحث فيه عن ملفات PDF تلك. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // استبدله بمسار الدليل الفعلي الخاص بك
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الذي توجد به ملفات PDF. هذه الخطوة بالغة الأهمية لأنه بدون الدليل الصحيح، لن يتمكن برنامجك من العثور على ملفات PDF التي يحتاج إلى معالجتها.

## الخطوة 2: استرداد أسماء ملفات PDF

بعد ذلك، ستحتاج إلى الحصول على أسماء جميع ملفات PDF الموجودة في الدليل. تساعد هذه الخطوة في تكرار كل ملف لاحقًا. 

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

 هنا نستخدم`Directory.GetFiles` طريقة لتصفية واسترجاع ملفات PDF فقط.`*.pdf` تضمن wildcard أننا نحصل على كل ملف PDF في الدليل المحدد. 

## الخطوة 3: قم بالتكرار خلال كل ملف PDF

الآن سوف نستعرض كل ملف قمنا باسترجاعه للتو. بالنسبة لكل ملف PDF، سوف نفتحه وننشئ صورًا مصغرة لصفحاته. 

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
    Document pdfDocument = new Document(fileEntries[counter]);
}
```

 في هذه الحلقة،`counter` يتتبع الملف الذي نعمل عليه.`Document` يتم استخدام الفئة لفتح كل ملف PDF. ستتعامل مع كل ملف PDF على حدة لإنشاء صور مصغرة من صفحاته.

## الخطوة 4: إنشاء صور مصغرة لكل صفحة

لكل صفحة في ملف PDF، سنقوم بإنشاء صورة مصغرة. دعنا نوضح هذا الجزء خطوة بخطوة.

### الخطوة 4.1: تهيئة تدفق الملفات لكل صورة مصغرة

داخل حلقتنا، سنحتاج إلى إعداد مجرى سيتم فيه حفظ الصورة المصغرة.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
{
```

 هنا، نقوم بإنشاء ملف JPG جديد لكل صورة مصغرة باستخدام`FileStream`يتضمن اسم الملف العداد حتى تحصل كل صورة مصغرة على اسم فريد.

### الخطوة 4.2: تحديد الدقة

بعد ذلك، نحتاج إلى تحديد دقة الصور المصغرة. تؤدي الدقة العالية إلى الحصول على صور أكثر وضوحًا، ولكنها قد تؤدي أيضًا إلى زيادة حجم الملف.

```csharp
Resolution resolution = new Resolution(300);
```

الدقة التي تبلغ 300 نقطة في البوصة هي المعيار للصور عالية الجودة. لا تتردد في تعديل هذه القيمة وفقًا لاحتياجاتك.

### الخطوة 4.3: إعداد JpegDevice

 الآن، سنقوم بإعداد`JpegDevice` والتي سيتم استخدامها لتحويل صفحات PDF إلى صور.

```csharp
JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
```

هنا، نحدد أبعاد الصور المصغرة والجودة. في هذه الحالة، قمنا بتعيين الأبعاد على 45×59 بكسل ولكن يمكننا تعديل هذه القيم وفقًا لما هو مطلوب لتطبيقك.

### الخطوة 4.4: معالجة كل صفحة

وبعد أن أصبح كل شيء في مكانه، يمكننا الآن معالجة كل صفحة من ملف PDF وحفظ الصورة المصغرة الناتجة في مجرى البيانات الخاص بنا.

```csharp
jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
```

 يأخذ هذا الخط الصفحة المحددة من ملف PDF ويعالجها بتنسيق JPEG، ويرسلها مباشرة إلى`imageStream`حيث سنخزن الصورة المصغرة.

### الخطوة 4.5: إغلاق البث

أخيرًا، بعد معالجة كل صفحة، نحتاج إلى إغلاق البث لتحرير الموارد.

```csharp
imageStream.Close();
```

يعد إغلاق الدفق ضروريًا لمنع تسرب الذاكرة والتأكد من كتابة كافة التغييرات على القرص بشكل صحيح.

## خاتمة

إن إنشاء صور مصغرة لملفات PDF يمكن أن يحسن بشكل كبير من كيفية تفاعل المستخدمين مع مستنداتك. باستخدام Aspose.PDF for .NET، من السهل والفعال إنشاء هذه الصور المصغرة برمجيًا، مما يوفر لك الوقت والجهد. اتبع هذا الدليل، وستكون مجهزًا جيدًا لدمج الصور المصغرة لملفات PDF في مشاريعك!

## الأسئلة الشائعة

### ما هو Aspose.PDF؟  
Aspose.PDF هي مكتبة قوية للعمل مع مستندات PDF في تطبيقات .NET، مما يسمح بإنشائها وتحريرها وتحويلها.

### هل مكتبة Aspose.PDF مجانية؟  
 Aspose.PDF هو منتج تجاري، ولكن يمكنك تنزيل نسخة تجريبية مجانية من موقعهم[موقع إلكتروني](https://releases.aspose.com/).

### هل يمكنني تخصيص أبعاد الصورة المصغرة؟  
نعم، يمكنك تغيير معلمات العرض والارتفاع في منشئ JpegDevice لضبط أحجام الصور المصغرة.

### هل هناك أي اعتبارات تتعلق بالأداء عند تحويل ملفات PDF كبيرة الحجم؟  
نعم، قد تستغرق الملفات الأكبر حجمًا وقتًا أطول للمعالجة اعتمادًا على الدقة وعدد الصفحات؛ ويمكن أن يساعد تحسين هذه المعلمات في تحسين الأداء.

### أين يمكنني العثور على المزيد من الموارد والدعم؟  
 يمكنك العثور على المزيد من الموارد ودعم المجتمع على[منتديات اسبوس](https://forum.aspose.com/c/pdf/10).