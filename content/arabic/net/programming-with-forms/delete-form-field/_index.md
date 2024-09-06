---
title: حذف حقل النموذج في مستند PDF
linktitle: حذف حقل النموذج في مستند PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك بسهولة إزالة حقول النموذج غير المرغوب فيها في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 50
url: /ar/net/programming-with-forms/delete-form-field/
---
في هذا البرنامج التعليمي، سنوضح لك كيفية حذف حقل نموذج باستخدام Aspose.PDF لـ .NET. وسنشرح لك التعليمات البرمجية المصدرية للغة C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

أولاً، تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات:

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

حفظ مستند PDF المعدل:

```csharp
dataDir = dataDir + "DeleteFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### عينة من كود المصدر لحذف حقل النموذج باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "DeleteFormField.pdf");
// حذف حقل معين حسب الاسم
pdfDocument.Form.Delete("textbox1");
dataDir = dataDir + "DeleteFormField_out.pdf";
// حفظ المستند المعدل
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية حذف حقل نموذج باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة إزالة حقول النموذج غير المرغوب فيها من مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### الأسئلة الشائعة

#### س: هل يمكنني حذف حقول نماذج متعددة مرة واحدة باستخدام Aspose.PDF لـ .NET؟

 ج: نعم، يمكنك حذف حقول نماذج متعددة مرة واحدة باستخدام Aspose.PDF لـ .NET. ما عليك سوى الاتصال بـ`Delete` الطريقة لكل حقل نموذج تريد إزالته.

#### س: كيف يمكنني التحقق من وجود حقل النموذج قبل محاولة حذفه؟

 أ: يمكنك التحقق مما إذا كان حقل النموذج موجودًا قبل محاولة حذفه باستخدام`Contains` طريقة`Form` الممتلكات. على سبيل المثال:

```csharp
if (pdfDocument.Form.Contains("textbox1"))
{
    pdfDocument.Form.Delete("textbox1");
}
```

#### س: ماذا يحدث إذا حاولت حذف حقل نموذج غير موجود في مستند PDF؟

 أ: إذا حاولت حذف حقل نموذج غير موجود في مستند PDF،`Delete` لن تتسبب الطريقة في حدوث خطأ أو استثناء. فهي ببساطة لن تفعل أي شيء، حيث لا يوجد حقل يمكن حذفه.

#### س: هل يمكنني حذف حقول النماذج من أنواع مختلفة، مثل حقول النص ومربعات الاختيار وأزرار الاختيار؟

 ج: نعم، يمكنك حذف حقول النماذج من أنواع مختلفة، مثل حقول النص ومربعات الاختيار وأزرار الاختيار، باستخدام نفس`Delete` الطريقة في Aspose.PDF لـ .NET. ما عليك سوى تمرير اسم الحقل الذي تريد حذفه كمعلمة إلى الطريقة.

#### س: هل من الممكن التراجع عن حذف حقل النموذج في مستند PDF؟

ج: لا، بمجرد حذف حقل نموذج باستخدام Aspose.PDF لـ .NET، لا يمكن التراجع عن ذلك برمجيًا. يوصى بإنشاء نسخة احتياطية من مستند PDF قبل إجراء أي تغييرات عليه، حتى تتمكن من الرجوع إلى المستند الأصلي إذا لزم الأمر.