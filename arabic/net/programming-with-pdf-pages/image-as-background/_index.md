---
title: تعيين الصورة كخلفية
linktitle: تعيين الصورة كخلفية
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتعيين صورة كخلفية للصفحة في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 110
url: /ar/net/programming-with-pdf-pages/image-as-background/
---
في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتعيين صورة كخلفية للصفحة باستخدام Aspose.PDF لـ .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية إضافة صورة كخلفية للصفحة في مستند PDF باستخدام Aspose.PDF لـ .NET.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- معرفة أساسية بلغة البرمجة C #
- تم تثبيت Aspose.PDF for .NET في بيئة التطوير الخاصة بك

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي تريد حفظ مستند PDF الذي تم تحريره فيه. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بإنشاء مستند جديد
 ثم يمكنك إنشاء كائن مستند جديد باستخدام امتداد`Document` فصل.

```csharp
Document doc = new Document();
```

## الخطوة 3: أضف صفحة جديدة إلى المستند
 يمكنك الآن إضافة صفحة جديدة إلى كائن المستند باستخدام امتداد`Add()` طريقة`Pages` فصل.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 4: قم بإنشاء كائن في الخلفية
ثم يمكنك إنشاء كائن BackgroundArtifact جديد لتعيين صورة الخلفية.

```csharp
BackgroundArtifact background = new BackgroundArtifact();
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
```

## الخطوة 5: أضف الخلفية إلى الصفحة
 بعد ذلك ، يمكنك إضافة كائن BackgroundArtifact إلى مجموعة القطع الأثرية للصفحة باستخدام امتداد`Artifacts` ممتلكات`Page` فصل.

```csharp
page. Artifacts. Add(background);
```

## الخطوة 6: احفظ مستند PDF
 أخيرًا ، يمكنك حفظ مستند PDF في ملف باستخدام امتداد`Save()` طريقة`Document`فصل. تأكد من تحديد المسار الصحيح واسم الملف.

```csharp
doc.Save(dataDir + "ImageAsBackground_out.pdf");
```

### نموذج التعليمات البرمجية المصدر للصورة كخلفية باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بإنشاء كائن مستند جديد
Document doc = new Document();
// أضف صفحة جديدة إلى كائن المستند
Page page = doc.Pages.Add();
// إنشاء كائن الخلفية الأثرية
BackgroundArtifact background = new BackgroundArtifact();
// حدد الصورة لكائن backgroundartifact
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
// أضف backgroundartifact إلى مجموعة القطع الأثرية للصفحة
page.Artifacts.Add(background);
dataDir = dataDir + "ImageAsBackground_out.pdf";
// احفظ المستند
doc.Save(dataDir);
System.Console.WriteLine("\nImage as page background added successfully.\nFile saved at " + dataDir);

```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين صورة كخلفية للصفحة في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة إضافة صورة خلفية إلى مستندات PDF الخاصة بك. يوفر Aspose.PDF واجهة برمجة تطبيقات قوية ومرنة للعمل مع ملفات PDF ، بما في ذلك تخصيص خلفية الصفحة. يمكنك الآن تطبيق هذه الميزة في مشاريعك الخاصة لإنشاء مستندات PDF مع صور خلفية مخصصة
