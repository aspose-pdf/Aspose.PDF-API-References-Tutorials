---
title: تدوير النص باستخدام جزء النص في ملف PDF
linktitle: تدوير النص باستخدام جزء النص في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تدوير النص باستخدام أجزاء النص في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 390
url: /ar/net/programming-with-text/rotate-text-using-text-fragment/
---
يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET لتدوير النص باستخدام أجزاء النص في ملف PDF. يوضح كود مصدر C# المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل متابعة البرنامج التعليمي، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو استخدام NuGet لتثبيته في مشروعك.

## الخطوة 1: إعداد المشروع

ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

أضف ما يلي باستخدام التوجيهات في بداية ملف C# الخاص بك لاستيراد مساحات الأسماء المطلوبة:

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

 تأكد من استبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 4: إضافة صفحة

 احصل على صفحة معينة من المستند باستخدام`Pages.Add()` طريقة:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## الخطوة 5: إنشاء أجزاء النص

 إنشاء متعددة`TextFragment` الكائنات، وتعيين نصها وخصائصها، وتحديد مواضعها في الصفحة:

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

اضبط النص والمواضع والخصائص الأخرى حسب الرغبة.

## الخطوة 6: إنشاء TextBuilder وإلحاق أجزاء النص

 إنشاء`TextBuilder` كائن باستخدام`pdfPage` وألحق أجزاء النص بصفحة PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## الخطوة 7: احفظ مستند PDF

 احفظ مستند PDF المعدل في ملف باستخدام الملف`Save` طريقة:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 تأكد من استبدال`"TextFragmentTests_Rotated1_out.pdf"` مع اسم ملف الإخراج المطلوب.

### نموذج التعليمات البرمجية المصدر لتدوير النص باستخدام جزء النص باستخدام Aspose.PDF لـ .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تهيئة كائن المستند
Document pdfDocument = new Document();
// الحصول على صفحة معينة
Page pdfPage = (Page)pdfDocument.Pages.Add();
// إنشاء جزء من النص
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// تعيين خصائص النص
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// إنشاء جزء نص مستدير
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// تعيين خصائص النص
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// إنشاء جزء نص مستدير
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// تعيين خصائص النص
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// إنشاء كائن TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// إلحاق جزء النص بصفحة PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// حفظ المستند
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية تدوير النص باستخدام أجزاء النص في مستند PDF باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، بدءًا من إنشاء المستند وحتى حفظ النسخة المعدلة. يمكنك الآن دمج هذا الرمز في مشاريع C# الخاصة بك لمعالجة تدوير النص في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "تدوير النص باستخدام جزء النص"؟

ج: يهدف البرنامج التعليمي "تدوير النص باستخدام جزء النص" إلى إرشادك خلال عملية استخدام مكتبة Aspose.PDF لـ .NET لتدوير النص باستخدام أجزاء النص في مستند PDF. يوفر البرنامج التعليمي إرشادات خطوة بخطوة ونموذج التعليمات البرمجية لتحقيق هذه الوظيفة.

#### س: ما المقصود بـ "تدوير النص باستخدام أجزاء النص"؟

ج: يشير تدوير النص باستخدام أجزاء النص إلى القدرة على تطبيق التدوير على أجزاء النص الفردية داخل مستند PDF باستخدام مكتبة Aspose.PDF. تتيح لك هذه التقنية التحكم في اتجاه النص بزوايا أو مواضع مختلفة داخل محتوى PDF.

#### س: لماذا أرغب في تدوير أجزاء النص في مستند PDF؟

ج: يمكن أن يكون تدوير أجزاء النص في مستند PDF مفيدًا لأغراض متعددة، مثل التركيز على محتوى معين، أو إنشاء تصميمات فنية، أو تحسين التخطيط وسهولة القراءة.

#### س: كيف أقوم بإعداد المشروع للبرنامج التعليمي؟

ج: لإعداد المشروع:

1. قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE).
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.
3. أضف توجيهات الاستخدام الضرورية إلى ملف C# الخاص بك.

#### س: كيف يمكنني إنشاء مستند PDF جديد؟

 ج: لإنشاء مستند PDF جديد، قم بتهيئة ملف`Document`كائن من مكتبة Aspose.PDF. يمكنك استخدام هذا الكائن لإضافة صفحات ومحتوى إلى ملف PDF.

#### س: كيف يمكنني تدوير أجزاء النص باستخدام أجزاء النص؟

ج: لتدوير أجزاء النص باستخدام أجزاء النص:

1.  يخلق`TextFragment` أشياء.
2. قم بتعيين النص وخصائص أجزاء النص.
3. حدد مواضع أجزاء النص على الصفحة.
4.  اضبط زاوية الدوران باستخدام`TextState.Rotation` خاصية أجزاء النص.
5.  إنشاء`TextBuilder`كائن وإلحاق أجزاء النص إلى صفحة PDF.

#### س: هل يمكنني تطبيق زوايا دوران مختلفة على أجزاء نص مختلفة؟

 ج: نعم، يمكنك تطبيق زوايا دوران مختلفة على مختلفة`TextFragment` أشياء. يمكن أن يكون لكل جزء من النص زاوية دوران خاصة به محددة باستخدام`TextState.Rotation` ملكية.

#### س: كيف يمكنني حفظ مستند PDF مع أجزاء النص التي تم تدويرها؟

 ج: لحفظ مستند PDF مع أجزاء نص تم تدويرها، استخدم الملف`Save` طريقة`Document` الكائن وتوفير مسار واسم ملف الإخراج المطلوب.