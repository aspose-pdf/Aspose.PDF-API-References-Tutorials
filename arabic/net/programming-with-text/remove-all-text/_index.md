---
title: إزالة كل النص
linktitle: إزالة كل النص
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إزالة كل النص من مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 280
url: /ar/net/programming-with-text/remove-all-text/
---

في هذا البرنامج التعليمي ، سنشرح كيفية إزالة كل النص من مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. سنتابع العملية خطوة بخطوة لفتح ملف PDF ، واختيار وحذف النص من كل صفحة ، وحفظ ملف PDF المعدل باستخدام كود المصدر C # المقدم.

## متطلبات

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي لبرمجة C #.

## الخطوة 1: قم بإعداد دليل المستندات

 أولاً ، تحتاج إلى تعيين المسار إلى الدليل حيث توجد ملفات PDF الخاصة بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى ملفات PDF الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

 بعد ذلك ، نفتح مستند PDF باستخدام ملف`Document` فئة من مكتبة Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## الخطوة 3: إزالة النص من كل صفحة

 نقوم بعمل حلقة عبر جميع صفحات مستند PDF ونستخدم ملف`OperatorSelector` لتحديد كل النص في كل صفحة. ثم نقوم بحذف النص المحدد.

```csharp
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
     Page page = pdfDocument.Pages[i];
     OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
     page.Contents.Accept(operatorSelector);
     page.Contents.Delete(operatorSelector.Selected);
}
```

## الخطوة 4: احفظ ملف PDF المعدل

أخيرًا ، نقوم بحفظ مستند PDF المعدل في ملف الإخراج المحدد.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### نموذج التعليمات البرمجية المصدر لـ Remove All Text باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// قم بالتكرار خلال كل صفحات مستند PDF
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
	Page page = pdfDocument.Pages[i];
	OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
	// حدد كل النص على الصفحة
	page.Contents.Accept(operatorSelector);
	// حذف كل النص
	page.Contents.Delete(operatorSelector.Selected);
}
// احفظ المستند
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية إزالة كل النص من مستند PDF باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل المفصل خطوة بخطوة وتنفيذ كود C # المقدم ، يمكنك فتح ملف PDF وتحديد وحذف النص من كل صفحة وحفظ ملف PDF المعدل.