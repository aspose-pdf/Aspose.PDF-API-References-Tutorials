---
title: البحث عن النص ورسم المستطيل
linktitle: البحث عن النص ورسم المستطيل
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعلم كيفية البحث عن نص في ملفات PDF وتسليط الضوء عليه باستخدام المستطيلات باستخدام Aspose.PDF for .NET! برنامج تعليمي سهل خطوة بخطوة لتحسين مهارات التعامل مع ملفات PDF.
type: docs
weight: 460
url: /ar/net/programming-with-text/search-text-and-draw-rectangle/
---
## مقدمة

هل تبحث عن تحسين مهاراتك في التعامل مع ملفات PDF؟ هل تريد أن تتعلم كيفية البحث عن نص معين في ملفات PDF وتمييزه بمستطيل؟ لقد وصلت إلى الدليل المثالي! اليوم، سأشرح لك كيفية استخدام Aspose.PDF for .NET للبحث عن نص في مستند PDF ورسم مستطيلات حوله. ستوفر هذه المقالة برنامجًا تعليميًا خطوة بخطوة مصممًا بوضوح وفائدة، مما يضمن لك القدرة على متابعة هذه التقنيات وتطبيقها على مشاريعك. 

## المتطلبات الأساسية

قبل التعمق في البرنامج التعليمي، دعنا نجهز ما تحتاجه لضمان سير العمل بسلاسة:

1. الفهم الأساسي لـ .NET: يجب أن تكون على دراية ببرمجة C# وإطار عمل .NET لمتابعة هذا البرنامج التعليمي بشكل فعال.
   
2. تثبيت Visual Studio: ستحتاج إلى بيئة تطوير متكاملة (IDE) لكتابة واختبار التعليمات البرمجية الخاصة بك. يعد Visual Studio Community خيارًا رائعًا، وهو مجاني.
   
