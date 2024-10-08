---
title: تعيين معلومات الملف في ملف PDF
linktitle: تعيين معلومات الملف في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تعيين معلومات الملف في مستندات PDF باستخدام Aspose.PDF for .NET من خلال هذا الدليل التفصيلي. يمكنك تحسين ملفات PDF الخاصة بك باستخدام البيانات الوصفية بسهولة.
type: docs
weight: 310
url: /ar/net/programming-with-document/setfileinfo/
---
## مقدمة

عندما يتعلق الأمر بإدارة ملفات PDF، فإن التحكم في بيانات التعريف الخاصة بالمستندات أمر بالغ الأهمية. سواء كنت تبحث عن إضافة معلومات المؤلف أو الكلمات الرئيسية أو حتى سطر الموضوع، فإن Aspose.PDF for .NET يوفر طريقة سلسة لتعيين معلومات الملف في مستندات PDF الخاصة بك. سيرشدك هذا البرنامج التعليمي خلال العملية خطوة بخطوة، مما يضمن فهمك لكل جزء من التعليمات البرمجية أثناء تقدمنا. لذا، استعد للبرمجة، ولنغوص في عالم معالجة ملفات PDF!

## المتطلبات الأساسية

قبل أن نبدأ، هناك بعض الأشياء التي تحتاج إلى وضعها في مكانها:

1. Visual Studio: تأكد من تثبيت Visual Studio على جهازك. هذا هو المكان الذي ستكتب فيه وتنفذ فيه كود .NET الخاص بك.
   
