---
title: إعداد اللغة والعنوان
linktitle: إعداد اللغة والعنوان
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتكوين لغة وعنوان مستند PDF باستخدام Aspose.PDF for .NET. قم بإنشاء مستندات متعددة اللغات مخصصة.
type: docs
weight: 140
url: /ar/net/programming-with-tagged-pdf/setup-language-and-title/
---
في هذا الدليل ، سنخبرك بكيفية تكوين لغة وعنوان مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. Aspose.PDF هي مكتبة قوية تتيح لك إنشاء ملفات PDF ومعالجتها وتحويلها برمجيًا.

دعنا نتعمق في الكود ونتعلم كيفية تكوين لغة وعنوان مستند PDF باستخدام Aspose.PDF لـ .NET.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من تثبيت Aspose.PDF لـ .NET وقم بإعداد بيئة التطوير الخاصة بك.

## الخطوة الأولى: إنشاء المستند

 تتمثل الخطوة الأولى في إنشاء مستند PDF جديد باستخدام امتداد`Document` فصل.

```csharp
// قم بإنشاء مستند PDF
Document document = new Document();
```

## الخطوة 2: الوصول إلى المحتوى الموسوم

 بعد ذلك ، نصل إلى المحتوى الذي تم وضع علامة عليه للمستند باستخدام ملف`ITaggedContent` هدف.

```csharp
//الوصول إلى المحتوى الموسوم
Tagged.ITaggedContent taggedContent = document.TaggedContent;
```

## الخطوة 3: حدد العنوان واللغة

 الآن يمكننا تعيين عنوان المستند ولغته باستخدام ملف`SetTitle` و`SetLanguage` طرق`ITaggedContent` هدف.

```csharp
// حدد عنوان المستند
taggedContent.SetTitle("Example of tagged document");

// اضبط لغة المستند
taggedContent.SetLanguage("fr-FR");
```

## الخطوة 4: إضافة محتوى متعدد اللغات

بعد ذلك ، نضيف محتوى متعدد اللغات إلى المستند باستخدام عناصر الفقرة لكل لغة.

```csharp
// أضف فقرة بالإنجليزية
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// أضف فقرة باللغة الألمانية
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hello Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// أضف فقرة بالفرنسية
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Hello world!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// أضف فقرة بالإسبانية
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);
```

## الخطوة 5: احفظ مستند PDF الذي تم وضع علامة عليه

أخيرًا ، نقوم بحفظ مستند PDF الموسوم.

```csharp
// احفظ مستند PDF بعلامات
document.Save(dataDir + "SetupLanguageAndTitle.pdf");
```

### نموذج التعليمات البرمجية المصدر للغة الإعداد والعنوان باستخدام Aspose.PDF لـ .NET 
```csharp

Document document = new Document();

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// احصل على TaggedContent
Tagged.ITaggedContent taggedContent = document.TaggedContent;

// تعيين العنوان واللغة
taggedContent.SetTitle("Example Tagged Document");
taggedContent.SetLanguage("en-US");

// العنوان (en-US ، موروث من المستند)
LogicalStructure.HeaderElement h1 = taggedContent.CreateHeaderElement(1);
h1.SetText("Phrase on different languages");
taggedContent.RootElement.AppendChild(h1);

// فقرة (الإنجليزية)
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// فقرة (ألمانية)
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hallo Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// فقرة (بالفرنسية)
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Bonjour le monde!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// فقرة (إسبانية)
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);

// حفظ وثيقة PDF الموسومة
document.Save(dataDir + "SetupLanguageAndTitle.pdf");

```

## خاتمة

تهنئة ! أنت تعرف الآن كيفية تكوين لغة وعنوان مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك أيضًا استكشاف ميزات Aspose.PDF لإنشاء مستندات PDF مخصصة ومتعددة اللغات.
