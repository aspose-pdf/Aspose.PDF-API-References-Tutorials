---
title: خصائص عناصر الهيكل
linktitle: خصائص عناصر الهيكل
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة للتعامل مع خصائص العنصر الهيكلي في مستند PDF باستخدام Aspose.PDF for .NET. إنشاء عناصر هيكلية غنية بالمعلومات.
type: docs
weight: 150
url: /ar/net/programming-with-tagged-pdf/structure-elements-properties/
---
في هذا الدليل ، سوف نوضح لك كيفية التعامل مع خصائص العناصر الهيكلية في مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. Aspose.PDF هي مكتبة قوية تتيح لك إنشاء ملفات PDF ومعالجتها وتحويلها برمجيًا.

دعنا نتعمق في الكود ونتعلم كيفية التعامل مع خصائص عنصر البنية في مستند PDF باستخدام Aspose.PDF for .NET.

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
taggedContent.SetTitle("Tagged PDF document");

// اضبط لغة المستند
taggedContent.SetLanguage("fr-FR");
```

## الخطوة 4: إنشاء العناصر الهيكلية

ثم نقوم بإنشاء العناصر الهيكلية في وثيقة PDF. في هذا المثال ، سننشئ عنصر قسم (`SectElement`) وعنصر الرأس (`HeaderElement`).

```csharp
//قم بإنشاء عنصر قسم
StructureElement rootElement = taggedContent.RootElement;
SectElement sect = taggedContent.CreateSectElement();
rootElement.AppendChild(sect);

// قم بإنشاء عنصر رأس
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
sect.AppendChild(h1);
h1.SetText("Header");
h1.Title = "Title";
h1.Language = "fr-FR";
h1.AlternativeText = "Alternative Text";
h1.ExpansionText = "Expansion Text";
h1.ActualText = "Actual Text";
```

## الخطوة 5: احفظ مستند PDF الذي تم وضع علامة عليه

أخيرًا ، نقوم بحفظ مستند PDF الموسوم.

```csharp
// احفظ مستند PDF بعلامات
document.Save(dataDir + "StructureElementsProperties.pdf");
```

### نموذج التعليمات البرمجية المصدر لخصائص عناصر البنية باستخدام Aspose.PDF لـ .NET 
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

// تكوين عناصر الهيكل
StructureElement rootElement = taggedContent.RootElement;
SectElement sect = taggedContent.CreateSectElement();
rootElement.AppendChild(sect);
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
sect.AppendChild(h1);
h1.SetText("The Header");
h1.Title = "Title";
h1.Language = "en-US";
h1.AlternativeText = "Alternative Text";
h1.ExpansionText = "Expansion Text";
h1.ActualText = "Actual Text";

// حفظ وثيقة PDF الموسومة
document.Save(dataDir + "StructureElementsProperties.pdf");

```

## خاتمة

تهنئة ! أنت تعرف الآن كيفية التعامل مع خصائص العنصر الهيكلي في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك أيضًا استكشاف ميزات Aspose.PDF لإنشاء مستندات PDF مخصصة مع عناصر بنية غنية بالمعلومات.
