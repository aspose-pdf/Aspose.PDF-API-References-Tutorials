---
title: إزالة الجدول
linktitle: إزالة الجدول
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إزالة جدول في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 160
url: /ar/net/programming-with-tables/remove-table/
---

في هذا البرنامج التعليمي ، سنوجهك خطوة بخطوة لإزالة جدول في مستند PDF باستخدام Aspose.PDF for .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه.

## الخطوة 1: تحميل مستند PDF الحالي
أولاً ، تحتاج إلى تحميل مستند PDF الحالي باستخدام الكود التالي:

```csharp
// المسار إلى دليل المستندات
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل مستند PDF الموجود
Document pdfDocument = new Document(dataDir + "Table_input.pdf");
```

## الخطوة 2: إنشاء كائن TableAbsorber للعثور على الجداول
بعد ذلك ، سننشئ كائن TableAbsorber للعثور على الجداول في مستند PDF:

```csharp
// قم بإنشاء كائن TableAbsorber للعثور على الجداول
TableAbsorber absorber = new TableAbsorber();
```

## الخطوة الثالثة: قم بزيارة الصفحة الأولى مع جهاز الامتصاص
سنقوم الآن بزيارة الصفحة الأولى من مستند PDF باستخدام أداة الامتصاص:

```csharp
//قم بزيارة الصفحة الأولى مع الممتص
absorb.Visit(pdfDocument.Pages[1]);
```

## الخطوة 4: الحصول على الجدول الأول على الصفحة
حتى نتمكن من إزالة الجدول سوف نحصل على الجدول الأول من الصفحة:

```csharp
// احصل على الجدول الأول على الصفحة
AbsorbedTable table = absorb.TableList[0];
```

## الخطوة 5: حذف الجدول
الآن دعنا نزيل المنضدة باستخدام جهاز الامتصاص:

```csharp
// قم بإزالة الجدول
absorb.Remove(table);
```

## الخطوة السادسة: احفظ ملف PDF
أخيرًا ، نحفظ مستند PDF المعدل:

```csharp
// احفظ ملف PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

### مثال على شفرة المصدر لـ Remove Table باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل مستند PDF موجود
Document pdfDocument = new Document(dataDir + "Table_input.pdf");

// قم بإنشاء كائن TableAbsorber للعثور على الجداول
TableAbsorber absorber = new TableAbsorber();

// زيارة الصفحة الأولى مع الماص
absorber.Visit(pdfDocument.Pages[1]);

// احصل على الجدول الأول على الصفحة
AbsorbedTable table = absorber.TableList[0];

// قم بإزالة الجدول
absorber.Remove(table);

// احفظ ملف PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

## خاتمة
تهنئة ! لقد تعلمت الآن كيفية إزالة جدول في مستند PDF باستخدام Aspose.PDF for .NET. يوضح لك هذا الدليل التفصيلي كيفية تحميل المستند والعثور على الجدول وإزالته. الآن يمكنك تطبيق هذه المعرفة على مشاريعك الخاصة.