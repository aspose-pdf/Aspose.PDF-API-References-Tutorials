---
title: تدوير النص باستخدام الفقرة في ملف PDF
linktitle: تدوير النص باستخدام الفقرة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تدوير النص باستخدام الفقرات في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 380
url: /ar/net/programming-with-text/rotate-text-using-paragraph/
---
يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET لتدوير النص باستخدام الفقرات. يوضح كود مصدر C# المقدم العملية خطوة بخطوة.

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

## الخطوة 5: إنشاء فقرة النص

 إنشاء`TextParagraph` الكائن وتعيين موضعه على الصفحة:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

اضبط قيم الموضع وفقًا لمتطلباتك.

## الخطوة 6: إنشاء وتكوين أجزاء النص

 إنشاء متعددة`TextFragment` الكائنات وتعيين نصها وخصائصها:

```csharp
TextFragment textFragment1 = new TextFragment("rotated text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.Rotation = 45;

TextFragment textFragment2 = new TextFragment("main text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment3 = new TextFragment("another rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = -45;
```

اضبط النص والخصائص الأخرى حسب الرغبة.

## الخطوة 7: إلحاق أجزاء النص بالفقرة

 قم بإلحاق أجزاء النص التي تم إنشاؤها بالفقرة باستخدام`AppendLine` طريقة:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## الخطوة 8: إنشاء TextBuilder وإلحاق الفقرة

 إنشاء`TextBuilder` كائن باستخدام`pdfPage` وإلحاق الفقرة النصية بصفحة PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

## الخطوة 9: احفظ مستند PDF

 احفظ مستند PDF المعدل في ملف باستخدام الملف`Save` طريقة:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

 تأكد من استبدال`"TextFragmentTests_Rotated2_out.pdf"` مع اسم ملف الإخراج المطلوب.

### نموذج التعليمات البرمجية المصدر لتدوير النص باستخدام الفقرة باستخدام Aspose.PDF لـ .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تهيئة كائن المستند
Document pdfDocument = new Document();
// الحصول على صفحة معينة
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
// إنشاء جزء من النص
TextFragment textFragment1 = new TextFragment("rotated text");
// تعيين خصائص النص
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// ضبط التدوير
textFragment1.TextState.Rotation = 45;
// إنشاء جزء من النص
TextFragment textFragment2 = new TextFragment("main text");
// تعيين خصائص النص
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// إنشاء جزء من النص
TextFragment textFragment3 = new TextFragment("another rotated text");
// تعيين خصائص النص
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// ضبط التدوير
textFragment3.TextState.Rotation = -45;
// إلحاق أجزاء النص بالفقرة
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// إنشاء كائن TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// إلحاق الفقرة النصية بصفحة PDF
textBuilder.AppendParagraph(paragraph);
// حفظ المستند
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية تدوير النص باستخدام الفقرات في مستند PDF باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، بدءًا من إنشاء المستند وحتى حفظ النسخة المعدلة. يمكنك الآن دمج هذا الرمز في مشاريع C# الخاصة بك لمعالجة تدوير النص في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "تدوير النص باستخدام الفقرة"؟

ج: يهدف البرنامج التعليمي "تدوير النص باستخدام الفقرة" إلى إرشادك خلال عملية استخدام مكتبة Aspose.PDF لـ .NET لتدوير النص باستخدام فقرات نصية في مستند PDF. يوفر البرنامج التعليمي إرشادات خطوة بخطوة ونموذج التعليمات البرمجية لتحقيق هذه الوظيفة.

#### س: ما المقصود بـ "تدوير النص باستخدام الفقرات"؟

ج: يشير تدوير النص باستخدام الفقرات إلى القدرة على تطبيق التدوير على النص داخل مستند PDF باستخدام فقرات نصية. تتيح لك هذه التقنية توجيه النص بزوايا أو مواضع مختلفة داخل محتوى PDF.

#### س: لماذا أرغب في تدوير النص في مستند PDF؟

ج: يمكن أن يكون تدوير النص في مستند PDF مفيدًا لأغراض متعددة، مثل التركيز على محتوى معين، أو إنشاء تصميمات فنية، أو تحسين التخطيط وسهولة القراءة.

#### س: كيف يمكنني إنشاء مستند PDF جديد؟

 ج: لإنشاء مستند PDF جديد، قم بتهيئة ملف`Document`كائن من مكتبة Aspose.PDF. يمكنك استخدام هذا الكائن لإضافة صفحات ومحتوى إلى ملف PDF.

#### س: كيف يمكنني تدوير النص باستخدام الفقرات؟

ج: لتدوير النص باستخدام الفقرات:

1.  إنشاء`TextParagraph` هدف.
2.  يخلق`TextFragment` الكائنات مع النص المطلوب وزوايا التدوير.
3. إلحاق أجزاء النص بفقرة النص.
4.  إنشاء`TextBuilder` كائن وإلحاق الفقرة النصية بصفحة PDF محددة.

#### س: هل يمكنني التحكم في زاوية تدوير أجزاء النص الفردية؟

 ج: نعم، يمكنك التحكم في زاوية دوران الفرد`TextFragment` الكائنات عن طريق تحديد`TextState.Rotation` ملكية. تشير القيم الإيجابية إلى الدوران في اتجاه عقارب الساعة، بينما تشير القيم السالبة إلى الدوران عكس اتجاه عقارب الساعة.

#### س: هل يمكنني تطبيق زوايا تدوير مختلفة على أجزاء نص مختلفة داخل نفس الفقرة؟

 ج: نعم، يمكنك تطبيق زوايا دوران مختلفة على مختلفة`TextFragment` الكائنات داخل نفس الفقرة عن طريق تعيين`TextState.Rotation` خاصية كل جزء وفقا لذلك.

#### س: كيف يمكنني حفظ مستند PDF الذي تم تدويره؟

ج: لحفظ مستند PDF الذي تم تدويره، استخدم الملف`Save` طريقة`Document` الكائن وتوفير مسار واسم ملف الإخراج المطلوب.