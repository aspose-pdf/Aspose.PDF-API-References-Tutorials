---
title: تطبيق نمط الأرقام في ملف PDF
linktitle: تطبيق نمط الأرقام في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تطبيق نمط الترقيم على العناوين في ملف PDF باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-headings/apply-number-style/
---
في هذا البرنامج التعليمي، سوف نرشدك خلال التعليمات البرمجية المصدرية C# خطوة بخطوة لتطبيق نمط الترقيم في ملف PDF باستخدام Aspose.PDF لـ .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل البدء. كما يجب أن يكون لديك معرفة أساسية ببرمجة C#.

### الخطوة 1: إعداد دليل المستندات

في الكود المصدر المقدم، تحتاج إلى تحديد الدليل الذي تريد حفظ ملف PDF الناتج فيه. قم بتغيير المتغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### الخطوة 2: إنشاء مستند PDF

نقوم بإنشاء مستند PDF جديد بأبعاد وهوامش محددة.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### الخطوة 3: إنشاء صفحة وحاوية عائمة

نضيف صفحة إلى المستند وننشئ حاوية عائمة لتنظيم المحتوى.

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### الخطوة 4: إضافة عناوين مع ترقيم

نقوم بإنشاء رؤوس ذات أرقام محددة ونضيفها إلى الحاوية العائمة.

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### الخطوة 5: حفظ مستند PDF

نقوم بحفظ مستند PDF الناتج في الدليل المحدد.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### عينة من كود المصدر لتطبيق نمط الأرقام باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## خاتمة

في هذا البرنامج التعليمي، شرحنا كيفية تطبيق نمط ترقيم على العناوين في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لإنشاء مستندات PDF بترقيم مخصص للعناوين.

### الأسئلة الشائعة حول تطبيق نمط الأرقام في ملف PDF

#### س: ما هو نمط الترقيم في مستند PDF؟

أ: يشير أسلوب الترقيم إلى التنسيق الذي يتم به ترقيم العناوين أو الأقسام في مستند PDF. ويمكن أن يتضمن أرقامًا أو أحرفًا أو أحرفًا أخرى لتوفير هيكل هرمي.

#### س: لماذا أحتاج إلى تطبيق نمط الترقيم على العناوين في مستند PDF؟

أ: يؤدي تطبيق نمط الترقيم على العناوين إلى تحسين قابلية قراءة مستند PDF وتنظيمه. ويساعد القراء على التنقل بسهولة وفهم الهيكل الهرمي للمحتوى.

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET هي مكتبة تتيح للمطورين العمل مع ملفات PDF برمجيًا في تطبيقات .NET. وهي توفر مجموعة واسعة من الميزات لإنشاء مستندات PDF وتحريرها وتحويلها ومعالجتها.

#### س: كيف يمكنني استيراد المكتبات المطلوبة لمشروع C# الخاص بي؟

أ: لاستيراد المكتبات اللازمة لمشروع C# الخاص بك، قم بتضمين توجيهات الاستيراد التالية:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

تتيح لك هذه التوجيهات الوصول إلى الفئات والطرق اللازمة للعمل مع مستندات PDF وتطبيق أنماط الترقيم.

#### س: كيف أحدد الدليل لحفظ ملف PDF الناتج؟

أ: في الكود المصدر المقدم، قم بتعديل المتغير "dataDir" لتحديد الدليل الذي تريد حفظ ملف PDF الناتج فيه.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع مسار الدليل الفعلي.

#### س: كيف أقوم بإنشاء مستند PDF بأبعاد وهوامش محددة؟

أ: لإنشاء مستند PDF بأبعاد وهوامش محددة، استخدم الكود التالي:

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### س: كيف أضيف عناوين ذات نمط ترقيم إلى مستند PDF؟

أ: لإضافة عناوين ذات نمط ترقيم إلى مستند PDF، استخدم عينات التعليمات البرمجية المقدمة لإنشاء عناوين وتخصيص أنماط ترقيمها. اضبط الخصائص مثل النص ونمط الترقيم ورقم البداية والتسلسل التلقائي حسب الحاجة.

#### س: كيف يمكنني حفظ مستند PDF الناتج؟

 أ: لحفظ مستند PDF الناتج، استخدم`Save` طريقة`pdfDoc` هدف:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### س: كيف يمكنني التأكد من أن نمط الترقيم قد تم تطبيقه؟

أ: افتح ملف PDF الناتج للتأكد من تطبيق نمط الترقيم المحدد على العناوين.

#### س: هل يمكنني تخصيص نمط الترقيم بشكل أكبر؟

 ج: نعم، يمكنك تخصيص نمط الترقيم بشكل أكبر عن طريق ضبط خصائص`Heading` الكائنات، مثل نوع نمط الترقيم، ورقم البداية، والتسلسل التلقائي.

#### س: هل يمكنني تطبيق أنماط ترقيم مختلفة على أقسام مختلفة من المستند؟

 ج: نعم، يمكنك تطبيق أنماط ترقيم مختلفة على أقسام مختلفة من المستند عن طريق إنشاء عدة`Heading` الأشياء ذات الأنماط والتسلسلات المختلفة.