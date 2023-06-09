---
title: تحديد لون الصفحة
linktitle: تحديد لون الصفحة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لتحديد لون صفحة PDF باستخدام Aspose.PDF for .NET. تحليل وعرض نوع اللون لكل صفحة. سهل التنفيذ.
type: docs
weight: 40
url: /ar/net/programming-with-pdf-pages/determine-page-color/
---
في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتحديد لون صفحة ملف PDF باستخدام Aspose.PDF لـ .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية تحديد لون صفحة ملف PDF باستخدام Aspose.PDF for .NET.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- معرفة أساسية بلغة البرمجة C #
- تم تثبيت Aspose.PDF for .NET في بيئة التطوير الخاصة بك

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يوجد به ملف PDF الخاص بك. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: افتح ملف PDF
 ثم يمكنك فتح ملف PDF للتحليل باستخدام امتداد`Document` فئة Aspose.PDF. تأكد من تحديد المسار الصحيح لملف PDF.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## الخطوة الثالثة: تحليل الصفحات
 يمكنك الآن تكرار كل صفحات مستند PDF باستخدام ملف`for` حلقة. لكل صفحة ، يمكنك الحصول على نوع لون الصفحة باستخدام ملف`ColorType` ممتلكات`Page` الكائن وعرضه في وحدة التحكم.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     ColorType pageColorType = pdfDocument.Pages[pageCount].ColorType;
     switch(pageColorType)
     {
         box ColorType.BlackAndWhite:
             Console.WriteLine("Page #" + pageCount + " is black and white.");
             break;
         ColorType.Grayscale box:
             Console.WriteLine("Page #" + pageCount + " is grayscale.");
             break;
         box ColorType.Rgb:
             Console.WriteLine("Page #" + pageCount + " is in RGB colors.");
             break;
         box ColorType.Undefined:
             Console.WriteLine("Page #" + pageCount + " has undefined color.");
             break;
     }
}
```

### نموذج التعليمات البرمجية المصدر لتحديد لون الصفحة باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// ملف PDF مفتوح المصدر
Document pdfDocument = new Document( dataDir + "input.pdf");
//كرر من خلال جميع صفحات ملف PDF
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	// احصل على معلومات نوع اللون لصفحة PDF معينة
	Aspose.Pdf.ColorType pageColorType = pdfDocument.Pages[pageCount].ColorType;
	switch (pageColorType)
	{
		case ColorType.BlackAndWhite:
			Console.WriteLine("Page # -" + pageCount + " is Black and white..");
			break;
		case ColorType.Grayscale:
			Console.WriteLine("Page # -" + pageCount + " is Gray Scale...");
			break;
		case ColorType.Rgb:
			Console.WriteLine("Page # -" + pageCount + " is RGB..", pageCount);
			break;
		case ColorType.Undefined:
			Console.WriteLine("Page # -" + pageCount + " Color is undefined..");
			break;
	}
}

```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تحديد لون صفحة ملف PDF باستخدام Aspose.PDF لـ .NET. باتباع الخطوات الموضحة أعلاه ، يمكنك بسهولة تنفيذ هذه الوظيفة في مشاريعك الخاصة. لا تتردد في استكشاف وثائق Aspose.PDF لاكتشاف الميزات المفيدة الأخرى للعمل مع ملفات PDF.