3. Aspose.PDF for .NET: يجب أن يكون لديك مكتبة Aspose.PDF مثبتة في مشروعك. يمكنك تنزيلها[هنا](https://releases.aspose.com/pdf/net/) أو النظر في[رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) للحصول على ميزات موسعة.
   
4.  نموذج مستند PDF: لهذا البرنامج التعليمي، ستحتاج إلى ملف PDF نموذجي باسم`SearchAndGetTextFromAll.pdf` تم تخزينها في دليل المشروع الخاص بك. 

## استيراد الحزم

للبدء، ستحتاج أولاً إلى استيراد الحزم اللازمة إلى مشروع .NET الخاص بك. اتبع الخطوات التالية:

### افتح برنامج Visual Studio

قم بتشغيل Visual Studio وإنشاء تطبيق وحدة تحكم جديد أو استخدم تطبيقًا موجودًا حيث تريد تنفيذ وظائف PDF.

### أضف Aspose.PDF إلى مشروعك

1. انقر بزر الماوس الأيمن على مشروعك في مستكشف الحلول.
2. حدد "إدارة حزم NuGet".
3.  بحث عن`Aspose.PDF` وتثبيت الإصدار الأحدث.

من خلال القيام بذلك، فإنك تضع الأساس لجميع عمليات التلاعب المذهلة بملفات PDF التي أنت على وشك القيام بها.

## استيراد مساحات الأسماء

في الجزء العلوي من ملف البرنامج الخاص بك، قد ترغب في استيراد المساحات ذات الصلة من مكتبة Aspose:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

يجعل هذا من الأسهل الوصول إلى الفئات والطرق داخل مكتبة Aspose.PDF لمهامك.


الآن بعد أن قمت بإعداد كل شيء، دعنا نقوم بتقسيم عملية البحث عن نص في ملف PDF ورسم مستطيل حوله إلى خطوات قابلة للإدارة.

## الخطوة 1: تعيين المسار للمستند الخاص بك

 أولاً، قم بتعيين المسار إلى ملف PDF الخاص بك. تأكد من استبدال`YOUR DOCUMENT DIRECTORY` مع المسار الفعلي الذي تريده`SearchAndGetTextFromAll.pdf` يتم تخزينها.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

 بعد ذلك، قم بإنشاء مثيل لـ`Document` الفئة لتحميل ملف PDF الخاص بك:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

يفتح هذا السطر من التعليمات البرمجية ملف PDF المحدد، مما يسمح لك بمعالجته بشكل أكبر.

## الخطوة 3: إنشاء ممتص نص

 الآن، ستحتاج إلى طريقة للبحث عن نص داخل هذا المستند. ولهذا، نستخدم`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 التعبير العادي`@"[\S]+"` تم تصميمه ليتوافق مع أي سلسلة غير مسافات بيضاء في ملف PDF. 

## الخطوة 4: تكوين خيارات البحث النصي

بعد ذلك، يجب عليك إعداد خيارات البحث النصي:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

 هنا،`true` تعني المعلمة أن البحث سيكون حساسًا لحالة الأحرف. يمكنك ضبطه على`false` إذا كنت تريد بحثًا لا يراعي حالة الأحرف.

## الخطوة 5: قبول خاصية امتصاص النص في المستند

 معك`TextFragmentAbsorber` والآن بعد أن أصبحت خيارات البحث جاهزة، حان الوقت لاستيعاب النص من المستند:

```csharp
document.Pages.Accept(textAbsorber);
```

تقوم هذه الطريقة بفحص كل صفحة في ملف PDF الخاص بك للعثور على أجزاء النص التي تطابق النمط المحدد.

## الخطوة 6: إنشاء محرر محتوى Pdf

 لرسم الأشكال على المستند، ستحتاج إلى`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

يسمح لك هذا المحرر بالتعامل مع محتوى PDF وتحريره بسهولة.

## الخطوة 7: تكرار أجزاء النص التي تم العثور عليها

الآن، قد ترغب في المرور عبر أجزاء النص التي تم العثور عليها لرسم مستطيلات حولها:

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

 تتكرر هذه الحلقة على كل جزء من النص وأجزائه، وتستدعي`DrawBox` طريقة رسم المستطيل.

## الخطوة 8: تحديد طريقة DrawBox

 يجب عليك تحديد`DrawBox` الطريقة التي ستتعامل مع منطق رسم المستطيل. فيما يلي تنفيذ بسيط:

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // حساب أبعاد المستطيل بناءً على مقطع النص
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // ارسم مستطيلاً باستخدام القيم المحسوبة
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

تحدد هذه الطريقة موضع وحجم المستطيل بناءً على المستطيل المحيط بالجزء وتستخدم المحرر لرسمه.

## الخطوة 9: حفظ المستند المعدل

بعد رسم المستطيلات حول النص الموجود، يمكنك حفظ المستند المعدل:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

تأكد من حفظ الملف الجديد باسم مميز لتجنب الكتابة فوق المستند الأصلي.

## الخطوة 10: رسالة التأكيد

وأخيرًا، قم بطباعة رسالة تأكيد على وحدة التحكم لإعلامك بنجاح العملية:

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

وها أنت ذا! لقد نجحت في إنشاء نص للبحث عن نص في ملف PDF وتمييزه باستخدام المستطيلات.

## خاتمة

تهانينا! لقد تمكنت للتو من فتح مهارة قوية يمكنها تعزيز قدراتك على التعامل مع ملفات PDF باستخدام Aspose.PDF for .NET. من خلال بضع خطوات بسيطة، يمكنك البحث عن أي نص في مستندك وتمييزه بصريًا، مما يجعل مستندات PDF الخاصة بك أكثر تفاعلية وسهولة في الإدارة. لا تتردد في تجربة أنماط تعبيرات عادية وخيارات ألوان مختلفة لجعل هذه الأداة خاصة بك حقًا!

## الأسئلة الشائعة

### ما هو Aspose.PDF لـ .NET؟
Aspose.PDF for .NET هي مكتبة توفر طريقة شاملة لإنشاء مستندات PDF ومعالجتها وتحويلها برمجيًا.

### هل يمكنني استخدام Aspose.PDF مجانًا؟
نعم، تقدم Aspose نسخة تجريبية مجانية يمكنك استخدامها لاختبار وظائف المكتبة. تحقق من ذلك[هنا](https://releases.aspose.com/).

### ما هي لغة البرمجة التي أحتاج إلى استخدامها مع Aspose.PDF لـ .NET؟
تم تصميم Aspose.PDF لـ .NET لاستخدامه مع C# ولغات .NET الأخرى.

### كيف أحصل على المساعدة مع Aspose.PDF؟
 يمكنك زيارة منتدى دعم Aspose للحصول على المساعدة بشأن أي مشكلة أو استفسار قد يكون لديك. ابحث عن الدعم[هنا](https://forum.aspose.com/c/pdf/10).

### أين يمكنني تنزيل Aspose.PDF لـ .NET؟
 يمكنك تنزيل المكتبة من موقع Aspose،[هنا](https://releases.aspose.com/pdf/net/).