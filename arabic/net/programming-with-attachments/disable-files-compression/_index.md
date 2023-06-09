---
title: تعطيل ضغط الملفات
linktitle: تعطيل ضغط الملفات
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعطيل ضغط الملفات في ملف PDF باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة لسهولة التعامل.
type: docs
weight: 30
url: /ar/net/programming-with-attachments/disable-files-compression/
---
في هذا البرنامج التعليمي ، سنرشدك خلال التعليمات البرمجية المصدر C # التالية خطوة بخطوة لتعطيل ضغط الملفات في ملف PDF باستخدام Aspose.PDF for .NET.

تأكد من تثبيت مكتبة Aspose.PDF وإعداد بيئة التطوير الخاصة بك قبل أن تبدأ. لديك أيضًا معرفة أساسية ببرمجة C #.

### الخطوة 1: إعداد دليل المستند

في التعليمات البرمجية المصدر المتوفرة ، تحتاج إلى تحديد الدليل حيث يوجد ملف PDF الذي تريد تعطيل ضغط الملف فيه. قم بتغيير متغير "dataDir" إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### الخطوة 2: افتح مستند PDF الحالي

نفتح مستند PDF الحالي باستخدام المسار المحدد.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### الخطوة 3: إعداد الملف الجديد لإضافته كمرفق

نقوم بتكوين الملف الجديد الذي نريد إضافته كمرفق. في هذا المثال ، نضيف ملفًا نصيًا باسم "test_out.txt" ووصف "مثال لملف نصي".

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### الخطوة 4: تعطيل ضغط الملفات

نقوم بتعطيل ضغط الملفات عن طريق تعيين خاصية ترميز كائن FileSpecification على FileEncoding.None.

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### الخطوة 5: إضافة المرفق إلى مجموعة مرفقات المستند

نضيف المرفق إلى مجموعة مرفقات المستند.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### الخطوة 6: احفظ ملف الإخراج الجديد

أخيرًا ، نحفظ ملف PDF الجديد الناتج باسم "DisableFilesCompression_out.pdf" في الدليل المحدد.

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### نموذج التعليمات البرمجية المصدر لـ Disable Files Compression باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// قم بإعداد ملف جديد لإضافته كمرفق
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
// حدد خاصية التشفير واضبطها على FileEncoding.None
fileSpecification.Encoding = FileEncoding.None;
// أضف مرفقًا إلى مجموعة مرفقات المستند
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
// حفظ الإخراج الجديد
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## خاتمة

في هذا البرنامج التعليمي ، شرحنا كيفية تعطيل ضغط الملفات في ملف PDF باستخدام Aspose.PDF لـ .NET. يمكنك الآن استخدام هذه المعرفة للحفاظ على تكامل الملفات المرفقة بدون ضغط.