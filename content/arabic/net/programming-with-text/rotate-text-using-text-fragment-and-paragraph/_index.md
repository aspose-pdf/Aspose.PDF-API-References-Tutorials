---
title: تدوير النص باستخدام جزء النص والفقرة
linktitle: تدوير النص باستخدام جزء النص والفقرة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تدوير النص باستخدام جزء النص والفقرة في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 400
url: /ar/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET لتدوير النص باستخدام جزء النص والفقرة. يوضح كود مصدر C# المقدم العملية خطوة بخطوة.

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

 إنشاء متعددة`TextFragment` الكائنات، وتعيين نصها وخصائصها، وتحديد زاوية التدوير:

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

اضبط النص وزاوية التدوير والخصائص الأخرى حسب الرغبة.

## الخطوة 6: إضافة أجزاء النص إلى الصفحة

 قم بإضافة أجزاء النص التي تم إنشاؤها إلى الصفحة عن طريق إلحاقها بملف`Paragraphs` مجموعة:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## الخطوة 7: احفظ مستند PDF

 احفظ مستند PDF المعدل في ملف باستخدام الملف`Save` طريقة:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 تأكد من استبدال`"TextFragmentTests_Rotated3_out.pdf"` مع اسم ملف الإخراج المطلوب.

### نموذج التعليمات البرمجية المصدر لتدوير النص باستخدام جزء النص والفقرة باستخدام Aspose.PDF لـ .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تهيئة كائن المستند
Document pdfDocument = new Document();
// الحصول على صفحة معينة
Page pdfPage = (Page)pdfDocument.Pages.Add();
// إنشاء جزء من النص
TextFragment textFragment1 = new TextFragment("main text");
// تعيين خصائص النص
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// إنشاء جزء من النص
TextFragment textFragment2 = new TextFragment("rotated text");
// تعيين خصائص النص
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// ضبط التدوير
textFragment2.TextState.Rotation = 315;
// إنشاء جزء من النص
TextFragment textFragment3 = new TextFragment("rotated text");
// تعيين خصائص النص
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// ضبط التدوير
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// حفظ المستند
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية تدوير النص باستخدام أجزاء النص والفقرات في مستند PDF باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، بدءًا من إنشاء المستند وحتى حفظ النسخة المعدلة. يمكنك الآن دمج هذا الرمز في مشاريع C# الخاصة بك لمعالجة تدوير النص في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "تدوير النص باستخدام جزء النص والفقرة"؟

ج: يهدف البرنامج التعليمي "تدوير النص باستخدام جزء النص والفقرة" إلى إرشادك خلال عملية استخدام مكتبة Aspose.PDF لـ .NET لتدوير النص باستخدام أجزاء النص والفقرات داخل مستند PDF. يوفر البرنامج التعليمي إرشادات خطوة بخطوة ونموذج التعليمات البرمجية لتحقيق هذه الوظيفة.

#### س: كيف يختلف هذا البرنامج التعليمي عن البرامج التعليمية السابقة لتدوير النص؟

ج: يجمع هذا البرنامج التعليمي بين استخدام أجزاء النص والفقرات لتحقيق تدوير النص داخل مستند PDF. ويوضح كيفية تدوير أجزاء النص بشكل فردي ثم إضافتها إلى الصفحة`Paragraphs` المجموعة لتحقيق تأثير دوران النص أكثر شمولاً.

#### س: ما هي مزايا استخدام أجزاء النص والفقرات لتدوير النص؟

ج: يتيح استخدام أجزاء النص والفقرات معًا مزيدًا من المرونة في تدوير النص. تعمل أجزاء النص على تمكين إعدادات التدوير والتنسيق الفردية، بينما توفر الفقرات بنية لترتيب أجزاء النص ووضعها داخل الصفحة.

#### س: هل يمكنني تطبيق زوايا تدوير مختلفة على أجزاء نص مختلفة داخل نفس الفقرة؟

 ج: نعم، يمكنك تطبيق زوايا دوران مختلفة على مختلفة`TextFragment` الكائنات داخل نفس الفقرة. يمكن أن يكون لكل جزء من النص زاوية دوران خاصة به محددة باستخدام`TextState.Rotation` ملكية.

#### س: هل من الممكن تحقيق تأثيرات تدوير النص المعقدة باستخدام هذه الطريقة؟

ج: نعم، من خلال الجمع بين أجزاء النص وزوايا التدوير المختلفة وترتيبها داخل الفقرات، يمكنك تحقيق تأثيرات تدوير النص المعقدة والمخصصة، مما يعزز المظهر المرئي لمستندات PDF الخاصة بك.

#### س: ما هي الخطوات المتبعة في تدوير النص باستخدام أجزاء النص والفقرات؟

ج: الخطوات تشمل:

1. إعداد المشروع عن طريق إنشاء مشروع C# جديد وإضافة مرجع إلى مكتبة Aspose.PDF لـ .NET.
2. إنشاء مستند PDF وإضافة صفحة.
3. إنشاء أجزاء النص وتحديد خصائصها وتحديد زوايا التدوير.
4.  إضافة أجزاء نص إلى الصفحة باستخدام`Paragraphs` مجموعة.
5. حفظ وثيقة PDF المعدلة.

#### س: هل يمكنني تطبيق التدوير على فقرات بأكملها؟

 ج: نعم، يمكنك تطبيق التدوير على فقرات بأكملها عن طريق ضبط الإعداد`TextState.Rotation` خاصية الفقرة نفسها سيؤدي هذا إلى تدوير كافة أجزاء النص داخل تلك الفقرة.