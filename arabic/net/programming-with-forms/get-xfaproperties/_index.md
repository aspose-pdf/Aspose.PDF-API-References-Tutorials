---
title: احصل على XFAProperties
linktitle: احصل على XFAProperties
second_title: Aspose.PDF لمرجع .NET API
description: احصل بسهولة على خصائص XFA لحقول النموذج في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.
type: docs
weight: 160
url: /ar/net/programming-with-forms/get-xfaproperties/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية الحصول على خصائص XFA لحقول النموذج في مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح كود المصدر C # خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة الأولى: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقم بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل نموذج XFA

قم بتحميل نموذج XFA من مستند PDF:

```csharp
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
```

## الخطوة 3: احصل على أسماء الحقول

احصل على أسماء حقول XFA:

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## الخطوة 4: تعيين قيم الحقل

تعيين قيم لحقول XFA:

```csharp
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
```

## الخطوة 5: احصل على موضع الحقول

احصل على موضع حقول XFA:

```csharp
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
```

## الخطوة 6: احفظ المستند المحدث

احفظ مستند PDF المحدث:

```csharp
dataDir = dataDir + "Filled_XFA_out.pdf";
doc.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر للحصول على XFAProperties باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تحميل نموذج XFA
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
string[] names = doc.Form.XFA.FieldNames;
// قم بتعيين قيم الحقل
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
// احصل على موقف ميداني
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
// احصل على موقف ميداني
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
dataDir = dataDir + "Filled_XFA_out.pdf";
// احفظ المستند المحدث
doc.Save(dataDir);
Console.WriteLine("\nXFA fields properties retrieved successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على خصائص XFA لحقول النموذج في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات ، يمكنك بسهولة استخراج معلومات حقل XFA ، مثل المواضع ، من مستندات PDF باستخدام Aspose.PDF.