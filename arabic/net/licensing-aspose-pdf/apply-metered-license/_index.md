---
title: تكوين الترخيص المقنن
linktitle: تكوين الترخيص المقنن
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لإعداد ترخيص مقنن باستخدام Aspose.PDF for .NET والاستفادة من الميزات المتقدمة.
type: docs
weight: 10
url: /ar/net/licensing-aspose-pdf/configure-metered-license/
---

في هذا البرنامج التعليمي ، سنرشدك خطوة بخطوة حول كيفية إعداد ترخيص مقنن باستخدام Aspose.PDF for .NET. يسمح لك الترخيص المقنن باستخدام الميزات المتقدمة لـ Aspose.PDF بناءً على استهلاكك الفعلي.

### الخطوة 1: تكوين مفاتيح الترخيص

في التعليمات البرمجية المصدر المتوفرة ، يجب عليك تحديد المفاتيح العامة والخاصة للترخيص المحسوب. استبدل "*****"بالمفاتيح الخاصة بك. سيتم توفير هذه المفاتيح لك عند شراء ترخيص مقنن من Aspose.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

### الخطوة الثانية: تحميل المستند

 قم بتحميل مستند PDF من القرص باستخدام ملف`Document`فئة Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

### الخطوة 3: احصل على عدد صفحات المستند

 استخدم ال`Count` ممتلكات`Pages` جمع للحصول على العدد الإجمالي للصفحات في المستند.

```csharp
Console.WriteLine(doc.Pages.Count);
```

### نموذج التعليمات البرمجية المصدر لتكوين الترخيص المقياس باستخدام Aspose.PDF لـ .NET 

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تعيين المفاتيح العامة والخاصة المقننة
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
// الوصول إلى الخاصية setMeteredKey وتمرير المفاتيح العامة والخاصة كمعلمات
metered.SetMeteredKey("*****", "*****");
// قم بتحميل المستند من القرص.
Document doc = new Document(dataDir + "input.pdf");
//احصل على عدد الصفحات من المستند
Console.WriteLine(doc.Pages.Count);

```

## خاتمة

في هذا البرنامج التعليمي ، شرحنا كيفية إعداد ترخيص مقنن باستخدام Aspose.PDF لـ .NET. باستخدام ترخيص مقنن ، يمكنك الاستفادة من الميزات المتقدمة لـ Aspose.PDF بناءً على استخدامك الفعلي. تأكد من توفير مفاتيح ترخيص صالحة لاستخدام Aspose.PDF بجميع ميزاته.
