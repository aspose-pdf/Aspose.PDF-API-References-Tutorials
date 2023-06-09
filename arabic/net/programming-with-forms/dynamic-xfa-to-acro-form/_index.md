---
title: XFA الديناميكي إلى نموذج Acro
linktitle: XFA الديناميكي إلى نموذج Acro
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحويل XFA الديناميكي بسهولة إلى النماذج إلى نماذج AcroForm القياسية باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 70
url: /ar/net/programming-with-forms/dynamic-xfa-to-acro-form/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية تحويل XFA إلى نموذج ديناميكي إلى نموذج AcroForm باستخدام Aspose.PDF لـ .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

أولاً ، تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل نموذج XFA الديناميكي

قم بتحميل نموذج XFA الديناميكي:

```csharp
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
```

## الخطوة 3: قم بتعيين نوع النموذج على أنه نموذج AcroForm قياسي

قم بتعيين نوع النموذج على أنه AcroForm قياسي:

```csharp
document.Form.Type = FormType.Standard;
```

## الخطوة 4: احفظ ملف PDF الناتج

احفظ ملف PDF الناتج:

```csharp
dataDir = dataDir + "Standard_AcroForm_out.pdf";
document. Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Dynamic XFA To Acro Form باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تحميل نموذج XFA الديناميكي
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
// قم بتعيين نوع حقول النموذج على أنه AcroForm قياسي
document.Form.Type = FormType.Standard;
dataDir = dataDir + "Standard_AcroForm_out.pdf";
// احفظ ملف PDF الناتج
document.Save(dataDir);
Console.WriteLine("\nDynamic XFA form converted to standard AcroForm successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية تحويل XFA إلى نموذج ديناميكي إلى نموذج AcroForm قياسي باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك بسهولة تحويل نماذج XFATo الديناميكية إلى AcroForms لاستخدام أكثر شيوعًا.