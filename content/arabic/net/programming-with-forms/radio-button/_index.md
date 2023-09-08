---
title: زر الراديو
linktitle: زر الراديو
second_title: Aspose.PDF لمرجع .NET API
description: أضف أزرار الاختيار بسهولة إلى مستندات PDF الخاصة بك باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 220
url: /ar/net/programming-with-forms/radio-button/
---
سنوضح لك في هذا البرنامج التعليمي كيفية إضافة زر اختيار في مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح لك كود مصدر C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء مثيل لكائن المستند

إنشاء كائن مستند لإنشاء مستند PDF جديد:

```csharp
Document pdfDocument = new Document();
```

## الخطوة 3: إضافة صفحة

إضافة صفحة إلى مستند PDF:

```csharp
pdfDocument.Pages.Add();
```

## الخطوة 4: إنشاء مثيل لكائن RadioButtonField

إنشاء مثيل لكائن RadioButtonField مع تحديد رقم الصفحة كوسيطة:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## الخطوة 5: إضافة خيارات زر الاختيار

أضف خيارات زر الاختيار إلى كائن RadioButtonField عن طريق تحديد إحداثيات كل خيار مع كائن Rectangle:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## الخطوة 6: أضف زر الاختيار إلى النموذج

أضف زر الاختيار إلى كائن النموذج الخاص بالمستند:

```csharp
pdfDocument.Form.Add(radio);
```

## الخطوة 7: احفظ مستند PDF

احفظ مستند PDF الذي تم إنشاؤه:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لزر الراديو باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// إنشاء مثيل لكائن المستند
	Document pdfDocument = new Document();
	// إضافة صفحة إلى ملف PDF
	pdfDocument.Pages.Add();
	// إنشاء كائن RadioButtonField باستخدام رقم الصفحة كوسيطة
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// أضف خيار زر الاختيار الأول وحدد أيضًا أصله باستخدام كائن المستطيل
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// إضافة خيار زر الاختيار الثاني
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// أضف زر الاختيار لتكوين كائن كائن المستند
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// احفظ ملف PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إضافة زر اختيار في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة إنشاء زر اختيار ووضعه على صفحة معينة في مستند PDF الخاص بك.


### الأسئلة الشائعة

#### س: هل يمكنني تخصيص مظهر زر الاختيار، مثل حجمه ولونه؟

 ج: نعم، يمكنك تخصيص مظهر زر الاختيار باستخدام`Rectangle` إحداثيات الكائن لتحديد حجمه وموضعه. يتيح لك Aspose.PDF for .NET إمكانية ضبط مظهر زر الاختيار ليناسب احتياجاتك.

#### س: هل يمكنني إضافة أزرار اختيار متعددة مع مجموعات مختلفة في نفس الصفحة؟

ج: نعم، يمكنك إضافة أزرار اختيار متعددة مع مجموعات مختلفة في نفس الصفحة. يمكن أن يكون لكل مجموعة من أزرار الاختيار اسم فريد، ويمكن تحديد خيار واحد فقط داخل كل مجموعة في المرة الواحدة.

#### س: كيف يمكنني إضافة تسمية أو وصف نصي إلى خيارات زر الاختيار؟

 ج: لإضافة تسمية أو وصف نصي إلى خيارات زر الاختيار، يمكنك استخدام`TextStamp`فئة من Aspose.PDF لـ .NET لتراكب النص على مستند PDF بإحداثيات محددة.

#### س: هل يتوافق Aspose.PDF for .NET مع كافة إصدارات .NET Framework؟

ج: نعم، Aspose.PDF for .NET متوافق مع كافة إصدارات .NET Framework، بما في ذلك .NET Core و.NET Standard.

#### س: هل يمكنني التحكم برمجيًا في تحديد خيار زر الاختيار في مستند PDF؟

 ج: نعم، يمكنك التحكم برمجيًا في تحديد خيار زر الاختيار باستخدام الزر`IsSelected` ملكية`RadioButtonOption` فصل. تسمح لك هذه الخاصية بتعيين خيار محدد كما هو محدد.