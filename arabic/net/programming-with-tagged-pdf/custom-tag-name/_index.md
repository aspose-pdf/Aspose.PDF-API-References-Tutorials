---
title: اسم العلامة المخصصة
linktitle: اسم العلامة المخصصة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لاستخدام اسم علامة مخصصة مع Aspose.PDF for .NET. قم بتحسين بنية ملفات PDF الخاصة بك باستخدام علامات مخصصة.
type: docs
weight: 90
url: /ar/net/programming-with-tagged-pdf/custom-tag-name/
---
في هذا الدليل المفصل خطوة بخطوة ، سنرشدك إلى كيفية استخدام اسم علامة مخصصة مع Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تتيح لك معالجة مستندات PDF برمجيًا. يتيح لك استخدام العلامات المخصصة إضافة معلومات هيكلية محددة إلى مستند PDF الخاص بك ، مما يسهل استخدامه والوصول إليه.

دعنا نتعمق في الكود ونتعلم كيفية استخدام اسم علامة مخصصة مع Aspose.PDF for .NET.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

1. تثبيت مكتبة Aspose.PDF لـ .NET.
2. معرفة أساسية بلغة البرمجة C #.

## الخطوة الأولى: تهيئة البيئة

للبدء ، افتح بيئة التطوير C # وأنشئ مشروعًا جديدًا. تأكد من إضافة مرجع إلى مكتبة Aspose.PDF لـ .NET في مشروعك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء المستند

 تتمثل الخطوة الأولى في إنشاء مستند PDF جديد باستخدام امتداد`Document` فصل.

```csharp
// قم بإنشاء مستند PDF
Document document = new Document();
```

## الخطوة 3: العمل مع المحتوى الذي تم وضع علامة عليه

ثم نحصل على محتوى المستند الذي تم وضع علامة عليه للعمل معه.

```csharp
// احصل على محتوى المستند بعلامات
ITaggedContent taggedContent = document.TaggedContent;
```

## الخطوة 4: حدد عنوان المستند ولغته

يمكننا الآن تعيين عنوان المستند ولغته.

```csharp
// حدد عنوان المستند ولغته
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## الخطوة 5: إنشاء عناصر البنية المنطقية

لنقم الآن بإنشاء بعض عناصر البنية المنطقية لتنظيم المحتوى الخاص بنا.

```csharp
// إنشاء عناصر هيكلية منطقية
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1.");
p2.SetText("P2.");
p3.SetText("P3.");
p4.SetText("P4.");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);
```

نحن هنا ننشئ عناصر فقرة ونمتد العناصر لمحتوانا ، ونخصص علامات مخصصة لها.

## الخطوة 6: احفظ مستند PDF الذي تم وضع علامة عليه

أخيرًا ، نقوم بحفظ مستند PDF الموسوم.

```csharp
// احفظ مستند PDF بعلامات
document.Save(dataDir + "CustomTag.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Custom Tag Name باستخدام Aspose.PDF لـ .NET 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مستند PDF
Document document = new Document();

// الحصول على محتوى للعمل مع TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// تعيين العنوان واللغة للوثيقة
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// تكوين عناصر البنية المنطقية
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1. ");
p2.SetText("P2. ");
p3.SetText("P3. ");
p4.SetText("P4. ");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);

// حفظ وثيقة PDF الموسومة
document.Save(dataDir + "CustomTag.pdf");

```

## خاتمة

تهنئة ! لقد تعلمت كيفية استخدام اسم علامة مخصصة مع Aspose.PDF for .NET. يمكنك الآن إضافة معلومات هيكلية محددة إلى مستند PDF الخاص بك باستخدام علامات مخصصة. اكتشف المزيد من ميزات Aspose.PDF لاكتشاف إمكاناتها الكاملة.
