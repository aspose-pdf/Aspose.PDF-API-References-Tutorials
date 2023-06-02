---
title: تعيين خصائص مربع حوار الطباعة
linktitle: تعيين خصائص مربع حوار الطباعة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تعيين خصائص مربع حوار الطباعة في Aspose.PDF for .NET باستخدام دليل خطوة بخطوة.
type: docs
weight: 320
url: /ar/net/programming-with-document/setpropertiesforprintdialog/
---
إليك دليل خطوة بخطوة لتعيين خصائص مربع حوار الطباعة باستخدام Aspose.PDF for .NET:


## الخطوة 1: حدد الدليل حيث يوجد مستند PDF الخاص بك:

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";
```
   
##  الخطوة 2: قم بإنشاء مثيل جديد لملف`Document` class:

```csharp
using (Document doc = new Document())
{
  // كود هنا
}
```
   
## الخطوة 3: إضافة صفحة جديدة إلى المستند:

```csharp
doc.Pages.Add();
```
   
##  الخطوة 4: اضبط خاصية الطباعة على الوجهين على`DuplexFlipLongEdge`:

```csharp
doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
```
   
## الخطوة 5: احفظ المستند باسم الملف والصيغة المحددين:

```csharp
doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
```

### مثال على التعليمات البرمجية المصدر لـ Set Properties For Print Dialog باستخدام Aspose.PDF for .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document doc = new Document())
{
	doc.Pages.Add();
	doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
	doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
}
```

## خاتمة

يجعل Aspose.PDF for .NET من السهل تعيين خصائص مربع حوار الطباعة في ملفات PDF الخاصة بك. باتباع الدليل المفصل خطوة بخطوة أعلاه ، يمكنك تحسين ملفات PDF الخاصة بك بسرعة للطباعة.