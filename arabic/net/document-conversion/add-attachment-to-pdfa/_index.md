---
title: أضف مرفقًا إلى PDFA
linktitle: أضف مرفقًا إلى PDFA
second_title: Aspose.PDF لمرجع .NET API
description: أضف المرفقات بسهولة إلى ملفات PDF / A الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 10
url: /ar/net/document-conversion/add-attachment-to-pdfa/
---

في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة حول كيفية إضافة مرفق إلى ملف PDF / A باستخدام Aspose.PDF for .NET. سنشرح كل خطوة باستخدام أمثلة كود C # ونقدم إرشادات خطوة بخطوة لمساعدتك على المتابعة بسهولة.

## مقدمة

يمكن أن تكون المرفقات إضافات قيمة لملفات PDF ، لأنها تسمح لك بتضمين ملفات إضافية مثل الصور أو المستندات أو الوسائط ذات الصلة. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة إضافة المرفقات إلى ملفات PDF الخاصة بك والتأكد من تضمينها في النتيجة النهائية.

## إعداد البيئة

قبل البدء في التنفيذ ، دعونا أولاً نقوم بتهيئة بيئة التطوير الخاصة بنا للعمل مع Aspose.PDF for .NET.

1. قم بتثبيت Visual Studio أو أي IDE آخر مناسب لتطوير C #.
2. إنشاء مشروع C # جديد.
3. قم بتثبيت حزمة Aspose.PDF لـ .NET عبر NuGet لإضافة التبعيات الضرورية.

## الخطوة 1: تحميل ملف PDF موجود

لإضافة مرفق ، نحتاج أولاً إلى تحميل ملف PDF موجود. اتبع هذه الخطوات لتحميل المستند باستخدام Aspose.PDF for .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء مثيل مستند جديد لتحميل الملف الحالي
Aspose.Pdf.Document doc = new Document(dataDir + "input.pdf");
```

 في الكود أعلاه ، استبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد مستند PDF الذي تم إدخاله. يقوم هذا الرمز بتهيئة مثيل جديد لملف`Document` فئة وتحميل ملف PDF الموجود.

## الخطوة 2: إنشاء مواصفات الملف للمرفق

لإضافة مرفق ، نحتاج إلى إنشاء ملف محدد يحدد خصائص المرفق. اتبع هذه الخطوات لإنشاء مواصفات الملف:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// حدد الملف الجديد لإضافته كمرفق
FileSpecification fileSpecification = new FileSpecification(dataDir + "aspose-logo.jpg", "Large image file");
```

 في الكود أعلاه ، استبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد ملف الصورة المراد إضافته. يتم إنشاء مواصفات الملف باستخدام الامتداد`FileSpecification` فئة ، مع تحديد مسار الملف ووصف.

## الخطوة 3: إضافة المرفق إلى المستند

الآن بعد أن أصبح لدينا مواصفات الملف ، يمكننا إضافته إلى مجموعة مرفقات المستند. اتبع هذه الخطوات لإضافة المرفق:

```csharp
// أضف المرفق إلى مجموعة

  document attachments
doc.EmbeddedFiles.Add(fileSpecification);
```

 في الكود أعلاه ، نستخدم الامتداد`Add` طريقة المستند`s `مجموعة EmbeddedFiles` لإضافة مواصفات الملف كمرفق.

## الخطوة 4: التحويل إلى PDF / A_3a

لكي يتم تضمين المرفق في الملف الناتج ، نحتاج إلى التحويل إلى تنسيق PDF / A_3a. اتبع هذه الخطوات لإجراء التحويل:

```csharp
// قم بإجراء التحويل إلى تنسيق PDF / A_3a
doc.Convert(dataDir + "log.txt", Aspose.Pdf.PdfFormat.PDF_A_3A, ConvertErrorAction.Delete);
```

 في الكود أعلاه ، نستخدم الامتداد`Convert`طريقة لتحويل المستند باستخدام`"log.txt"` ملف تسجيل. نحدد تنسيق الإخراج باستخدام`PdfFormat.PDF_A_3A` تعداد وتحديد الإجراء المطلوب اتخاذه بشأن خطأ التحويل مع`ConvertErrorAction.Delete`.

## الخطوة 5: احفظ الملف الناتج

أخيرًا ، نقوم بحفظ مستند PDF المعدل مع المرفق المضاف. اتبع هذه الخطوات لحفظ الملف الناتج:

```csharp
// احفظ الملف الناتج
doc.Save(dataDir + "AddAttachmentToPDFA_out.pdf");
```

 في الكود أعلاه ، نستخدم الامتداد`Save` طريقة لحفظ المستند باسم الملف`"AddAttachmentToPDFA_out.pdf"`. تأكد من تحديد المسار المناسب حيث تريد حفظ الملف الناتج.

### مثال على الكود المصدري لإضافة مرفق إلى PDFA باستخدام Aspose.PDF for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// إنشاء مثيل المستند لتحميل ملف موجود
Aspose.Pdf.Document doc = new Document(dataDir + "input.pdf");
// قم بإعداد ملف جديد لإضافته كمرفق
FileSpecification fileSpecification = new FileSpecification(dataDir + "aspose-logo.jpg", "Large Image file");
// أضف مرفقًا إلى مجموعة مرفقات المستند
doc.EmbeddedFiles.Add(fileSpecification);
// قم بإجراء التحويل إلى PDF / A_3a بحيث يتم تضمين المرفق في ملف resultnat
doc.Convert(dataDir + "log.txt", Aspose.Pdf.PdfFormat.PDF_A_3A, ConvertErrorAction.Delete);
// حفظ الملف الناتج
doc.Save(dataDir + "AddAttachmentToPDFA_out.pdf");

Console.WriteLine("\nAttachment added successfully to PDF/A file.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية إضافة مرفق إلى ملف PDF / A باستخدام Aspose.PDF لـ .NET. لقد غطينا كل خطوة من خطوات العملية ، من تحميل المستند الحالي إلى تحويل الملف الناتج وحفظه. باستخدام أمثلة التعليمات البرمجية المتوفرة ، يمكنك بسهولة دمج هذه الوظيفة في مشاريعك الخاصة. جرب Aspose.PDF لـ .NET واكتشف الإمكانيات التي يوفرها لمعالجة متقدمة لملفات PDF.