2.  Aspose.PDF لـ .NET: ستحتاج إلى تنزيل مكتبة Aspose.PDF وتثبيتها. يمكنك الحصول عليها من[صفحة تنزيلات Aspose](https://releases.aspose.com/pdf/net/).

3. المعرفة الأساسية بلغة C#: ستساعدك المعرفة ببرمجة C# على فهم مقتطفات التعليمات البرمجية التي سنستخدمها.

4.  ملف PDF: قم بإعداد ملف PDF نموذجي تريد تعديله. في هذا البرنامج التعليمي، سنشير إليه باسم`SetFileInfo.pdf`.

بمجرد إعداد كل ذلك، سنكون مستعدين للانتقال إلى الكود!

## استيراد الحزم

للبدء، تحتاج إلى استيراد الحزم الضرورية التي ستسمح لك بالعمل مع ملفات PDF. في مشروع C# الخاص بك، أضف التعليمات التالية باستخدام أعلى ملف التعليمات البرمجية الخاص بك:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
```

توفر هذه المساحات الأسماء إمكانية الوصول إلى الفئات والطرق اللازمة للتعامل مع مستندات PDF بشكل فعال.

## الخطوة 1: تحديد دليل المستندات

أولاً وقبل كل شيء، عليك تحديد الدليل الذي يوجد به ملف PDF الخاص بك. وهذا أمر بالغ الأهمية لأنك ستفتح الملف من هذا المسار.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 شرح: استبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي للمجلد الذي يحتوي على ملفك`SetFileInfo.pdf`يخبر هذا برنامجك بالمكان الذي يجب أن يبحث فيه عن ملف PDF.

## الخطوة 2: افتح مستند PDF

 بعد ذلك، دعنا نفتح مستند PDF الذي تريد تعديله. يتم ذلك باستخدام`Document` الفئة من مكتبة Aspose.PDF.

```csharp
// فتح المستند
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

 الشرح: هنا، نقوم بإنشاء مثيل جديد لـ`Document`قم بتمرير مسار ملف PDF. سيؤدي هذا إلى تحميل المستند إلى الذاكرة، جاهزًا للتحرير.

## الخطوة 3: إنشاء كائن معلومات المستند

الآن بعد أن فتحنا المستند، نحتاج إلى إنشاء كائن يحمل معلومات المستند.

```csharp
// تحديد معلومات الوثيقة
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

 الشرح:`DocumentInfo` تسمح لنا الفئة بتعيين خصائص بيانات وصفية مختلفة لملف PDF. سيتم استخدام هذا الكائن لتخزين معلومات مثل المؤلف وتاريخ الإنشاء والمزيد.

## الخطوة 4: تعيين بيانات تعريف المستند

 مع`DocumentInfo` بعد أن أصبح الكائن جاهزًا، حان الوقت لملئه بالبيانات الوصفية ذات الصلة. هنا يمكنك تحديد المؤلف وتاريخ الإنشاء والكلمات الرئيسية وتاريخ التعديل والموضوع وعنوان المستند.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

 الشرح: يحدد كل سطر خاصية معينة للمستند. على سبيل المثال،`docInfo.Author` يحدد اسم المؤلف، بينما`docInfo.CreationDate` يحدد تاريخ إنشاء المستند. يمكنك تخصيص هذه القيم حسب الحاجة.

## الخطوة 5: احفظ المستند

بعد تحديد البيانات الوصفية المطلوبة، تكون الخطوة التالية هي حفظ ملف PDF المعدّل. تحتاج إلى تحديد مسار جديد لملف الإخراج.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
// حفظ المستند الناتج
pdfDocument.Save(dataDir);
```

 الشرح: هنا نضيف`_out.pdf` إلى اسم الملف الأصلي لإنشاء ملف جديد للمستند المعدل.`Save` ثم تكتب الطريقة التغييرات في هذا الملف الجديد.

## الخطوة 6: تأكيد التغييرات

أخيرًا، من الأفضل دائمًا التأكد من ضبط المعلومات بشكل صحيح. يمكنك القيام بذلك عن طريق طباعة رسالة نجاح على وحدة التحكم.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

الشرح: يقوم هذا السطر بإخراج رسالة تشير إلى أن الملف تم حفظه بنجاح، بالإضافة إلى المسار إلى الملف الجديد. إنها طريقة بسيطة للتأكد من أن كل شيء سار وفقًا للخطة.

## خاتمة

إن ضبط معلومات الملف في مستندات PDF باستخدام Aspose.PDF for .NET هي عملية بسيطة يمكنها تحسين قابلية استخدام ملفات PDF الخاصة بك بشكل كبير. باتباع هذه الخطوات، يمكنك بسهولة إضافة بيانات وصفية مثل المؤلف وتاريخ الإنشاء والمزيد، مما يجعل مستنداتك أكثر إفادة واحترافية. سواء كنت تقوم بتطوير تطبيقات تولد ملفات PDF أو تحتاج ببساطة إلى إدارة مستنداتك بشكل أفضل، فإن Aspose.PDF يوفر لك الأدوات التي تحتاجها لإنجاز المهمة بكفاءة.

## الأسئلة الشائعة

### ما هو Aspose.PDF لـ .NET؟
Aspose.PDF for .NET هي مكتبة قوية تسمح للمطورين بإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا.

### هل يمكنني استخدام Aspose.PDF مجانًا؟
 نعم، تقدم Aspose إصدارًا تجريبيًا مجانيًا يمكنك استخدامه لتقييم المكتبة. قم بزيارة[صفحة التجربة المجانية](https://releases.aspose.com/) لمزيد من المعلومات.

### أين يمكنني العثور على الوثائق؟
 يمكن العثور على الوثائق الكاملة لـ Aspose.PDF[هنا](https://reference.aspose.com/pdf/net/).

### كيف يمكنني شراء Aspose.PDF؟
 يمكنك شراء ترخيص Aspose.PDF من خلال[صفحة الشراء](https://purchase.aspose.com/buy).

### ماذا لو كنت بحاجة إلى الدعم؟
إذا كان لديك أي أسئلة أو تحتاج إلى مساعدة، يمكنك زيارة[منتدى دعم Aspose](https://forum.aspose.com/c/pdf/10).