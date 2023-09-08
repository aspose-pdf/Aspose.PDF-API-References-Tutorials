---
title: فقرات متعددة الأعمدة في ملف PDF
linktitle: فقرات متعددة الأعمدة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية العمل مع فقرات متعددة الأعمدة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 250
url: /ar/net/programming-with-text/multicolumn-paragraphs/
---
في هذا البرنامج التعليمي، سنشرح كيفية العمل مع الفقرات متعددة الأعمدة في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنخوض عملية خطوة بخطوة لمعالجة الفقرات متعددة الأعمدة والوصول إليها باستخدام كود مصدر C# المقدم.

## متطلبات

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي للبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي يوجد به ملف PDF الذي قمت بإدخاله. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستند PDF

 بعد ذلك، نقوم بتحميل مستند PDF المدخل باستخدام ملف`Document` فئة من مكتبة Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
```

## الخطوة 3: الوصول إلى الفقرات متعددة الأعمدة

 نحن نستخدم ال`ParagraphAbsorber` فئة لاستيعاب وزيارة الفقرات في وثيقة PDF. نقوم بعد ذلك باسترداد علامات الصفحة والوصول إلى الفقرات متعددة الأعمدة.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
PageMarkup markup = absorb.PageMarkups[0];
```

## الخطوة 4: العمل مع الفقرات متعددة الأعمدة

نحن نصل إلى أقسام وفقرات محددة داخل البنية متعددة الأعمدة ونطبع نصها.

```csharp
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");

// الوصول إلى الفقرة الأخيرة في القسم
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// الوصول إلى الفقرة الأولى في القسم
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// تمكين الفقرات متعددة الأعمدة
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");

// الوصول إلى الفقرة الأخيرة في القسم بعد تمكين الفقرات متعددة الأعمدة
section = markup. Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

//الوصول إلى الفقرة الأولى في القسم بعد تمكين الفقرات متعددة الأعمدة
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

### نموذج التعليمات البرمجية المصدر للفقرات متعددة الأعمدة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
PageMarkup markup = absorber.PageMarkups[0];
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");
section = markup.Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية العمل مع فقرات متعددة الأعمدة في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل الموضح خطوة بخطوة وتنفيذ كود C# المقدم، يمكنك الوصول إلى الفقرات متعددة الأعمدة ومعالجتها في مستند PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "الفقرات متعددة الأعمدة في ملف PDF"؟

ج: يوضح البرنامج التعليمي "الفقرات متعددة الأعمدة في ملف PDF" كيفية العمل مع الفقرات متعددة الأعمدة في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. يوفر البرنامج التعليمي دليلاً خطوة بخطوة وكود مصدر C# لمساعدتك في الوصول إلى الفقرات متعددة الأعمدة ومعالجتها.

#### س: لماذا أرغب في العمل مع فقرات متعددة الأعمدة في مستند PDF؟

ج: يتيح لك العمل مع فقرات متعددة الأعمدة إنشاء تخطيطات أكثر تعقيدًا وجاذبية بصريًا لمستندات PDF الخاصة بك. غالبًا ما تُستخدم الفقرات متعددة الأعمدة لتحسين إمكانية القراءة وتحسين العرض العام للمحتوى.

#### س: كيف أقوم بإعداد دليل المستندات؟

ج: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى الدليل حيث يوجد ملف PDF المدخل الخاص بك.

#### س: كيف يمكنني تحميل مستند PDF والوصول إلى فقرات متعددة الأعمدة؟

 ج: في البرنامج التعليمي،`Document` يتم استخدام الفئة لتحميل مستند PDF الإدخال. ال`ParagraphAbsorber` يتم بعد ذلك استخدام الفصل لاستيعاب وزيارة الفقرات الموجودة في مستند PDF. ال`PageMarkup` يتم استخدام الفصل للوصول إلى الفقرات متعددة الأعمدة.

#### س: كيف يمكنني التعامل مع فقرات محددة متعددة الأعمدة؟

 ج: يرشدك البرنامج التعليمي خلال عملية الوصول إلى أقسام وفقرات محددة داخل البنية متعددة الأعمدة باستخدام`MarkupSection` و`MarkupParagraph` الطبقات. ويوضح كيفية طباعة نص هذه الفقرات.

#### س: كيف يمكنني تمكين الفقرات متعددة الأعمدة؟

 ج: لتمكين الفقرات متعددة الأعمدة، يمكنك تعيين`IsMulticolumnParagraphsAllowed` ملكية`PageMarkup` يعترض على`true`.

#### س: ما هو الناتج المتوقع من هذا البرنامج التعليمي؟

ج: بعد اتباع البرنامج التعليمي وتنفيذ كود C# المقدم، ستتمكن من الوصول إلى الفقرات متعددة الأعمدة ومعالجتها في مستند PDF. يوضح البرنامج التعليمي كيفية العمل مع الأقسام والفقرات المختلفة داخل البنية متعددة الأعمدة.

#### س: هل يمكنني تخصيص مظهر الفقرات متعددة الأعمدة؟

ج: يركز هذا البرنامج التعليمي على الوصول إلى محتوى الفقرات متعددة الأعمدة ومعالجتها بدلاً من مظهرها. ومع ذلك، يمكنك استخدام ميزات أخرى في مكتبة Aspose.PDF لتخصيص مظهر مستند PDF الخاص بك، مثل تعيين الخطوط والألوان والأنماط.