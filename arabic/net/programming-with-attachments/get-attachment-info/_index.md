---
title: الحصول على معلومات المرفقات
linktitle: الحصول على معلومات المرفقات
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية الحصول على معلومات حول مرفق معين في ملف PDF باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة.
type: docs
weight: 50
url: /ar/net/programming-with-attachments/get-attachment-info/
---
في هذا البرنامج التعليمي ، سنرشدك خلال التعليمات البرمجية المصدر C # التالية خطوة بخطوة للحصول على معلومات حول مرفق معين لملف PDF باستخدام Aspose.PDF for .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل أن تبدأ. لديك أيضًا معرفة أساسية ببرمجة C #.

### الخطوة 1: إعداد دليل المستند

في التعليمات البرمجية المصدر المتوفرة ، تحتاج إلى تحديد الدليل الذي يوجد به ملف PDF الذي تريد الحصول على معلومات المرفقات منه. قم بتغيير متغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### الخطوة 2: افتح مستند PDF الحالي

نفتح مستند PDF الحالي باستخدام المسار المحدد.

```csharp
Document pdfDocument = new Document(dataDir + "GetAttachmentInfo.pdf");
```

### الخطوة الثالثة: الحصول على مرفق محدد

نسترجع مرفقًا محددًا من مجموعة مرفقات المستند. في هذا المثال ، نحصل على المرفق الأول باستخدام الفهرس 1.

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### الخطوة 4: احصل على خصائص الملف

نعرض خصائص المرفقات مثل الاسم والوصف ونوع MIME وتجزئة التحكم وتاريخ الإنشاء وتاريخ التعديل والحجم.

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// تحقق مما إذا كانت معلمات الكائن تحتوي على معلومات إضافية
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### نموذج التعليمات البرمجية المصدر للحصول على معلومات المرفقات باستخدام Aspose.PDF for .NET
 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "GetAttachmentInfo.pdf");
// احصل على ملف مضمن معين
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// احصل على خصائص الملف
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
// تحقق مما إذا كان كائن المعلمة يحتوي على المعلمات
if (fileSpecification.Params != null)
{
	Console.WriteLine("CheckSum: {0}",
	fileSpecification.Params.CheckSum);
	Console.WriteLine("Creation Date: {0}",
	fileSpecification.Params.CreationDate);
	Console.WriteLine("Modification Date: {0}",
	fileSpecification.Params.ModDate);
	Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

```

## خاتمة

في هذا البرنامج التعليمي ، شرحنا كيفية الحصول على معلومات حول مرفق معين لملف PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة لاستخراج وعرض معلومات المرفقات من ملفات PDF الخاصة بك.
