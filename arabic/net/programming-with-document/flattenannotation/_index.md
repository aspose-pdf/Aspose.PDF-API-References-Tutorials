---
title: تسطيح الشرح
linktitle: تسطيح الشرح
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تسوية التعليقات التوضيحية في مستند PDF باستخدام Aspose.PDF for .NET. الحفاظ على التعليقات التوضيحية ومنع التغيير العرضي.
type: docs
weight: 150
url: /ar/net/programming-with-document/flattenannotation/
---

Aspose.PDF for .NET مكتبة قوية تمكن المطورين من العمل مع مستندات PDF برمجيًا. إحدى الميزات التي يوفرها هي القدرة على تسوية التعليقات التوضيحية في مستندات PDF. تعني تسوية التعليقات التوضيحية في مستند PDF أن التعليقات التوضيحية أصبحت جزءًا من محتوى المستند ولا يمكن تحريرها أو حذفها بعد الآن. يكون هذا مفيدًا عندما تريد التأكد من الاحتفاظ بالتعليقات التوضيحية ولا يمكن تغييرها عن طريق الخطأ.

في هذا البرنامج التعليمي ، سنناقش كيفية استخدام Aspose.PDF لـ .NET لتسوية التعليقات التوضيحية في مستند PDF. سنقدم دليلًا تفصيليًا حول كيفية القيام بذلك ، جنبًا إلى جنب مع مثال على كود المصدر.

## الخطوة 1: إنشاء تطبيق C # Console جديد
للبدء ، قم بإنشاء تطبيق C # Console جديد في Visual Studio. يمكنك تسميته ما شئت. بمجرد إنشاء المشروع ، تحتاج إلى إضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد Aspose.PDF Namespace
أضف السطر التالي من التعليمات البرمجية أعلى ملف C # لاستيراد مساحة الاسم Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## الخطوة 3: افتح مستند PDF
افتح مستند PDF الذي تريد تسويته:

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## الخطوة 4: تسوية التعليقات التوضيحية
قم بتسوية التعليقات التوضيحية في مستند PDF:

```csharp
foreach (var page in pdfDocument.Pages)
{
    foreach (var annotation in page.Annotations)
    {
        annotation.Flatten();
    }
}
```

## الخطوة 5: احفظ المستند المحدث
احفظ المستند المحدث:

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("\nFlattened annotation successfully.\nFile saved at " + dataDir);
```

### مثال على التعليمات البرمجية المصدر لـ Flatten Annotation باستخدام Aspose.PDF for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// تسطيح التعليقات التوضيحية
foreach (var page in pdfDocument.Pages)
{
	foreach (var annotation in page.Annotations)
	{
		annotation.Flatten();
	}

}
// احفظ المستند المحدث
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("\nFlattened annotation successfully.\nFile saved at " + dataDir);
```

## خاتمة
في هذا البرنامج التعليمي ، ناقشنا كيفية تسوية التعليقات التوضيحية في مستند PDF باستخدام Aspose.PDF لـ .NET. تعد تسوية التعليقات التوضيحية في مستند PDF ميزة مفيدة تضمن الاحتفاظ بالتعليقات التوضيحية ولا يمكن تغييرها عن طريق الخطأ. يوفر Aspose.PDF for .NET واجهة برمجة تطبيقات بسيطة وسهلة الاستخدام للعمل مع مستندات PDF ، بما في ذلك تسطيح التعليقات التوضيحية. 

