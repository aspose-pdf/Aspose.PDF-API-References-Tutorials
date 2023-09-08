---
title: تقديم الرموز القابلة للاستبدال في ملف PDF
linktitle: تقديم الرموز القابلة للاستبدال في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية عرض الرموز القابلة للاستبدال في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 310
url: /ar/net/programming-with-text/rendering-replaceable-symbols/
---
سنشرح في هذا البرنامج التعليمي كيفية عرض الرموز القابلة للاستبدال في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنتابع عملية إنشاء ملف PDF خطوة بخطوة، وإضافة جزء نص باستخدام علامات السطر الجديد، وتعيين خصائص النص، وتحديد موضع النص، وحفظ ملف PDF باستخدام كود مصدر C# المقدم.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي للبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي تريد حفظ ملف PDF الذي تم إنشاؤه فيه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir`متغير مع المسار إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند وصفحة PDF

 بعد ذلك، نقوم بإنشاء مستند PDF جديد ونضيف إليه صفحة باستخدام الملف`Document` الطبقة و`Page` فئة من مكتبة Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## الخطوة 3: إضافة جزء نص باستخدام علامات السطر الجديد

 نقوم بإنشاء أ`TextFragment`كائن وقم بتعيين نصه ليشمل علامات السطر الجديد (`Environment.NewLine`) لتمثيل أسطر متعددة من النص.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## الخطوة 4: تعيين خصائص جزء النص

يمكننا تعيين خصائص مختلفة لجزء النص إذا رغبت في ذلك، مثل حجم الخط والخط ولون الخلفية ولون المقدمة.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## الخطوة 5: إنشاء فقرة نصية وموضعها

 نقوم بإنشاء أ`TextParagraph` كائن، وإلحاق جزء النص بالفقرة، وتعيين موضع الفقرة على الصفحة.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## الخطوة 6: إضافة فقرة نصية إلى الصفحة

 نقوم بإنشاء أ`TextBuilder` كائن مع الصفحة وإلحاق فقرة النص بمنشئ النص.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## الخطوة 7: احفظ مستند PDF

وأخيرًا، نقوم بحفظ مستند PDF في ملف الإخراج المحدد.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لعرض الرموز القابلة للاستبدال باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// قم بتهيئة TextFragment الجديد بنص يحتوي على علامات السطر الجديد المطلوبة
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// قم بتعيين خصائص جزء النص إذا لزم الأمر
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// إنشاء كائن TextParagraph
TextParagraph par = new TextParagraph();
// إضافة TextFragment جديد إلى الفقرة
par.AppendLine(textFragment);
// ضبط موضع الفقرة
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// إنشاء كائن TextBuilder
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// أضف TextParagraph باستخدام TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية عرض رموز قابلة للاستبدال في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ كود C# المقدم، يمكنك إنشاء ملف PDF وإضافة نص بعلامات السطر الجديد وتعيين خصائص النص ووضع النص على الصفحة وحفظ ملف PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "عرض الرموز القابلة للاستبدال في ملف PDF"؟

ج: يوضح البرنامج التعليمي "عرض الرموز القابلة للاستبدال في ملف PDF" كيفية استخدام مكتبة Aspose.PDF لـ .NET لإنشاء مستند PDF يتضمن رموزًا قابلة للاستبدال. يتم تمثيل هذه الرموز كأجزاء نصية مع علامات الأسطر الجديدة لإنشاء محتوى متعدد الأسطر.

#### س: لماذا أرغب في عرض رموز قابلة للاستبدال في مستند PDF؟

ج: يعد عرض الرموز القابلة للاستبدال مفيدًا عندما تحتاج إلى إنشاء محتوى PDF يتضمن معلومات متغيرة أو خاصة بالمستخدم ديناميكيًا. تعمل هذه الرموز كعناصر نائبة يمكن استبدالها بالبيانات الفعلية أثناء وقت التشغيل، مثل قيم حقل النموذج أو التفاصيل الشخصية.

#### س: كيف أقوم بإعداد دليل المستندات؟

ج: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى الدليل الذي تريد حفظ ملف PDF الذي تم إنشاؤه فيه.

#### س: كيف يمكنني عرض رموز قابلة للاستبدال في مستند PDF باستخدام مكتبة Aspose.PDF؟

ج: يرشدك البرنامج التعليمي خلال العملية خطوة بخطوة:

1.  قم بإنشاء مستند PDF جديد باستخدام`Document` فصل.
2.  أضف صفحة إلى المستند باستخدام`Page` فصل.
3.  إنشاء`TextFragment` كائن بعلامات السطر الجديد (`Environment.NewLine`) لتمثيل محتوى متعدد الأسطر.
4. قم بتخصيص خصائص جزء النص مثل حجم الخط والخط ولون الخلفية ولون المقدمة.
5.  إنشاء`TextParagraph` كائن، وألحق جزء النص به، وقم بتعيين موضع الفقرة على الصفحة.
6.  إنشاء`TextBuilder` كائن مع الصفحة وإلحاق فقرة النص بها.
7. احفظ مستند PDF.

#### س: ما هو الغرض من استخدام علامات السطر الجديد (`Environment.NewLine`) in the text fragment?

 ج: تُستخدم علامات السطر الجديد لإنشاء محتوى متعدد الأسطر داخل جزء نص واحد. باستخدام`Environment.NewLine`، يمكنك الإشارة إلى المكان الذي يجب أن تظهر فيه فواصل الأسطر في النص.

#### س: هل يمكنني تخصيص مظهر الرموز القابلة للاستبدال؟

ج: نعم، يمكنك تخصيص خصائص مختلفة لجزء النص، مثل حجم الخط والخط ولون الخلفية ولون المقدمة. تحدد هذه الخصائص المظهر المرئي للرموز القابلة للاستبدال في مستند PDF.

#### س: كيف أحدد موضع النص في الصفحة؟

 ج: يمكنك ضبط موضع النص عن طريق إنشاء ملف`TextParagraph` الكائن واستخدام`Position` الخاصية لتحديد إحداثيات X وY على الصفحة التي يجب وضع الفقرة فيها.

#### س: ما هي النتيجة المتوقعة من تنفيذ الكود المقدم؟

ج: باتباع البرنامج التعليمي وتشغيل رمز C# المقدم، ستقوم بإنشاء مستند PDF يتضمن رموزًا قابلة للاستبدال. سيتم تمثيل الرموز القابلة للاستبدال على هيئة أجزاء نصية مع علامات السطر الجديد وخصائص مخصصة.

#### س: هل يمكنني استخدام هذا الأسلوب لإنشاء مستندات PDF مخصصة ديناميكيًا؟

ج: نعم، هذا الأسلوب مناسب لإنشاء مستندات PDF بمعلومات مخصصة ديناميكيًا. من خلال استبدال الرموز القابلة للاستبدال بالبيانات الفعلية، يمكنك إنشاء محتوى PDF مخصص لكل مستخدم أو سيناريو.