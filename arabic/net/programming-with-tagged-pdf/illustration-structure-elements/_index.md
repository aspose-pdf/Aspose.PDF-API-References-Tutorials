---
title: عناصر الهيكل التوضيحي
linktitle: عناصر الهيكل التوضيحي
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لاستخدام أصول التوضيح مع Aspose.PDF for .NET. قم بتحسين عرض ملفات PDF الخاصة بك بالصور.
type: docs
weight: 100
url: /ar/net/programming-with-tagged-pdf/illustration-structure-elements/
---
في هذا الدليل المفصل خطوة بخطوة ، سوف نوضح لك كيفية استخدام عناصر البنية التوضيحية مع Aspose.PDF for .NET. Aspose.PDF هي مكتبة قوية تتيح لك معالجة مستندات PDF برمجيًا. تسمح لك عناصر هيكل الرسم التوضيحي بإضافة صور وأرقام إلى مستند PDF الخاص بك ، مما يؤدي إلى تحسين عرضه وفهمه المرئي.

دعنا نتعمق في الكود ونتعلم كيفية استخدام عناصر البنية التوضيحية مع Aspose.PDF for .NET.

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

## الخطوة 5: إضافة عمل فني

الآن دعنا نضيف عناصر توضيحية ، مثل الصور والأشكال ، إلى وثيقتنا.

```csharp
// تحت التطوير
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Figure One";
figure1.Title = "Picture 1";
figure1.SetTag("Fig1");
figure1.SetImage("image.png");
```

نقوم هنا بإنشاء عنصر هيكل توضيح ، وإعطائه نصًا بديلًا وعنوانًا وعلامة مخصصة وربط صورة به.

## الخطوة 6: احفظ مستند PDF الذي تم وضع علامة عليه

أخيرًا ، نقوم بحفظ مستند PDF الموسوم.

```csharp
// احفظ مستند PDF بعلامات
document.Save(dataDir + "IllustrationStructureElements.pdf");
```

### نموذج التعليمات البرمجية المصدر لعناصر البنية التوضيحية باستخدام Aspose.PDF لـ .NET 
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

// تحت التطوير
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Figure One";
figure1.Title = "Image 1";
figure1.SetTag("Fig1");
figure1.SetImage("image.png");

// حفظ وثيقة PDF الموسومة
document.Save(dataDir + "IllustrationStructureElements.pdf");

```

## خاتمة

تهنئة ! لقد تعلمت كيفية استخدام عناصر البنية التوضيحية مع Aspose.PDF for .NET. يمكنك الآن إضافة الصور والأشكال إلى مستند PDF الخاص بك لتحسين عرضه المرئي. اكتشف المزيد من ميزات Aspose.PDF لاكتشاف إمكاناتها الكاملة.