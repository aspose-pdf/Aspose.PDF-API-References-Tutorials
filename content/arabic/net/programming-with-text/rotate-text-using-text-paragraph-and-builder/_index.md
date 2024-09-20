---
title: تدوير النص باستخدام فقرة النص والمنشئ في ملف PDF
linktitle: تدوير النص باستخدام فقرة النص والمنشئ في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تدوير النص باستخدام فقرة النص ومنشئها في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 410
url: /ar/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---
## مقدمة

 إن إنشاء مستندات PDF ديناميكية يمكن أن يكون طريقة مثيرة لعرض بياناتك وتقاريرك وأفكارك بصريًا. هناك أداة قوية يمكنها مساعدتك في إنجاز هذا بطريقة منظمة وهي Aspose.PDF for .NET. في هذا الدليل، سنستكشف كيفية استخدام Aspose.PDF لتدوير النص داخل ملف PDF باستخدام`TextParagraph` و`TextBuilder` سواء كنت ترغب في إنشاء تقارير مُعلَّقة أو مستندات جذابة بصريًا، فإن إتقان التعامل مع النصوص في ملفات PDF أمر ضروري. هل أنت مستعد لقلب النص رأسًا على عقب - حرفيًا؟ دعنا نبدأ!

## المتطلبات الأساسية

قبل أن نبدأ في مغامرة تدوير النص، هناك بعض الأساسيات التي يجب أن تكون موجودة لديك:

