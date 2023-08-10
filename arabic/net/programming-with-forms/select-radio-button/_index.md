---
title: حدد زر الراديو في مستند PDF
linktitle: حدد زر الراديو في مستند PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحديد زر اختيار في مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 250
url: /ar/net/programming-with-forms/select-radio-button/
---
فيما يلي برنامج تعليمي مفصل حول كيفية تحديد زر اختيار باستخدام Aspose.PDF for .NET. اتبع هذه الخطوات:

##  الخطوة 1: ابدأ بتحديد دليل المستندات الخاصة بك عن طريق تحديد المسار في ملف`dataDir` variable.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  الخطوة 2: افتح مستند PDF باستخدام ملف`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## الخطوة 3: احصل على حقل زر الاختيار من نموذج المستند.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## الخطوة 4: حدد فهرس زر الاختيار للاختيار من المجموعة.

```csharp
radioField. Selected = 2;
```

## الخطوة 5: قم بتعيين مسار الإخراج لملف PDF المحرر.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## الخطوة 6: احفظ ملف PDF المعدل.

```csharp
pdfDocument.Save(dataDir);
```

## الخطوة 7: عرض رسالة تأكيد وموقع الملف المحفوظ.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لتحديد زر الراديو باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// افتح المستند
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// احصل على حقل
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// حدد فهرس زر الاختيار من المجموعة
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	//احفظ ملف PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية تحديد زر اختيار باستخدام Aspose.PDF لـ .NET. باتباع الخطوات الموضحة أعلاه ، يمكنك معالجة وتعديل أزرار الاختيار في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.


### التعليمات

#### س: هل يمكنني تحديد عدة أزرار اختيار في مجموعة باستخدام Aspose.PDF for .NET؟

ج: لا ، تم تصميم أزرار الاختيار في مجموعة بحيث تكون حصرية بشكل متبادل. يمكنك تحديد زر اختيار واحد فقط في كل مرة داخل المجموعة ، ويؤدي تحديد أحد الأزرار تلقائيًا إلى إلغاء تحديد أي زر اختيار تم تحديده مسبقًا في نفس المجموعة.

#### س: كيف يمكنني استرداد زر الاختيار المحدد في مجموعة باستخدام Aspose.PDF for .NET؟

 ج: لاسترداد زر الاختيار المحدد في مجموعة ، يمكنك استخدام`Selected` ممتلكات`RadioButtonField`فصل. سيعيد فهرس زر الاختيار المحدد داخل المجموعة.

#### س: هل يمكنني تخصيص مظهر زر الاختيار المحدد في مستند PDF؟

ج: نعم ، يمكنك تخصيص مظهر زر الاختيار المحدد باستخدام Aspose.PDF for .NET. يمكنك تعديل اللون والحجم ونمط الحدود والسمات المرئية الأخرى لتتناسب مع المظهر الذي تريده.

#### س: هل من الممكن إنشاء مجموعات أزرار خيار جديدة برمجيًا باستخدام Aspose.PDF for .NET؟

ج: نعم ، يمكنك إنشاء مجموعات أزرار خيار جديدة برمجيًا باستخدام Aspose.PDF for .NET. يمكنك إضافة أزرار اختيار جديدة إلى نموذج المستند وتحديد نفس اسم المجموعة لكل زر اختيار لإنشاء مجموعة جديدة.

#### س: هل يدعم Aspose.PDF for .NET العمل مع نماذج PDF التفاعلية؟

ج: نعم ، يدعم Aspose.PDF for .NET بشكل كامل العمل مع نماذج PDF التفاعلية ، بما في ذلك أزرار الاختيار وحقول النص ومربعات الاختيار وعناصر النموذج الأخرى. يمكنك بسهولة قراءة وتعديل وإنشاء نماذج PDF تفاعلية باستخدام المكتبة.