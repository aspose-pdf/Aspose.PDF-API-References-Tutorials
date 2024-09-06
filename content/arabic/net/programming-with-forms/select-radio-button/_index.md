---
title: تحديد زر الاختيار في مستند PDF
linktitle: تحديد زر الاختيار في مستند PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تحديد زر الاختيار في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 250
url: /ar/net/programming-with-forms/select-radio-button/
---
فيما يلي برنامج تعليمي مفصل حول كيفية تحديد زر اختيار باستخدام Aspose.PDF لـ .NET. اتبع الخطوات التالية:

##  الخطوة 1: ابدأ بتحديد دليل مستنداتك من خلال تحديد المسار في`dataDir` variable.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  الخطوة 2: افتح مستند PDF باستخدام`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## الخطوة 3: الحصول على حقل زر الاختيار من نموذج المستند.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## الخطوة 4: حدد فهرس زر الاختيار الذي تريد تحديده من المجموعة.

```csharp
radioField. Selected = 2;
```

## الخطوة 5: قم بتعيين مسار الإخراج لملف PDF المحرر.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## الخطوة 6: احفظ ملف PDF المعدّل.

```csharp
pdfDocument.Save(dataDir);
```

## الخطوة 7: عرض رسالة تأكيد وموقع الملف المحفوظ.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### عينة من كود المصدر لزر الاختيار باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// فتح المستند
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// احصل على حقل
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// تحديد فهرس زر الاختيار من المجموعة
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// حفظ ملف PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تحديد زر اختيار باستخدام Aspose.PDF for .NET. باتباع الخطوات الموضحة أعلاه، يمكنك التعامل مع أزرار الاختيار وتعديلها في مستندات PDF باستخدام Aspose.PDF for .NET.


### الأسئلة الشائعة

#### س: هل يمكنني تحديد أزرار اختيار متعددة في مجموعة باستخدام Aspose.PDF لـ .NET؟

ج: لا، تم تصميم أزرار الاختيار في المجموعة بحيث تكون متبادلة الحصر. لا يمكنك تحديد سوى زر اختيار واحد في كل مرة ضمن المجموعة، وتحديد أحد هذه الأزرار سيؤدي تلقائيًا إلى إلغاء تحديد أي زر اختيار تم تحديده مسبقًا في نفس المجموعة.

#### س: كيف يمكنني استرداد زر الاختيار المحدد في مجموعة باستخدام Aspose.PDF لـ .NET؟

 أ: لاسترداد زر الاختيار المحدد في مجموعة، يمكنك استخدام`Selected` ممتلكات`RadioButtonField` سيتم إرجاع فهرس زر الاختيار المحدد ضمن المجموعة.

#### س: هل يمكنني تخصيص مظهر زر الاختيار المحدد في مستند PDF؟

ج: نعم، يمكنك تخصيص مظهر زر الاختيار المحدد باستخدام Aspose.PDF لـ .NET. يمكنك تعديل لونه وحجمه ونمط حدوده وغير ذلك من السمات المرئية لتتناسب مع المظهر الذي تريده.

#### س: هل من الممكن إنشاء مجموعات أزرار اختيارية جديدة برمجيًا باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يمكنك إنشاء مجموعات أزرار اختيار جديدة برمجيًا باستخدام Aspose.PDF for .NET. يمكنك إضافة أزرار اختيار جديدة إلى نموذج المستند وتحديد نفس اسم المجموعة لكل زر اختيار لإنشاء مجموعة جديدة.

#### س: هل يدعم Aspose.PDF لـ .NET العمل مع نماذج PDF التفاعلية؟

ج: نعم، يدعم Aspose.PDF for .NET العمل بشكل كامل مع نماذج PDF التفاعلية، بما في ذلك أزرار الاختيار وحقول النص ومربعات الاختيار وعناصر النموذج الأخرى. يمكنك بسهولة قراءة وتعديل وإنشاء نماذج PDF التفاعلية باستخدام المكتبة.