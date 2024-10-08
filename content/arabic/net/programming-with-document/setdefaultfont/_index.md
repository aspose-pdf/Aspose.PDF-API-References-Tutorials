---
title: تعيين الخط الافتراضي في ملف PDF
linktitle: تعيين الخط الافتراضي في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تعيين خط افتراضي في ملفات PDF باستخدام Aspose.PDF for .NET من خلال هذا الدليل المفصل. مثالي للمطورين الذين يتطلعون إلى تحسين مستندات PDF.
type: docs
weight: 280
url: /ar/net/programming-with-document/setdefaultfont/
---
## مقدمة

هل سبق لك أن فتحت مستند PDF لتكتشف أن الخطوط مفقودة أو لا يتم عرضها بشكل صحيح؟ قد يكون الأمر محبطًا، أليس كذلك؟ حسنًا، لا تقلق! في هذا البرنامج التعليمي، سنتعمق في كيفية تعيين خط افتراضي في ملف PDF باستخدام Aspose.PDF لـ .NET. تتيح لك هذه المكتبة القوية التعامل مع مستندات PDF بسهولة، وتعيين خط افتراضي هو مجرد واحدة من العديد من الميزات التي تقدمها. لذا، استعد للبدء!

## المتطلبات الأساسية

قبل أن ننتقل إلى الكود، هناك بعض الأشياء التي ستحتاج إلى وضعها في مكانها:

1. Visual Studio: تأكد من تثبيت Visual Studio على جهازك. فهو أفضل بيئة تطوير متكاملة لتطوير .NET.
2.  Aspose.PDF لـ .NET: ستحتاج إلى تنزيل مكتبة Aspose.PDF وتثبيتها. يمكنك العثور عليها[هنا](https://releases.aspose.com/pdf/net/).
3. المعرفة الأساسية بلغة C#: إن القليل من الألفة مع برمجة C# سوف يساعدك بشكل كبير في فهم الأمثلة التي سنغطيها.

## استيراد الحزم

للبدء، ستحتاج إلى استيراد الحزم اللازمة في مشروع C# الخاص بك. إليك كيفية القيام بذلك:

1. افتح مشروع Visual Studio الخاص بك.
2. انقر بزر الماوس الأيمن على مشروعك في مستكشف الحلول وحدد "إدارة حزم NuGet".
3.  بحث عن`Aspose.PDF` وتثبيت الإصدار الأحدث.

بمجرد تثبيت الحزمة، ستكون جاهزًا لبدء الترميز!

## الخطوة 1: إعداد مشروعك

### إنشاء مشروع جديد

أولاً وقبل كل شيء، دعونا ننشئ مشروع C# جديد في Visual Studio:

- افتح Visual Studio وحدد "إنشاء مشروع جديد".
- اختر "تطبيق وحدة التحكم (.NET Core)" ثم انقر فوق "التالي".
-  قم بتسمية مشروعك (على سبيل المثال،`AsposePdfExample`) ثم انقر فوق "إنشاء".

### إضافة باستخدام التوجيهات

 الآن، دعنا نضيف توجيهات الاستخدام الضرورية في الجزء العلوي من ملفك`Program.cs` ملف:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

ستسمح لك هذه التوجيهات بالوصول إلى فئات وطرق Aspose.PDF.

## الخطوة 2: تحميل مستند PDF

### تحديد مسار المستند

بعد ذلك، ستحتاج إلى تحديد المسار إلى مستند PDF الذي تريد العمل عليه. وإليك كيفية القيام بذلك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // استبدل بالدليل الفعلي الخاص بك
string documentName = Path.Combine(dataDir, "input.pdf");
```

 تأكد من الاستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي الذي يقع فيه ملف PDF الخاص بك.

### تحميل المستند

الآن، دعنا نحمل مستند PDF الموجود:

```csharp
using (FileStream fs = new FileStream(documentName, FileMode.Open))
{
    Document document = new Document(fs);
}
```

 يفتح مقتطف التعليمات البرمجية هذا ملف PDF وينشئ`Document` كائن يمكنك التحكم فيه.

## الخطوة 3: تعيين الخط الافتراضي

### إنشاء خيارات حفظ ملف Pdf

 الآن يأتي الجزء المثير! ستحتاج إلى إنشاء مثيل لـ`PdfSaveOptions` لتحديد الخط الافتراضي:

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
```

### حدد اسم الخط الافتراضي

بعد ذلك، ستقوم بتعيين اسم الخط الافتراضي. في هذا المثال، سنستخدم "Arial":

```csharp
pdfSaveOptions.DefaultFontName = "Arial";
```

يخبر هذا السطر Aspose.PDF باستخدام Arial كخط افتراضي لأي نص لا يحتوي على خط محدد.

## الخطوة 4: حفظ المستند

وأخيرًا، حان الوقت لحفظ مستند PDF المعدّل باستخدام الخط الافتراضي الجديد:

```csharp
document.Save(Path.Combine(dataDir, "output_out.pdf"), pdfSaveOptions);
```

 هذا السطر يحفظ المستند كـ`output_out.pdf` في الدليل المحدد.

## خاتمة

والآن، لقد نجحت في تعيين خط افتراضي في ملف PDF باستخدام Aspose.PDF لـ .NET. يمكن لهذه الميزة البسيطة والقوية أن تساعد في ضمان ظهور مستنداتك بالشكل الذي تريده بالضبط، حتى في حالة عدم وجود خطوط. لذا، في المرة القادمة التي تواجه فيها ملف PDF به مشاكل في الخطوط، ستعرف بالضبط ما يجب عليك فعله!

## الأسئلة الشائعة

### ما هو Aspose.PDF لـ .NET؟
Aspose.PDF for .NET هي مكتبة تسمح للمطورين بإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا.

### هل يمكنني استخدام خطوط أخرى غير Arial؟
نعم، يمكنك تحديد أي خط مثبت على نظامك كخط افتراضي.

### هل استخدام Aspose.PDF مجاني؟
يقدم Aspose.PDF نسخة تجريبية مجانية، ولكن للحصول على الوظائف الكاملة، ستحتاج إلى شراء ترخيص.

### أين يمكنني العثور على مزيد من الوثائق؟
 يمكنك العثور على وثائق شاملة[هنا](https://reference.aspose.com/pdf/net/).

### كيف أحصل على الدعم لـ Aspose.PDF؟
 يمكنك الحصول على الدعم من خلال منتدى Aspose[هنا](https://forum.aspose.com/c/pdf/10).