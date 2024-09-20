---
title: البحث عن النص وإضافة ارتباط تشعبي
linktitle: البحث عن النص وإضافة ارتباط تشعبي
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية البحث عن النص وإضافة ارتباطات تشعبية في ملفات PDF باستخدام Aspose.PDF لـ .NET من خلال البرنامج التعليمي الخاص بنا خطوة بخطوة.
type: docs
weight: 450
url: /ar/net/programming-with-text/search-text-and-add-hyperlink/
---
## مقدمة

هل تبحث عن طريقة ليس فقط لمعالجة ملفات PDF بل وأيضًا لتحسينها عن طريق إدراج ارتباطات تشعبية؟ حسنًا، أنت في المكان الصحيح! باستخدام مكتبة Aspose.PDF القوية لـ .NET، يمكنك البحث عن أنماط النص في مستندات PDF وإضافة ارتباطات تشعبية بسلاسة. تخيل أن لديك مستندًا لا ينقل المعلومات فحسب، بل يربط القراء أيضًا بالموارد ذات الصلة بمجرد النقر فوق رابط. يبدو رائعًا، أليس كذلك؟ في هذا البرنامج التعليمي، سنرشدك خطوة بخطوة حول كيفية البحث عن نص باستخدام التعبيرات العادية وإضافة ارتباطات تشعبية داخل ملفات PDF الخاصة بك. سواء كنت مطورًا متمرسًا أو مبتدئًا، فستجد هذه العملية بسيطة ومجزية.

## المتطلبات الأساسية

قبل أن نتعمق في التفاصيل، دعنا نتأكد من أنك تمتلك كل ما تحتاج إليه لمتابعة الأمر. إليك قائمة مرجعية مفيدة:

