---
title: تدوير النص باستخدام جزء النص والفقرة
linktitle: تدوير النص باستخدام جزء النص والفقرة
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تدوير النص باستخدام جزء النص والفقرة في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 400
url: /ar/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
يوضح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET لتدوير النص باستخدام شظايا النص والفقرات. يوضح كود المصدر C# المقدم العملية خطوة بخطوة.

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

 إنشاء متعددة`TextFragment` الكائنات، وتعيين نصها وخصائصها، وتحديد زاوية الدوران:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

قم بضبط النص وزاوية الدوران والخصائص الأخرى حسب رغبتك.

## الخطوة 6: إضافة أجزاء نصية إلى الصفحة

 أضف أجزاء النص التي تم إنشاؤها إلى الصفحة عن طريق إلحاقها بـ`Paragraphs` مجموعة:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## الخطوة 7: احفظ مستند PDF

 احفظ مستند PDF المعدّل في ملف باستخدام`Save` طريقة:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 تأكد من الاستبدال`"TextFragmentTests_Rotated3_out.pdf"` مع اسم ملف الإخراج المطلوب.

### عينة من كود المصدر لتدوير النص باستخدام جزء نصي وفقرة باستخدام Aspose.PDF لـ .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تهيئة كائن المستند
Document pdfDocument = new Document();
// الحصول على صفحة معينة
Page pdfPage = (Page)pdfDocument.Pages.Add();
// إنشاء جزء نصي
TextFragment textFragment1 = new TextFragment("main text");
// تعيين خصائص النص
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// إنشاء جزء نصي
TextFragment textFragment2 = new TextFragment("rotated text");
// تعيين خصائص النص
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// ضبط الدوران
textFragment2.TextState.Rotation = 315;
// إنشاء جزء نصي
TextFragment textFragment3 = new TextFragment("rotated text");
// تعيين خصائص النص
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// ضبط الدوران
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// حفظ المستند
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## خاتمة

مبروك! لقد تعلمت بنجاح كيفية تدوير النص باستخدام أجزاء من النص والفقرات في مستند PDF باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، من إنشاء المستند إلى حفظ النسخة المعدلة. يمكنك الآن دمج هذا الكود في مشاريع C# الخاصة بك للتلاعب بتدوير النص في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "تدوير النص باستخدام جزء النص والفقرة"؟

أ: يهدف البرنامج التعليمي "تدوير النص باستخدام شظايا النص والفقرات" إلى إرشادك خلال عملية استخدام مكتبة Aspose.PDF لـ .NET لتدوير النص باستخدام شظايا النص والفقرات داخل مستند PDF. يوفر البرنامج التعليمي تعليمات خطوة بخطوة وعينة من التعليمات البرمجية لتحقيق هذه الوظيفة.

#### س: كيف يختلف هذا البرنامج التعليمي عن دروس تدوير النص السابقة؟

ج: يجمع هذا البرنامج التعليمي بين استخدام أجزاء النص والفقرات لتحقيق تدوير النص داخل مستند PDF. ويوضح كيفية تدوير أجزاء النص بشكل فردي ثم إضافتها إلى الصفحة.`Paragraphs` مجموعة لتحقيق تأثير تدوير النص بشكل أكثر شمولاً.

#### س: ما هي فوائد استخدام أجزاء النص والفقرات لتدوير النص؟

أ: يتيح استخدام أجزاء النص والفقرات معًا مزيدًا من المرونة في تدوير النص. تتيح أجزاء النص إمكانية تدوير النص وإعدادات التنسيق الفردية، بينما توفر الفقرات هيكلًا لترتيب أجزاء النص وتحديد موضعها داخل الصفحة.

#### س: هل يمكنني تطبيق زوايا دوران مختلفة على أجزاء نصية مختلفة ضمن نفس الفقرة؟

 ج: نعم، يمكنك تطبيق زوايا دوران مختلفة على`TextFragment` الكائنات الموجودة ضمن نفس الفقرة. يمكن أن يكون لكل جزء نصي زاوية دوران خاصة به محددة باستخدام`TextState.Rotation` ملكية.

#### س: هل من الممكن تحقيق تأثيرات تدوير النص المعقدة باستخدام هذه الطريقة؟

ج: نعم، من خلال الجمع بين أجزاء النص ذات زوايا الدوران المختلفة وترتيبها داخل الفقرات، يمكنك تحقيق تأثيرات دوران نص معقدة ومخصصة، مما يعزز الجاذبية البصرية لمستندات PDF الخاصة بك.

#### س: ما هي الخطوات المتبعة في تدوير النص باستخدام أجزاء النص والفقرات؟

أ: تشمل الخطوات ما يلي:

1. إعداد المشروع عن طريق إنشاء مشروع C# جديد وإضافة مرجع إلى مكتبة Aspose.PDF for .NET.
2. إنشاء مستند PDF وإضافة صفحة.
3. إنشاء أجزاء نصية، وتعيين خصائصها، وتحديد زوايا الدوران.
4.  إضافة أجزاء نصية إلى الصفحة باستخدام`Paragraphs` مجموعة.
5. حفظ مستند PDF المعدل.

#### س: هل يمكنني تطبيق التدوير على الفقرات بأكملها؟

 ج: نعم، يمكنك تطبيق التدوير على الفقرات بأكملها عن طريق ضبط`TextState.Rotation` خاصية الفقرة نفسها. سيؤدي هذا إلى تدوير جميع أجزاء النص داخل تلك الفقرة.