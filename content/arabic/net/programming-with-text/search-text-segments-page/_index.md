---
title: البحث عن أجزاء النص في صفحة ملف PDF
linktitle: البحث عن أجزاء النص في صفحة ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية البحث عن أجزاء نصية في ملفات PDF باستخدام Aspose.PDF for .NET من خلال هذا الدليل التفصيلي خطوة بخطوة. استخرج النص، وقم بتحليل الأجزاء، والمزيد.
type: docs
weight: 470
url: /ar/net/programming-with-text/search-text-segments-page/
---
## مقدمة

هل تساءلت يومًا عن كيفية تحديد أجزاء نصية معينة داخل مستند PDF باستخدام Aspose.PDF for .NET؟ حسنًا، أنت محظوظ! في هذا الدليل، سنرشدك خلال العملية بتنسيق بسيط خطوة بخطوة. سواء كنت تحاول استخراج المعلومات أو تحليل النص أو مجرد التنقل في تعقيدات معالجة PDF، فإن Aspose.PDF for .NET سيوفر لك ما تحتاجه. دعنا نتعمق في الأمر!

## المتطلبات الأساسية

قبل أن نبدأ، دعونا نتأكد من أنك حصلت على كل ما تحتاجه:

-  Aspose.PDF for .NET: تأكد من تثبيت المكتبة. يمكنك الحصول عليها من[هنا](https://releases.aspose.com/pdf/net/).
- .NET Framework: تأكد من تثبيت .NET على جهازك.
- بيئة التطوير: يوصى باستخدام Visual Studio أو أي بيئة تطوير متكاملة تدعم .NET.
- مستند PDF: ملف PDF الذي ستبحث فيه عن أجزاء النص.

 إذا لم يكن لديك Aspose.PDF لـ .NET بعد، فلا تقلق! يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/) أو شرائه[هنا](https://purchase.aspose.com/buy).

## استيراد الحزم

قبل أن نبدأ في كتابة التعليمات البرمجية، من المهم استيراد الحزم اللازمة إلى مشروعك. يضمن هذا توفر جميع الفئات والطرق المطلوبة لمهام معالجة ملفات PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

بعد أن وضعنا الأساسيات في مكانها، دعنا ننتقل مباشرة إلى الدليل خطوة بخطوة.


## الخطوة 1: تحميل مستند PDF

الخطوة الأولى في هذه العملية هي تحميل ملف PDF إلى البرنامج. بدون مستند محمل، لن يكون هناك ما تبحث عنه، أليس كذلك؟ إليك كيفية القيام بذلك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

- `dataDir` :يحتوي هذا المتغير على المسار إلى ملف PDF الخاص بك. استبدل`"YOUR DOCUMENT DIRECTORY"` مع الدليل الفعلي الذي يتم تخزين ملفك فيه.
- `pdfDocument` :استخدام`Document` الصف، نقوم بتحميل ملف PDF إلى الذاكرة.

## الخطوة 2: إعداد البحث النصي

 الآن بعد أن تم تحميل مستندك، فإن الخطوة التالية هي إنشاء`TextFragmentAbsorber` الكائن الذي يسمح لنا بالبحث عن نص محدد داخل المستند.

```csharp
// إنشاء كائن TextAbsorber للعثور على جميع حالات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

- `TextFragmentAbsorber` :يستخدم هذا الكائن لالتقاط جميع تكرارات النص الذي تبحث عنه. استبدال`"text"` مع النص الفعلي الذي تريد البحث عنه.

## الخطوة 3: قبول الامتصاص لصفحات محددة

قد لا ترغب دائمًا في البحث في مستند PDF بأكمله. في هذا المثال، نقوم بتضييق نطاق البحث إلى صفحة محددة.

```csharp
// قبول الممتص لجميع الصفحات
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

- `pdfDocument.Pages[2]`:يشير هذا إلى أننا نبحث فقط في الصفحة الثانية من المستند. يمكنك تعديل الفهرس لاستهداف صفحات أخرى.
- `Accept()` :هذه الطريقة تسمح بـ`TextFragmentAbsorber` لمعالجة النص داخل الصفحة المحددة.

## الخطوة 4: استخراج أجزاء النص

بعد البحث في الصفحة، نقوم باستخراج أجزاء النص الموجودة إلى مجموعة.

```csharp
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`:تحتوي هذه المجموعة على جميع أجزاء النص التي تم العثور عليها أثناء عملية البحث.

## الخطوة 5: تكرار أجزاء النص واستخراج البيانات

الآن، دعنا ننتقل عبر كل جزء من النص ونستخرج تفاصيله، مثل الموضع والخط واللون.

```csharp
// التنقل عبر الشظايا
foreach (TextFragment textFragment in textFragmentCollection)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        Console.WriteLine("Text : {0} ", textSegment.Text);
        Console.WriteLine("Position : {0} ", textSegment.Position);
        Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
        Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
        Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
        Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
        Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
        Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
        Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
        Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
    }
}
```

- `foreach (TextFragment textFragment in textFragmentCollection)` :نحن نمر عبر كل`TextFragment` في المجموعة.
- `foreach (TextSegment textSegment in textFragment.Segments)`:داخل كل جزء، توجد أجزاء متعددة. ننتقل عبرها لجمع كل المعلومات ذات الصلة.
-  خصائص مختلفة من`textSegment`:وهي تعطينا معلومات مفصلة عن النص، مثل موضعه (X وY)، وتفاصيل الخط، والحجم، واللون.

## الخطوة 6: إخراج النتائج

أخيرًا، بعد استخراج كافة المعلومات، تتم طباعة النتائج في وحدة التحكم. يساعدك هذا على رؤية مكان النص بالضبط وتفاصيل تنسيقه.

فيما يلي عينة من الناتج من أجل الوضوح:

```
Text : text
Position : X: 45.0, Y: 75.0
XIndent : 45.0
YIndent : 75.0
Font - Name : Arial
Font - IsAccessible : True
Font - IsEmbedded : False
Font - IsSubset : False
Font Size : 12.0
Foreground Color : System.Drawing.Color [Black]
```

- يتيح لك هذا الإخراج الموقع الدقيق ومعلومات التنسيق للنص "النص" على الصفحة المحددة.

## خاتمة

والآن، لقد تعلمت للتو كيفية البحث عن أجزاء نصية محددة داخل مستند PDF باستخدام Aspose.PDF for .NET. هذه العملية مفيدة للغاية عند التعامل مع ملفات PDF كبيرة، مما يسمح لك بتحديد النص الرئيسي واستخراجه بكفاءة. سواء كنت تقوم بتحليل البيانات أو استخراج المعلومات أو مجرد التنقل عبر مستند، فإن Aspose.PDF يوفر لك أدوات قوية لإنجاز المهمة.

## الأسئلة الشائعة

### هل يمكنني البحث عن كلمات أو عبارات متعددة؟
 نعم يمكنك تعديل`TextFragmentAbsorber`للبحث عن نص مختلف عن طريق تغيير سلسلة الإدخال.

### هل من الممكن البحث عبر صفحات متعددة؟
 بالتأكيد! يمكنك التنقل عبر جميع الصفحات في ملف PDF عن طريق التكرار`pdfDocument.Pages`.

### كيف أبحث عن نص لا يميز بين الأحرف الكبيرة والصغيرة؟
 يمكنك استخدام`TextSearchOptions` لتفعيل البحث غير الحساس لحالة الأحرف.

### هل يمكنني تعديل النص بعد العثور عليه؟
 نعم، بمجرد تحديد موقع`TextFragment`يمكنك تعديل خصائص النص الخاصة به.

### هل هذه الطريقة قابلة للتطبيق على ملفات PDF المشفرة؟
نعم، بشرط أن تقوم بإلغاء قفل ملف PDF باستخدام كلمة المرور الصحيحة.