---
title: تحقق من صحة PDFUAstandard
linktitle: تحقق من صحة PDFUAstandard
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF for .NET للتحقق من صحة معيار PDF / UA باستخدام كود C #. دليل خطوة بخطوة.
type: docs
weight: 400
url: /ar/net/programming-with-document/validatepdfuastandard/
---
Aspose.PDF for .NET مكتبة قوية توفر ميزات متنوعة للعمل مع مستندات PDF. تتمثل إحدى ميزاته في القدرة على التحقق من صحة مستندات PDF للتوافق مع معايير PDF / UA. في هذه المقالة ، سنقدم إرشادات خطوة بخطوة حول كيفية استخدام Aspose.PDF لـ .NET للحصول على التوافق القياسي مع PDF / UA والتحقق من صحته باستخدام كود C #.

## الخطوة 1: تحديد مسار دليل المستند

بعد ذلك ، نحتاج إلى تحديد المسار إلى الدليل حيث يوجد مستند PDF الخاص بنا. يمكنك القيام بذلك عن طريق إضافة مقتطف الشفرة التالي:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

استبدل "دليل مستنداتك" بالمسار الفعلي إلى دليل مستند PDF الخاص بك.

## الخطوة 2: فتح مستند PDF

بعد تحديد مسار دليل المستند ، يمكننا فتح مستند PDF الخاص بنا باستخدام الكود التالي:

```csharp
Document pdfDocument = new Document(dataDir + "ValidatePDFUAStandard.pdf");
```

 هذا الرمز يخلق ملف`Document` كائن من ملف PDF الموجود في الدليل المحدد.

## الخطوة 3: التحقق من صحة ملف PDF لـ PDF / UA

الآن بعد أن فتحنا مستند PDF ، يمكننا استخدام Aspose.PDF لـ .NET للتحقق من صحة المستند لتوافق PDF / UA. سيفي مقتطف الشفرة التالي بالمهمة:

```csharp
bool isValidPdfUa = pdfDocument.Validate(dataDir + "validation-result-UA.xml", PdfFormat.PDF_UA_1);
```

يتحقق هذا الرمز من صحة وثيقة PDF للتوافق القياسي مع PDF / UA وينشئ تقرير تحقق في ملف XML المحدد. يتم تخزين نتيجة التحقق في ملف`isValidPdfUa` متغير ، وهو من نوع البيانات المنطقية.

### مثال على شفرة المصدر للحصول على Validate PDFUAstandard باستخدام Aspose.PDF for .NET

```csharp
           
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// افتح المستند
	Document pdfDocument = new Document(dataDir + "ValidatePDFUAStandard.pdf");

	// تحقق من صحة PDF لـ PDF / UA
	bool isValidPdfUa = pdfDocument.Validate(dataDir + "validation-result-UA.xml", PdfFormat.PDF_UA_1);
		   
```
