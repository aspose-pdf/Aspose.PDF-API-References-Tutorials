---
title: املأ حقول XFAF
linktitle: املأ حقول XFAF
second_title: Aspose.PDF لمرجع .NET API
description: قم بملء حقول XFA بسهولة في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 90
url: /ar/net/programming-with-forms/fill-xfafields/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية ملء حقول XFA باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

أولاً ، تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل نموذج XFA

قم بتحميل نموذج XFA:

```csharp
Document doc = new Document(dataDir + "FillXFAFields.pdf");
```

## الخطوة 3: احصل على أسماء حقول XFA

احصل على أسماء حقول XFA للنموذج:

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## الخطوة 4: تعيين قيم الحقل

قم بتعيين قيم حقل XFA باستخدام الأسماء التي تم الحصول عليها مسبقًا:

```csharp
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
```

## الخطوة 5: احفظ المستند المحدث

احفظ مستند PDF المحدث:

```csharp
dataDir = dataDir + "Filled_XFA_out.pdf";
doc.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لملء XFAFields باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تحميل نموذج XFA
Document doc = new Document(dataDir + "FillXFAFields.pdf");
//احصل على أسماء حقول نموذج XFA
string[] names = doc.Form.XFA.FieldNames;
// قم بتعيين قيم الحقل
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
dataDir = dataDir + "Filled_XFA_out.pdf";
// احفظ المستند المحدث
doc.Save(dataDir);
Console.WriteLine("\nXFA fields filled successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية ملء حقول XFA باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك بسهولة تغيير قيم حقول XFA في مستندات PDF الخاصة بك باستخدام Aspose.PDF.