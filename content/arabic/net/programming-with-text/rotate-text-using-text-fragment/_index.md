---
title: تدوير النص باستخدام جزء النص في ملف PDF
linktitle: تدوير النص باستخدام جزء النص في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تدوير النص باستخدام أجزاء النص في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 390
url: /ar/net/programming-with-text/rotate-text-using-text-fragment/
---
يوضح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET لتدوير النص باستخدام أجزاء نصية في ملف PDF. يوضح كود المصدر C# المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل المتابعة بالبرنامج التعليمي، تأكد من توفر ما يلي:

- المعرفة الأساسية للغة البرمجة C#.
- تم تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك الحصول عليها من موقع Aspose على الويب أو استخدام NuGet لتثبيتها في مشروعك.

## الخطوة 1: إعداد المشروع

ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات الأساسية الضرورية

أضف التوجيهات التالية في بداية ملف C# الخاص بك لاستيراد المساحات المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## الخطوة 3: إنشاء مستند PDF

 تهيئة`Document` كائن لإنشاء مستند PDF جديد:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 تأكد من الاستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: إضافة صفحة

 احصل على صفحة معينة من المستند باستخدام`Pages.Add()` طريقة:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## الخطوة 5: إنشاء أجزاء نصية

 إنشاء متعددة`TextFragment` الكائنات، وتعيين نصها وخصائصها، وتحديد مواقعها على الصفحة:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

قم بضبط النص والمواضع والخصائص الأخرى حسب رغبتك.

## الخطوة 6: إنشاء TextBuilder وإضافة أجزاء نصية

 إنشاء`TextBuilder` كائن باستخدام`pdfPage` وأضف أجزاء النص إلى صفحة PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## الخطوة 7: احفظ مستند PDF

 احفظ مستند PDF المعدّل في ملف باستخدام`Save` طريقة:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 تأكد من الاستبدال`"TextFragmentTests_Rotated1_out.pdf"` مع اسم ملف الإخراج المطلوب.

### عينة من كود المصدر لتدوير النص باستخدام جزء نصي باستخدام Aspose.PDF لـ .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تهيئة كائن المستند
Document pdfDocument = new Document();
// الحصول على صفحة معينة
Page pdfPage = (Page)pdfDocument.Pages.Add();
// إنشاء جزء نصي
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// تعيين خصائص النص
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// إنشاء جزء نصي مدور
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// تعيين خصائص النص
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// إنشاء جزء نصي مدور
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// تعيين خصائص النص
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// إنشاء كائن TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// إضافة جزء من النص إلى صفحة PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// حفظ المستند
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## خاتمة

مبروك! لقد تعلمت بنجاح كيفية تدوير النص باستخدام أجزاء نصية في مستند PDF باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، من إنشاء المستند إلى حفظ الإصدار المعدل. يمكنك الآن دمج هذا الكود في مشاريع C# الخاصة بك للتلاعب بتدوير النص في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "تدوير النص باستخدام جزء النص"؟

أ: يهدف البرنامج التعليمي "تدوير النص باستخدام شظايا النص" إلى إرشادك خلال عملية استخدام مكتبة Aspose.PDF لـ .NET لتدوير النص باستخدام شظايا النص في مستند PDF. يوفر البرنامج التعليمي تعليمات خطوة بخطوة وعينة من التعليمات البرمجية لتحقيق هذه الوظيفة.

#### س: ماذا يقصد بـ "تدوير النص باستخدام أجزاء النص"؟

أ: يشير تدوير النص باستخدام أجزاء نصية إلى القدرة على تطبيق التدوير على أجزاء نصية فردية داخل مستند PDF باستخدام مكتبة Aspose.PDF. تتيح لك هذه التقنية التحكم في اتجاه النص عند زوايا أو مواضع مختلفة داخل محتوى PDF.

#### س: لماذا أرغب في تدوير أجزاء النص في مستند PDF؟

أ: يمكن أن يكون تدوير أجزاء النص في مستند PDF مفيدًا لأغراض مختلفة، مثل التأكيد على محتوى معين، أو إنشاء تصميمات فنية، أو تحسين التخطيط والقدرة على القراءة.

#### س: كيف أقوم بإعداد المشروع للبرنامج التعليمي؟

أ: لإعداد المشروع:

1. قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.
3. أضف توجيهات الاستخدام الضرورية إلى ملف C# الخاص بك.

#### س: كيف يمكنني إنشاء مستند PDF جديد؟

 أ: لإنشاء مستند PDF جديد، قم بتهيئة`Document`كائن من مكتبة Aspose.PDF. يمكنك استخدام هذا الكائن لإضافة صفحات ومحتوى إلى ملف PDF.

#### س: كيف أقوم بتدوير أجزاء النص باستخدام أجزاء النص؟

أ: لتدوير أجزاء النص باستخدام أجزاء النص:

1.  يخلق`TextFragment` أشياء.
2. تعيين النص وخصائص أجزاء النص.
3. حدد مواضع أجزاء النص على الصفحة.
4.  اضبط زاوية الدوران باستخدام`TextState.Rotation` خصائص أجزاء النص.
5.  إنشاء`TextBuilder`قم بتعديل الكائن وإضافة أجزاء النص إلى صفحة PDF.

#### س: هل يمكنني تطبيق زوايا دوران مختلفة على أجزاء نصية مختلفة؟

 ج: نعم، يمكنك تطبيق زوايا دوران مختلفة على`TextFragment` الأشياء. يمكن أن يكون لكل جزء من النص زاوية دوران خاصة به يتم تحديدها باستخدام`TextState.Rotation` ملكية.

#### س: كيف يمكنني حفظ مستند PDF مع أجزاء النص الدائرية؟

 أ: لحفظ مستند PDF مع أجزاء نصية مدورة، استخدم`Save` طريقة`Document` الكائن وتوفير مسار ملف الإخراج والاسم المطلوب.