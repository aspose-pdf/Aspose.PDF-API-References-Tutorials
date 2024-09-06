---
title: فقرات متعددة الأعمدة في ملف PDF
linktitle: فقرات متعددة الأعمدة في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية العمل مع فقرات متعددة الأعمدة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 250
url: /ar/net/programming-with-text/multicolumn-paragraphs/
---
في هذا البرنامج التعليمي، سنشرح كيفية التعامل مع الفقرات متعددة الأعمدة في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنتناول عملية معالجة الفقرات متعددة الأعمدة والوصول إليها خطوة بخطوة باستخدام كود المصدر C# المقدم.

## متطلبات

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت مكتبة Aspose.PDF لـ .NET.
- فهم أساسي لبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي يوجد به ملف PDF المدخل. استبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل مستند PDF

 بعد ذلك، نقوم بتحميل مستند PDF المدخل باستخدام`Document` الفئة من مكتبة Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
```

## الخطوة 3: الوصول إلى فقرات متعددة الأعمدة

 نحن نستخدم`ParagraphAbsorber` الصف لاستيعاب وزيارة الفقرات في مستند PDF. ثم نسترد علامات الصفحة ونصل إلى الفقرات متعددة الأعمدة.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
PageMarkup markup = absorb.PageMarkups[0];
```

## الخطوة 4: العمل مع الفقرات متعددة الأعمدة

نقوم بالوصول إلى أقسام وفقرات محددة داخل هيكل الأعمدة المتعددة ونطبع نصها.

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

// تمكين فقرات متعددة الأعمدة
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");

// الوصول إلى الفقرة الأخيرة في القسم بعد تمكين فقرات الأعمدة المتعددة
section = markup. Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// الوصول إلى الفقرة الأولى في القسم بعد تمكين فقرات الأعمدة المتعددة
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

### عينة من كود المصدر للفقرات متعددة الأعمدة باستخدام Aspose.PDF لـ .NET 
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

في هذا البرنامج التعليمي، تعلمت كيفية العمل مع فقرات متعددة الأعمدة في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل خطوة بخطوة وتنفيذ التعليمات البرمجية C# المقدمة، يمكنك الوصول إلى الفقرات متعددة الأعمدة في مستند PDF ومعالجتها.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "فقرات متعددة الأعمدة في ملف PDF"؟

ج: يوضح البرنامج التعليمي "فقرات متعددة الأعمدة في ملف PDF" كيفية العمل مع فقرات متعددة الأعمدة في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. يوفر البرنامج التعليمي دليلاً خطوة بخطوة وكود مصدر C# لمساعدتك في الوصول إلى الفقرات متعددة الأعمدة ومعالجتها.

#### س: لماذا أرغب في العمل مع فقرات متعددة الأعمدة في مستند PDF؟

ج: يتيح لك العمل باستخدام فقرات متعددة الأعمدة إنشاء تخطيطات أكثر تعقيدًا وجاذبية بصريًا لمستندات PDF الخاصة بك. غالبًا ما تُستخدم الفقرات متعددة الأعمدة لتحسين قابلية القراءة وتعزيز العرض العام للمحتوى.

#### س: كيف أقوم بإعداد دليل المستندات؟

أ: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى الدليل الذي يوجد به ملف PDF المدخل الخاص بك.

#### س: كيف أقوم بتحميل مستند PDF والوصول إلى الفقرات متعددة الأعمدة؟

 أ: في البرنامج التعليمي،`Document` يتم استخدام الفئة لتحميل مستند PDF المدخل.`ParagraphAbsorber` يتم بعد ذلك استخدام الفصل لاستيعاب الفقرات الموجودة في مستند PDF وزيارتها.`PageMarkup` يتم استخدام class للوصول إلى فقرات متعددة الأعمدة.

#### س: كيف أتعامل مع فقرات محددة متعددة الأعمدة؟

 أ: يرشدك البرنامج التعليمي خلال عملية الوصول إلى أقسام وفقرات محددة داخل هيكل متعدد الأعمدة باستخدام`MarkupSection` و`MarkupParagraph` الفصول الدراسية. وهو يوضح كيفية طباعة نص هذه الفقرات.

#### س: كيف أقوم بتمكين فقرات متعددة الأعمدة؟

 أ: لتمكين فقرات الأعمدة المتعددة، يمكنك ضبط`IsMulticolumnParagraphsAllowed` ممتلكات`PageMarkup` الاعتراض على`true`.

#### س: ما هي النتيجة المتوقعة من هذا البرنامج التعليمي؟

ج: بعد اتباع البرنامج التعليمي وتنفيذ كود C# المقدم، ستتمكن من الوصول إلى الفقرات متعددة الأعمدة في مستند PDF ومعالجتها. يوضح البرنامج التعليمي كيفية العمل مع أقسام وفقرات مختلفة داخل بنية متعددة الأعمدة.

#### س: هل يمكنني تخصيص مظهر الفقرات متعددة الأعمدة؟

ج: يركز هذا البرنامج التعليمي على الوصول إلى محتوى الفقرات متعددة الأعمدة ومعالجتها بدلاً من مظهرها. ومع ذلك، يمكنك استخدام ميزات أخرى لمكتبة Aspose.PDF لتخصيص مظهر مستند PDF الخاص بك، مثل ضبط الخطوط والألوان والأنماط.