- المعرفة الأساسية بلغة C#: إن الإلمام ببرمجة C# سيجعل التنقل عبر الكود أسهل.
- إعداد Visual Studio: تأكد من تثبيت Visual Studio على جهازك لتتمكن من كتابة التعليمات البرمجية وتشغيلها.
- مكتبة Aspose.PDF: يجب أن يكون لديك مكتبة Aspose.PDF مذكورة في مشروعك. إذا لم تكن قد قمت بتثبيتها بعد، فيمكنك تنزيلها من[هنا](https://releases.aspose.com/pdf/net/).
- .NET Framework: تأكد من أن البيئة الخاصة بك تدعم .NET؛ يمكنك استخدام .NET Framework أو .NET Core حسب احتياجاتك.

الآن بعد أن أصبح لدينا الأساس، دعنا نستورد الحزم اللازمة للبدء في العمل مع ملفات PDF.

## استيراد الحزم

للعمل مع Aspose.PDF لـ .NET، تحتاج إلى استيراد مساحات الأسماء الصحيحة. في الجزء العلوي من ملف C#، أضف التعليمات التالية باستخدام التوجيهات:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
```

ستوفر لك هذه الحزم جميع الفئات التي تحتاجها للتعامل مع النصوص وجوانب المستندات الأخرى بشكل فعال.

الآن بعد أن انتهينا من الإعداد، فلنبدأ في شرح الخطوات الفعلية المتضمنة في تدوير النص داخل مستند PDF. سنبدأ من تهيئة المستند إلى حفظه. استعد!

## الخطوة 1: تهيئة كائن المستند

 الخطوة الأولى هي إنشاء وتشغيل`Document` الكائن. يعمل هذا الكائن كلوحة قماشية ستضيف إليها النص.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تهيئة كائن المستند
Document pdfDocument = new Document();
```

 ال`Document`تُعد الفئة العمود الفقري لملف PDF الخاص بك. فهي تساعد في إدارة الصفحات والمحتويات الموجودة داخلها.

## الخطوة 2: إضافة صفحة

الآن، دعونا نضيف صفحة جديدة إلى مستندنا حيث سيتم وضع النص.

```csharp
// الحصول على صفحة معينة
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

هنا نضيف صفحة جديدة إلى ملف PDF. ستكون هذه الصفحة هي المكان الذي ستعيش فيه فقرات النص الخاصة بنا.

## الخطوة 3: إنشاء فقرات النص وتكوينها

 الآن تبدأ المتعة! سننشئ العديد من`TextParagraph` الكائنات وتكوين خصائصها بما في ذلك موقعها وزاوية دورانها.

```csharp
for (int i = 0; i < 4; i++)
{
    TextParagraph paragraph = new TextParagraph();
    paragraph.Position = new Position(200, 600);
    // تحديد الدوران
    paragraph.Rotation = i * 90 + 45;
}
```

في هذه الحلقة، نقوم بإنشاء أربع فقرات، مع تدوير كل فقرة بمقدار 90 درجة إضافية. يتم وضع كل فقرة في البداية عند الإحداثيات (200، 600).

## الخطوة 4: إنشاء أجزاء نصية

 بعد إعداد الفقرات، حان الوقت لإضافة بعض النصوص! سننشئ`TextFragment` الكائنات التي تحتوي على النص الفعلي الذي نريد عرضه.

```csharp
TextFragment textFragment1 = new TextFragment("Paragraph Text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
```

يمكن تخصيص خصائص كل جزء، مثل حجم الخط ونوع الخط ولون الخلفية ولون المقدمة. نكرر هذه العملية لأجزاء نصية متعددة:

```csharp
TextFragment textFragment2 = new TextFragment("Second line of text");
textFragment2.TextState = ConfigureText("Second line of text");
TextFragment textFragment3 = new TextFragment("And some more text...");
textFragment3.TextState = ConfigureText("And some more text...", true);
```

 الطريقة`ConfigureText`يمكن أن تكون طريقة مساعدة تقوم بإنشائها لتغليف خصائص تصميم النص، وتحسين إعادة استخدام الكود والوضوح.

## الخطوة 5: إضافة أجزاء نصية إلى الفقرات

بعد ذلك، سنقوم بإضافة أجزاء النص إلى فقرتنا. وهذا من شأنه أن يؤدي إلى إنشاء تدفق منظم للنص في الفقرة.

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

 استخدام`AppendLine`، عليك التأكد من إضافة كل جزء من النص عموديًا كخطوط مميزة داخل الفقرة.

## الخطوة 6: إضافة الفقرة إلى صفحة PDF

 الآن بعد أن أصبحت فقرتنا مليئة بالنص، نحتاج إلى وضعها على صفحة PDF باستخدام`TextBuilder` هدف.

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

 وهنا يحدث السحر! فأنت تأخذ الفقرة المعدة وتخبر`TextBuilder` لوضعها على القماش (صفحة PDF) التي قمت بإنشائها مسبقًا.

## الخطوة 7: احفظ المستند

أخيرًا، حان الوقت لإنقاذ عملنا الشاق! حدد الدليل واسم ملف PDF الناتج.

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 في هذا السطر، استبدل`dataDir` مع المسار إلى دليل الإخراج المطلوب. سيتم حفظ ملف PDF باسم "TextFragmentTests_Rotated4_out.pdf".

## خاتمة

والآن لديك دليل كامل حول كيفية تدوير النص في ملف PDF باستخدام Aspose.PDF لـ .NET! الأمر كله يتعلق بتقسيم المهام إلى خطوات يمكن إدارتها، وقبل أن تدرك ذلك، تكون قد حولت ملف PDF الخاص بك إلى مستند ديناميكي يعرض أسلوبك وإبداعك. سواء كنت تقوم بإنشاء التقارير أو إنشاء الدعوات أو مجرد تجربة ترتيبات النصوص، فإن Aspose.PDF يوفر أدوات مرنة لتلبية احتياجاتك. فلماذا الانتظار؟ ابدأ في التجربة وشاهد مدى الإبداع الذي يمكنك الوصول إليه في مستندات PDF الخاصة بك!

## الأسئلة الشائعة

### هل يمكنني تدوير النص في أي اتجاه؟
نعم، يمكنك تحديد أي زاوية دوران (مضاعفات 90 درجة) لتحقيق توجهات مختلفة.

### ماذا لو أردت إضافة الصور بدلاً من النص؟
 يتيح لك Aspose.PDF أيضًا معالجة الصور! يمكنك إضافة الصور باستخدام`Image` الفصول الدراسية بطريقة مماثلة.

### هل Aspose.PDF لـ .NET مجاني؟
 إنه يقدم نسخة تجريبية مجانية، ولكن للاستخدام المستمر، يجب شراء ترخيص. تحقق من[شراء](https://purchase.aspose.com/buy) الصفحة للتفاصيل!

### هل يمكنني الحصول على الدعم لاستخدام Aspose.PDF؟
نعم، يمكنك العثور على الدعم ونشر استفساراتك على[منتدى اسبوس](https://forum.aspose.com/c/pdf/10).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.PDF؟
 يمكنك الحصول على ترخيص مؤقت لأغراض الاختبار من[صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).