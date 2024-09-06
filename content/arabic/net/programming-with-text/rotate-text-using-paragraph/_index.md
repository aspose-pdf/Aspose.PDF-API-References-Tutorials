---
title: تدوير النص باستخدام الفقرة في ملف PDF
linktitle: تدوير النص باستخدام الفقرة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تدوير النص باستخدام الفقرات في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 380
url: /ar/net/programming-with-text/rotate-text-using-paragraph/
---
يوضح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET لتدوير النص باستخدام الفقرات. يوضح كود المصدر C# المقدم العملية خطوة بخطوة.

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

## الخطوة 5: إنشاء فقرة النص

 إنشاء`TextParagraph` الكائن وتعيين موضعه على الصفحة:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

قم بضبط قيم الموضع وفقًا لمتطلباتك.

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

قم بضبط النص والخصائص الأخرى حسب رغبتك.

## الخطوة 7: إضافة أجزاء نصية إلى الفقرة

 قم بإضافة أجزاء النص التي تم إنشاؤها إلى الفقرة باستخدام`AppendLine` طريقة:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## الخطوة 8: إنشاء TextBuilder وإضافة الفقرة

 إنشاء`TextBuilder` كائن باستخدام`pdfPage` وأضف فقرة النص إلى صفحة PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

## الخطوة 9: احفظ مستند PDF

 احفظ مستند PDF المعدّل في ملف باستخدام`Save` طريقة:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

 تأكد من الاستبدال`"TextFragmentTests_Rotated2_out.pdf"` مع اسم ملف الإخراج المطلوب.

### عينة من كود المصدر لتدوير النص باستخدام الفقرة باستخدام Aspose.PDF لـ .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تهيئة كائن المستند
Document pdfDocument = new Document();
// الحصول على صفحة معينة
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
// إنشاء جزء نصي
TextFragment textFragment1 = new TextFragment("rotated text");
// تعيين خصائص النص
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// ضبط الدوران
textFragment1.TextState.Rotation = 45;
// إنشاء جزء نصي
TextFragment textFragment2 = new TextFragment("main text");
// تعيين خصائص النص
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// إنشاء جزء نصي
TextFragment textFragment3 = new TextFragment("another rotated text");
// تعيين خصائص النص
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// ضبط الدوران
textFragment3.TextState.Rotation = -45;
// إضافة أجزاء النص إلى الفقرة
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// إنشاء كائن TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// قم بإضافة فقرة النص إلى صفحة PDF
textBuilder.AppendParagraph(paragraph);
// حفظ المستند
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## خاتمة

مبروك! لقد تعلمت بنجاح كيفية تدوير النص باستخدام الفقرات في مستند PDF باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، من إنشاء المستند إلى حفظ النسخة المعدلة. يمكنك الآن دمج هذا الكود في مشاريع C# الخاصة بك للتلاعب بتدوير النص في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "تدوير النص باستخدام الفقرة"؟

أ: يهدف البرنامج التعليمي "تدوير النص باستخدام فقرة" إلى إرشادك خلال عملية استخدام مكتبة Aspose.PDF لـ .NET لتدوير النص باستخدام فقرات نصية في مستند PDF. يوفر البرنامج التعليمي تعليمات خطوة بخطوة وعينة من التعليمات البرمجية لتحقيق هذه الوظيفة.

#### س: ماذا نقصد بـ "تدوير النص باستخدام الفقرات"؟

أ: يشير تدوير النص باستخدام الفقرات إلى القدرة على تطبيق التدوير على النص داخل مستند PDF باستخدام فقرات نصية. تتيح لك هذه التقنية توجيه النص بزوايا أو مواضع مختلفة داخل محتوى PDF.

#### س: لماذا أرغب في تدوير النص في مستند PDF؟

أ: يمكن أن يكون تدوير النص في مستند PDF مفيدًا لأغراض مختلفة، مثل التأكيد على محتوى معين، أو إنشاء تصميمات فنية، أو تحسين التخطيط والقدرة على القراءة.

#### س: كيف يمكنني إنشاء مستند PDF جديد؟

 أ: لإنشاء مستند PDF جديد، قم بتهيئة`Document`كائن من مكتبة Aspose.PDF. يمكنك استخدام هذا الكائن لإضافة صفحات ومحتوى إلى ملف PDF.

#### س: كيف أقوم بتدوير النص باستخدام الفقرات؟

أ: لتدوير النص باستخدام الفقرات:

1.  إنشاء`TextParagraph` هدف.
2.  يخلق`TextFragment` الأشياء مع النص المطلوب وزوايا الدوران.
3. إضافة أجزاء النص إلى فقرة النص.
4.  إنشاء`TextBuilder` كائن وإضافة فقرة نصية إلى صفحة PDF محددة.

#### س: هل يمكنني التحكم في زاوية دوران أجزاء النص الفردية؟

 ج: نعم، يمكنك التحكم في زاوية دوران الفرد`TextFragment` الأشياء عن طريق ضبط`TextState.Rotation` الخاصية. تشير القيم الإيجابية إلى الدوران في اتجاه عقارب الساعة، في حين تشير القيم السلبية إلى الدوران عكس اتجاه عقارب الساعة.

#### س: هل يمكنني تطبيق زوايا دوران مختلفة على أجزاء نصية مختلفة ضمن نفس الفقرة؟

 ج: نعم، يمكنك تطبيق زوايا دوران مختلفة على`TextFragment` الكائنات الموجودة ضمن نفس الفقرة عن طريق ضبط`TextState.Rotation` خصائص كل جزء وفقا لذلك.

#### س: كيف أحفظ مستند PDF المُدار؟

أ: لحفظ مستند PDF المُدار، استخدم`Save` طريقة`Document` الكائن وتوفير مسار ملف الإخراج والاسم المطلوب.