---
title: عرض الرموز القابلة للاستبدال في ملف PDF
linktitle: عرض الرموز القابلة للاستبدال في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية عرض الرموز القابلة للاستبدال في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 310
url: /ar/net/programming-with-text/rendering-replaceable-symbols/
---
في هذا البرنامج التعليمي، سنشرح كيفية عرض الرموز القابلة للاستبدال في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنتناول العملية خطوة بخطوة لإنشاء ملف PDF، وإضافة جزء نصي مع علامات سطر جديد، وتعيين خصائص النص، وتحديد موضع النص، وحفظ ملف PDF باستخدام كود المصدر C# المقدم.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت مكتبة Aspose.PDF لـ .NET.
- فهم أساسي لبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه. استبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند وصفحة PDF

 بعد ذلك، نقوم بإنشاء مستند PDF جديد وإضافة صفحة إليه باستخدام`Document` الصف و`Page` الفئة من مكتبة Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## الخطوة 3: إضافة جزء من النص باستخدام علامات السطر الجديد

 نحن ننشئ`TextFragment` الكائن وضبط نصه ليشمل علامات السطر الجديد (`Environment.NewLine`) لتمثيل أسطر متعددة من النص.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## الخطوة 4: تعيين خصائص جزء النص

يمكننا تعيين خصائص مختلفة لشظية النص إذا رغبنا في ذلك، مثل حجم الخط، ونوع الخط، ولون الخلفية، ولون المقدمة.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## الخطوة 5: إنشاء فقرة نصية وموضعها

 نحن ننشئ`TextParagraph` الكائن، قم بإضافة جزء النص إلى الفقرة، وقم بتعيين موضع الفقرة على الصفحة.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## الخطوة 6: إضافة فقرة نصية إلى الصفحة

 نحن ننشئ`TextBuilder` قم بإنشاء كائن بالصفحة وأضف فقرة النص إلى منشئ النص.

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

### نموذج لمصدر التعليمات البرمجية لعرض الرموز القابلة للاستبدال باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// تهيئة TextFragment جديدة بنص يحتوي على علامات السطر الجديد المطلوبة
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// تعيين خصائص جزء النص إذا لزم الأمر
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// إنشاء كائن TextParagraph
TextParagraph par = new TextParagraph();
// إضافة جزء نصي جديد إلى الفقرة
par.AppendLine(textFragment);
// تعيين موضع الفقرة
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

في هذا البرنامج التعليمي، تعلمت كيفية عرض الرموز القابلة للاستبدال في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ التعليمات البرمجية C# المقدمة، يمكنك إنشاء ملف PDF وإضافة نص بعلامات سطر جديد وتعيين خصائص النص ووضع النص على الصفحة وحفظ ملف PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "عرض الرموز القابلة للاستبدال في ملف PDF"؟

ج: يوضح البرنامج التعليمي "عرض الرموز القابلة للاستبدال في ملف PDF" كيفية استخدام مكتبة Aspose.PDF لـ .NET لإنشاء مستند PDF يتضمن رموزًا قابلة للاستبدال. يتم تمثيل هذه الرموز على هيئة أجزاء نصية مع علامات سطر جديد لإنشاء محتوى متعدد الأسطر.

#### س: لماذا أرغب في عرض رموز قابلة للاستبدال في مستند PDF؟

أ: يعد عرض الرموز القابلة للاستبدال مفيدًا عندما تحتاج إلى إنشاء محتوى PDF ديناميكيًا يتضمن معلومات متغيرة أو خاصة بالمستخدم. تعمل هذه الرموز كعناصر نائبة يمكن استبدالها ببيانات فعلية أثناء وقت التشغيل، مثل قيم حقول النموذج أو التفاصيل الشخصية.

#### س: كيف أقوم بإعداد دليل المستندات؟

أ: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه.

#### س: كيف يمكنني عرض الرموز القابلة للاستبدال في مستند PDF باستخدام مكتبة Aspose.PDF؟

أ: يرشدك البرنامج التعليمي خلال العملية خطوة بخطوة:

1.  إنشاء مستند PDF جديد باستخدام`Document` فصل.
2.  أضف صفحة إلى المستند باستخدام`Page` فصل.
3.  إنشاء`TextFragment` كائن مع علامات السطر الجديد (`Environment.NewLine`) لتمثيل المحتوى متعدد الأسطر.
4. تخصيص خصائص جزء النص مثل حجم الخط، ولون الخلفية، ولون المقدمة.
5.  إنشاء`TextParagraph` الكائن، وأضف إليه جزءًا من النص، ثم حدد موضع الفقرة على الصفحة.
6.  إنشاء`TextBuilder` قم بربط الكائن بالصفحة وأضف فقرة النص إليها.
7. احفظ مستند PDF.

#### س: ما هو الغرض من استخدام علامات السطر الجديد (`Environment.NewLine`) in the text fragment?

 أ: تُستخدم علامات السطر الجديد لإنشاء محتوى متعدد الأسطر داخل جزء نصي واحد. باستخدام`Environment.NewLine`يمكنك الإشارة إلى مكان حدوث فواصل الأسطر في النص.

#### س: هل يمكنني تخصيص مظهر الرموز القابلة للاستبدال؟

ج: نعم، يمكنك تخصيص خصائص مختلفة لشظية النص، مثل حجم الخط ونوعه ولون الخلفية ولون المقدمة. تحدد هذه الخصائص المظهر المرئي للرموز القابلة للاستبدال في مستند PDF.

#### س: كيف أحدد موضع النص في الصفحة؟

 أ: يمكنك تعيين موضع النص عن طريق إنشاء`TextParagraph` الكائن واستخدامه`Position` الخاصية لتحديد إحداثيات X وY على الصفحة حيث يجب وضع الفقرة.

#### س: ما هي النتيجة المتوقعة من تنفيذ الكود المقدم؟

ج: باتباع البرنامج التعليمي وتشغيل كود C# المقدم، ستتمكن من إنشاء مستند PDF يتضمن رموزًا قابلة للاستبدال. سيتم تمثيل الرموز القابلة للاستبدال على هيئة أجزاء نصية مع علامات سطر جديد وخصائص مخصصة.

#### س: هل يمكنني استخدام هذا النهج لإنشاء مستندات PDF مخصصة بشكل ديناميكي؟

ج: نعم، هذا النهج مناسب لإنشاء مستندات PDF بشكل ديناميكي تحتوي على معلومات مخصصة. من خلال استبدال الرموز القابلة للاستبدال ببيانات فعلية، يمكنك إنشاء محتوى PDF مخصص لكل مستخدم أو سيناريو.