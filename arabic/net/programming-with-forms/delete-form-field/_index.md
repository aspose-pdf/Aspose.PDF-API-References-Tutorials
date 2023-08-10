---
title: حذف حقل النموذج في مستند PDF
linktitle: حذف حقل النموذج في مستند PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بإزالة حقول النموذج غير المرغوب فيها بسهولة في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 50
url: /ar/net/programming-with-forms/delete-form-field/
---
في هذا البرنامج التعليمي ، سنوضح لك كيفية حذف حقل نموذج باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

أولاً ، تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح المستند

افتح مستند PDF الموجود:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
```

## الخطوة 3: حذف حقل معين

حذف حقل نموذج معين باستخدام اسمه:

```csharp
pdfDocument.Form.Delete("textbox1");
```

## الخطوة 4: احفظ المستند المحرر

احفظ مستند PDF المعدل:

```csharp
dataDir = dataDir + "DeleteFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لحذف حقل النموذج باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
// حذف حقل معين بالاسم
pdfDocument.Form.Delete("textbox1");
dataDir = dataDir + "DeleteFormField_out.pdf";
// احفظ المستند المعدل
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية حذف حقل نموذج باستخدام Aspose.PDF for .NET. باتباع هذه الخطوات ، يمكنك بسهولة إزالة حقول النماذج غير المرغوب فيها من مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### التعليمات

#### س: هل يمكنني حذف حقول نماذج متعددة مرة واحدة باستخدام Aspose.PDF for .NET؟

 ج: نعم ، يمكنك حذف حقول نماذج متعددة مرة واحدة باستخدام Aspose.PDF for .NET. ما عليك سوى الاتصال بـ`Delete` طريقة لكل حقل نموذج تريد إزالته.

#### س: كيف يمكنني التحقق من وجود حقل نموذج قبل محاولة حذفه؟

 ج: يمكنك التحقق من وجود حقل نموذج قبل محاولة حذفه باستخدام ملف`Contains` طريقة`Form` ملكية. على سبيل المثال:

```csharp
if (pdfDocument.Form.Contains("textbox1"))
{
    pdfDocument.Form.Delete("textbox1");
}
```

#### س: ماذا يحدث إذا حاولت حذف حقل نموذج غير موجود في مستند PDF؟

 ج: إذا حاولت حذف حقل نموذج غير موجود في مستند PDF ، فإن ملف`Delete` لن يؤدي الأسلوب إلى ظهور خطأ أو استثناء. لن تفعل شيئًا ببساطة ، حيث لا يوجد حقل لحذفه.

#### س: هل يمكنني حذف حقول النموذج من أنواع مختلفة ، مثل الحقول النصية ومربعات الاختيار وأزرار الاختيار؟

 ج: نعم ، يمكنك حذف حقول النموذج من أنواع مختلفة ، مثل الحقول النصية ومربعات الاختيار وأزرار الاختيار ، باستخدام نفس`Delete` الطريقة في Aspose.PDF لـ .NET. ما عليك سوى تمرير اسم الحقل الذي تريد حذفه كمعامل للطريقة.

#### س: هل من الممكن التراجع عن حذف حقل نموذج في مستند PDF؟

ج: لا ، بمجرد حذف حقل النموذج باستخدام Aspose.PDF for .NET ، لا يمكن التراجع عنه برمجيًا. يوصى بإنشاء نسخة احتياطية من مستند PDF قبل إجراء أي تغييرات عليه ، حتى تتمكن من الرجوع إلى المستند الأصلي إذا لزم الأمر.