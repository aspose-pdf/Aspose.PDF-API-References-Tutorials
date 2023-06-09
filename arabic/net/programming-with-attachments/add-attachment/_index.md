---
title: إضافة مرفق
linktitle: إضافة مرفق
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة المرفقات إلى ملفات PDF الخاصة بك باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة لسهولة التعامل.
type: docs
weight: 10
url: /ar/net/programming-with-attachments/add-attachment/
---

في هذا البرنامج التعليمي ، سنوجهك عبر التعليمات البرمجية المصدر C # التالية خطوة بخطوة لإضافة مرفق إلى ملف PDF باستخدام Aspose.PDF for .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل أن تبدأ. لديك أيضًا معرفة أساسية ببرمجة C #.

### الخطوة 1: إعداد دليل المستند

في كود المصدر المقدم ، تحتاج إلى تحديد الدليل حيث يوجد ملف PDF الذي تريد إضافة المرفق فيه. قم بتغيير متغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### الخطوة 2: افتح مستند PDF الحالي

نفتح مستند PDF الحالي باستخدام المسار المحدد.

```csharp
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
```

### الخطوة 3: إعداد الملف الجديد لإضافته كمرفق

نقوم بتكوين الملف الجديد الذي نريد إضافته كمرفق. في هذا المثال ، نضيف ملفًا نصيًا باسم "test.txt" ووصفًا "مثال ملف نصي".

```csharp
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
```

### الخطوة 4: إضافة المرفق إلى مجموعة مرفقات المستند

نضيف المرفق إلى مجموعة مرفقات المستند.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### الخطوة 5: حفظ ملف الإخراج الجديد

أخيرًا ، نحفظ ملف PDF الجديد الناتج باسم "AddAttachment_out.pdf" في الدليل المحدد.

```csharp
pdfDocument.Save(dataDir + "AddAttachment_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لإضافة مرفق باستخدام Aspose.PDF لـ .NET
 
```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
// قم بإعداد ملف جديد لإضافته كمرفق
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
// أضف مرفقًا إلى مجموعة مرفقات المستند
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "AddAttachment_out.pdf";
// حفظ الإخراج الجديد
pdfDocument.Save(dataDir);
Console.WriteLine("\nSample text file attached successfully.\nFile saved at " + dataDir);

```

## خاتمة

في هذا البرنامج التعليمي ، شرحنا كيفية إضافة مرفق إلى ملف PDF باستخدام Aspose.PDF for .NET. يمكنك الآن استخدام هذه المعرفة لإضافة ملفات إضافية كمرفقات إلى مستندات PDF الخاصة بك.
