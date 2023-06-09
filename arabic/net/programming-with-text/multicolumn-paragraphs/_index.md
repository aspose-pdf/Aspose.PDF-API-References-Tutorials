---
title: فقرات متعددة الأعمدة
linktitle: فقرات متعددة الأعمدة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية التعامل مع الفقرات متعددة الأعمدة في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 250
url: /ar/net/programming-with-text/multicolumn-paragraphs/
---

في هذا البرنامج التعليمي ، سنشرح كيفية العمل مع فقرات متعددة الأعمدة في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنمر في عملية خطوة بخطوة لمعالجة الفقرات متعددة الأعمدة والوصول إليها باستخدام الكود المصدري C # المقدم.

## متطلبات

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي لبرمجة C #.

## الخطوة 1: قم بإعداد دليل المستندات

 أولاً ، تحتاج إلى تعيين المسار إلى الدليل حيث يوجد ملف PDF الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى ملف PDF الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستند PDF

 بعد ذلك ، نقوم بتحميل مستند PDF المدخل باستخدام ملف`Document` فئة من مكتبة Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
```

## الخطوة 3: الوصول إلى فقرات متعددة الأعمدة

 نحن نستخدم ال`ParagraphAbsorber` فئة لاستيعاب وزيارة الفقرات في مستند PDF. ثم نقوم باسترداد ترميز الصفحة والوصول إلى الفقرات متعددة الأعمدة.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
PageMarkup markup = absorb.PageMarkups[0];
```

## الخطوة 4: العمل مع فقرات متعددة الأعمدة

نصل إلى أقسام وفقرات محددة داخل هيكل متعدد الأعمدة ونطبع نصوصها.

```csharp
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");

// الوصول إلى آخر فقرة في القسم
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

// الوصول إلى الفقرة الأخيرة في القسم بعد تمكين الفقرات متعددة الأعمدة
section = markup. Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// الوصول إلى الفقرة الأولى في القسم بعد تمكين الفقرات متعددة الأعمدة
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

في هذا البرنامج التعليمي ، تعلمت كيفية العمل مع فقرات متعددة الأعمدة في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل المفصل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك الوصول إلى فقرات متعددة الأعمدة ومعالجتها في مستند PDF.