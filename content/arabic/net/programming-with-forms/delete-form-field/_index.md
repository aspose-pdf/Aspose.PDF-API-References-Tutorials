---
title: حذف حقل النموذج في وثيقة PDF
linktitle: حذف حقل النموذج في وثيقة PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بإزالة حقول النموذج غير المرغوب فيها بسهولة في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 50
url: /ar/net/programming-with-forms/delete-form-field/
---
سنوضح لك في هذا البرنامج التعليمي كيفية حذف حقل نموذج باستخدام Aspose.PDF لـ .NET. سنشرح لك كود مصدر C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

أولاً، تأكد من استيراد المكتبات اللازمة وتعيين المسار إلى دليل المستندات:

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

## الخطوة 4: احفظ المستند الذي تم تحريره

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
// حفظ الوثيقة المعدلة
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular field deleted successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية حذف حقل نموذج باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة إزالة حقول النماذج غير المرغوب فيها من مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### الأسئلة الشائعة

#### س: هل يمكنني حذف حقول نماذج متعددة مرة واحدة باستخدام Aspose.PDF لـ .NET؟

 ج: نعم، يمكنك حذف حقول نماذج متعددة مرة واحدة باستخدام Aspose.PDF لـ .NET. ما عليك سوى الاتصال بـ`Delete` طريقة لكل حقل نموذج تريد إزالته.

#### س: كيف يمكنني التحقق من وجود حقل النموذج قبل محاولة حذفه؟

 ج: يمكنك التحقق من وجود حقل نموذج قبل محاولة حذفه باستخدام الملف`Contains` طريقة`Form` ملكية. على سبيل المثال:

```csharp
if (pdfDocument.Form.Contains("textbox1"))
{
    pdfDocument.Form.Delete("textbox1");
}
```

#### س: ماذا يحدث إذا حاولت حذف حقل نموذج غير موجود في مستند PDF؟

 ج: إذا حاولت حذف حقل نموذج غير موجود في مستند PDF، فسيتم حذف حقل النموذج`Delete` لن ترمي الطريقة خطأ أو استثناء. ببساطة لن يفعل شيئًا، حيث لا يوجد حقل لحذفه.

#### س: هل يمكنني حذف حقول النموذج من أنواع مختلفة، مثل حقول النص وخانات الاختيار وأزرار الاختيار؟

 ج: نعم، يمكنك حذف حقول النموذج بأنواعها المختلفة، مثل الحقول النصية وخانات الاختيار وأزرار الاختيار، باستخدام نفس الطريقة`Delete` الطريقة في Aspose.PDF لـ .NET. ما عليك سوى تمرير اسم الحقل الذي تريد حذفه كمعلمة للطريقة.

#### س: هل من الممكن التراجع عن حذف حقل النموذج في وثيقة PDF؟

ج: لا، بمجرد حذف حقل نموذج باستخدام Aspose.PDF لـ .NET، لا يمكن التراجع عن ذلك برمجيًا. يوصى بإنشاء نسخة احتياطية من مستند PDF قبل إجراء أي تغييرات عليه، حتى تتمكن من العودة إلى المستند الأصلي إذا لزم الأمر.