- .NET Framework: يجب أن يكون لديك إطار عمل .NET مثبتًا على جهازك (الإصدار 4.0 أو أعلى).
- مكتبة Aspose.PDF لـ .NET: لا تنس تنزيل مكتبة Aspose.PDF وإضافتها إلى مشروعك. يمكنك العثور عليها[هنا](https://releases.aspose.com/pdf/net/).
- IDE: ستحتاج إلى بيئة تطوير متكاملة (IDE) مثل Visual Studio لكتابة وتشغيل التعليمات البرمجية.
- ملف PDF نموذجي: احصل على ملف PDF نموذجي يمكنك من خلاله اختبار الكود. يمكنك إنشاء ملف PDF بسيط أو استخدام أحد المستندات الموجودة لديك.

بمجرد الانتهاء من كل شيء في هذه القائمة، سنكون جاهزين للانطلاق!

## استيراد الحزم

الخطوة الأولى في رحلتنا هي استيراد الحزم اللازمة. وهنا نخبر مشروعنا بالأدوات التي سنستخدمها. وإليك كيفية القيام بذلك:

في ملف C# الخاص بك، ابدأ بتضمين المساحات التالية في الأعلى:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

من خلال استيراد هذه المساحات الاسمية، فإنك تمنح برنامجك إمكانية الوصول إلى جميع الميزات الرائعة التي يقدمها Aspose.PDF.

الآن بعد أن قمنا بإعداد كل شيء، حان وقت البدء في العمل. سنتناول هذا الأمر في سلسلة من الخطوات، لذا اتبعها بعناية!

### الخطوة 1: قم بتعيين دليل المستندات الخاص بك

أولاً، ستحتاج إلى تحديد مكان تخزين ملفات PDF الخاصة بك. عدّل`dataDir` متغير يشير إلى دليل المستند الخاص بك. إليك كيفية القيام بذلك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 تأكد من الاستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي لمستنداتك.

### الخطوة 2: إنشاء TextFragmentAbsorber

 بعد ذلك، نحتاج إلى أداة للعثور على النص الذي نريد ربطه. أدخل`TextFragmentAbsorber`سيساعدنا هذا الرجل الصغير في البحث عن نمط النص المحدد في ملف PDF الخاص بنا.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

هنا، نبحث عن نمط محدد: أربعة أرقام، وشرطة، تليها أربعة أرقام أخرى (مثل رقم الهاتف أو السنة).

### الخطوة 3: تمكين البحث باستخدام التعبيرات العادية

 نحن نستخدم بالفعل تعبيرًا عاديًا للعثور على نمط النص الخاص بنا، ولكننا بحاجة إلى التأكد من`absorber` يعرف أنه تم تمكينه. وهذا أمر بالغ الأهمية لكي يتمكن من البحث بشكل صحيح.

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

### الخطوة 4: تهيئة PdfContentEditor

 الآن بعد أن أصبح لدينا جهاز الامتصاص جاهزًا، نحتاج إلى`PdfContentEditor` للعمل مع ملف PDF الخاص بنا. تتيح لنا هذه الفئة الارتباط بملف PDF الخاص بنا والتلاعب به.

```csharp
PdfContentEditor editor = new PdfContentEditor();
```

### الخطوة 5: ربط ملف PDF المصدر الخاص بك

بعد أن أصبح محرر المحتوى جاهزًا، حان الوقت لربطه بملف PDF الفعلي الذي نريد العمل عليه.

```csharp
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 تأكد من الاستبدال`"SearchRegularExpressionPage.pdf"` مع اسم ملف PDF الخاص بك.

### الخطوة 6: قبول الممتص للصفحة

نحتاج إلى إخبار محررنا بأننا نريد البحث في صفحة معينة من المستند. في هذه الحالة، فلننتقل إلى الصفحة 1.

```csharp
editor.Document.Pages[1].Accept(absorber);
```

### الخطوة 7: الاستعداد للتكرار عبر أجزاء النص

الآن، أصبحنا مستعدين لتكرار كل أجزاء النص التي وجدها الممتص لدينا. وسنقوم بتعديل مظهرها وإعداد ارتباطنا التشعبي.

```csharp
int[] dashArray = { };
String[] LEArray = { };
Color blue = Color.Blue;
```

هنا، نقوم بتعيين بعض المعلمات، مثل لون الرابط التشعبي الخاص بنا.

### الخطوة 8: تكرار كل جزء من النص

بالنسبة لكل جزء نصي يتطابق مع بحثنا، سنقوم بتغيير لونه وإنشاء ارتباط تشعبي. وهذا هو الشكل الذي يبدو عليه:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    Rectangle rect = new Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
    
    editor.CreateWebLink(rect, "http://www.aspose.com، 1، أزرق، اسم الإجراء)؛
    editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
        (float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
```

### الخطوة 9: احفظ ملف PDF المحرر

لقد اقتربنا من الانتهاء! والآن حان الوقت لحفظ التغييرات التي أجريناها في ملف PDF جديد.

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
```

### الخطوة 10: إغلاق المحرر

وأخيرًا، لا تنسَ إغلاق مستندك لتحرير الموارد!

```csharp
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

الآن، قمت للتو بإنشاء ملف PDF يحتوي على رابط تشعبي تم إنشاؤه ديناميكيًا استنادًا إلى نتائج البحث. ما مدى روعة ذلك؟

## خاتمة

والآن، لقد انتهيت! باتباع هذه الخطوات، تكون قد تعلمت كيفية البحث في ملف PDF وإضافة ارتباطات تشعبية باستخدام مكتبة Aspose.PDF for .NET. وهذا من شأنه أن يفتح لك عالمًا من الاحتمالات، خاصة إذا كنت تعمل مع مستندات تتطلب التفاعل. تخيل إضافة ارتباطات إلى الموارد ذات الصلة، أو مواقع الويب المرجعية، أو حتى الصفحات الداخلية - كل هذا باستخدام بضعة أسطر فقط من التعليمات البرمجية!
## الأسئلة الشائعة

### ما هو Aspose.PDF لـ .NET؟  
Aspose.PDF for .NET هي مكتبة تسمح للمطورين بإنشاء مستندات PDF ومعالجتها وإدارتها في تطبيقات .NET.

### كيف يمكنني تنزيل Aspose.PDF لـ .NET؟  
 يمكنك تحميل المكتبة[هنا](https://releases.aspose.com/pdf/net/).

### هل يمكنني تجربة Aspose.PDF مجانًا؟  
 بالتأكيد! يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).

### هل يتوفر الدعم لمنتجات Aspose؟  
 نعم، يمكنك العثور على الدعم ومناقشات المجتمع[هنا](https://forum.aspose.com/c/pdf/10).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.PDF؟  
 يمكنك طلب ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).