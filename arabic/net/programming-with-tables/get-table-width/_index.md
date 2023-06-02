---
title: احصل على عرض الجدول
linktitle: احصل على عرض الجدول
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية الحصول على عرض الجدول في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 90
url: /ar/net/programming-with-tables/get-table-width/
---

في هذا البرنامج التعليمي ، سوف نتعلم كيفية الحصول على عرض الجدول في مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح الكود المصدري في C # خطوة بخطوة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية الحصول على عرض الجدول في مستند PDF. لنبدأ!

## الخطوة الأولى: تهيئة البيئة
أولاً ، تأكد من إعداد بيئة التطوير C # الخاصة بك باستخدام Aspose.PDF لـ .NET. أضف المرجع إلى المكتبة واستورد مساحات الأسماء الضرورية.

## الخطوة 2: إنشاء مستند وصفحة جديدتين
نقوم بإنشاء مستند PDF جديد وإضافة صفحة في هذا المستند.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## الخطوة 3: تهيئة جدول جديد
نقوم بتهيئة جدول جديد وضبط العمود المناسب على "AutoFitToContent".

```csharp
Table table = new Table
{
ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
```

## الخطوة 4: أضف صفًا وخلايا في الجدول
نضيف صفًا في الجدول ونضيف خلايا في هذا الصف.

```csharp
Row row = table.Rows.Add();
Cell cell = row.Cells.Add("Text of cell 1");
cell = row.Cells.Add("Text from cell 2");
```

## الخطوة 5: احصل على عرض الجدول
نستخدم طريقة "GetWidth ()" للحصول على عرض الجدول.

```csharp
Console.WriteLine(table.GetWidth());
```

### مثال على شفرة المصدر للحصول على عرض الجدول باستخدام Aspose.Words for .NET

```csharp
// قم بإنشاء مستند جديد
Document doc = new Document();
// أضف الصفحة في المستند
Page page = doc.Pages.Add();
// تهيئة جدول جديد
Table table = new Table
{
	ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
// أضف صفًا في الجدول
Row row = table.Rows.Add();
// أضف خلية في الجدول
Cell cell = row.Cells.Add("Cell 1 text");
cell = row.Cells.Add("Cell 2 text");
// احصل على عرض الجدول
Console.WriteLine(table.GetWidth());

System.Console.WriteLine("Extracted table width succesfully!");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على عرض الجدول في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذا الدليل المفصل خطوة بخطوة للحصول على عروض الجدول في مشاريع C # الخاصة بك.