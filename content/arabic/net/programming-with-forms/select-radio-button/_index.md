---
title: حدد زر الاختيار في مستند PDF
linktitle: حدد زر الاختيار في مستند PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحديد زر اختيار في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 250
url: /ar/net/programming-with-forms/select-radio-button/
---
فيما يلي برنامج تعليمي مفصل حول كيفية تحديد زر اختيار باستخدام Aspose.PDF لـ .NET. اتبع الخطوات التالية:

##  الخطوة 1: ابدأ بتحديد دليل مستنداتك عن طريق تحديد المسار في الملف`dataDir` variable.

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

### نموذج التعليمات البرمجية المصدر لـ Select Radio Button باستخدام Aspose.PDF لـ .NET 
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
	// احفظ ملف PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تحديد زر الاختيار باستخدام Aspose.PDF لـ .NET. باتباع الخطوات الموضحة أعلاه، يمكنك التعامل مع أزرار الاختيار وتعديلها في مستندات PDF الخاصة بك باستخدام Aspose.PDF for .NET.


### الأسئلة الشائعة

#### س: هل يمكنني تحديد أزرار اختيار متعددة في مجموعة باستخدام Aspose.PDF لـ .NET؟

ج: لا، أزرار الاختيار الموجودة في المجموعة مصممة بحيث تكون حصرية لبعضها البعض. يمكنك تحديد زر اختيار واحد فقط في كل مرة داخل المجموعة، وسيؤدي تحديد زر إلى إلغاء تحديد أي زر اختيار تم تحديده مسبقًا في نفس المجموعة تلقائيًا.

#### س: كيف يمكنني استرداد زر الاختيار المحدد في مجموعة باستخدام Aspose.PDF لـ .NET؟

 ج: لاسترداد زر الاختيار المحدد في مجموعة، يمكنك استخدام`Selected` ملكية`RadioButtonField` فصل. سيُرجع فهرس زر الاختيار المحدد داخل المجموعة.

#### س: هل يمكنني تخصيص مظهر زر الاختيار المحدد في مستند PDF؟

ج: نعم، يمكنك تخصيص مظهر زر الاختيار المحدد باستخدام Aspose.PDF لـ .NET. يمكنك تعديل اللون والحجم ونمط الحدود والسمات المرئية الأخرى لتتناسب مع المظهر المطلوب.

#### س: هل من الممكن إنشاء مجموعات أزرار اختيار جديدة برمجيًا باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يمكنك إنشاء مجموعات أزرار اختيار جديدة برمجيًا باستخدام Aspose.PDF لـ .NET. يمكنك إضافة أزرار اختيار جديدة إلى نموذج المستند وتحديد نفس اسم المجموعة لكل زر اختيار لإنشاء مجموعة جديدة.

#### س: هل يدعم Aspose.PDF for .NET العمل مع نماذج PDF التفاعلية؟

ج: نعم، يدعم Aspose.PDF for .NET بشكل كامل العمل مع نماذج PDF التفاعلية، بما في ذلك أزرار الاختيار وحقول النص ومربعات الاختيار وعناصر النموذج الأخرى. يمكنك بسهولة قراءة نماذج PDF تفاعلية وتعديلها وإنشائها باستخدام المكتبة.