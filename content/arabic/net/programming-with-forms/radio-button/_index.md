---
title: زر الراديو
linktitle: زر الراديو
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك بسهولة إضافة أزرار الاختيار إلى مستندات PDF الخاصة بك باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 220
url: /ar/net/programming-with-forms/radio-button/
---
في هذا البرنامج التعليمي، سنوضح لك كيفية إضافة زر اختيار في مستند PDF باستخدام Aspose.PDF لـ .NET. وسنشرح لك التعليمات البرمجية المصدرية للغة C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقمت بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء كائن مستند

إنشاء كائن مستند لإنشاء مستند PDF جديد:

```csharp
Document pdfDocument = new Document();
```

## الخطوة 3: إضافة صفحة

إضافة صفحة إلى مستند PDF:

```csharp
pdfDocument.Pages.Add();
```

## الخطوة 4: إنشاء كائن RadioButtonField

إنشاء كائن RadioButtonField مع تحديد رقم الصفحة كوسيطة:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## الخطوة 5: إضافة خيارات أزرار الاختيار

أضف خيارات أزرار الاختيار إلى كائن RadioButtonField من خلال تحديد إحداثيات كل خيار باستخدام كائن Rectangle:

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

### عينة من كود المصدر لزر الراديو باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// إنشاء كائن مستند
	Document pdfDocument = new Document();
	// إضافة صفحة إلى ملف PDF
	pdfDocument.Pages.Add();
	// إنشاء كائن RadioButtonField مع رقم الصفحة كحجة
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// أضف خيار زر الاختيار الأول وحدد أيضًا أصله باستخدام كائن المستطيل
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// إضافة خيار زر الاختيار الثاني
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// إضافة زر اختياري إلى كائن النموذج الخاص بكائن المستند
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// حفظ ملف PDF
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

 ج: نعم، يمكنك تخصيص مظهر زر الاختيار باستخدام`Rectangle` يتيح لك Aspose.PDF لـ .NET ضبط مظهر أزرار الاختيار لتناسب احتياجاتك.

#### س: هل يمكنني إضافة أزرار اختيار متعددة بمجموعات مختلفة على نفس الصفحة؟

ج: نعم، يمكنك إضافة أزرار اختيار متعددة بمجموعات مختلفة على نفس الصفحة. يمكن أن يكون لكل مجموعة من أزرار الاختيار اسم فريد، ولا يمكن تحديد سوى خيار واحد ضمن كل مجموعة في كل مرة.

#### س: كيف يمكنني إضافة تسمية أو وصف نصي إلى خيارات أزرار الاختيار؟

 أ: لإضافة تسمية أو وصف نصي إلى خيارات زر الاختيار، يمكنك استخدام`TextStamp`فئة من Aspose.PDF لـ .NET لتراكب النص على مستند PDF في إحداثيات محددة.

#### س: هل Aspose.PDF for .NET متوافق مع كافة إصدارات .NET Framework؟

ج: نعم، يعد Aspose.PDF لـ .NET متوافقًا مع جميع إصدارات .NET Framework، بما في ذلك .NET Core و.NET Standard.

#### س: هل يمكنني التحكم برمجيًا في اختيار خيار زر الراديو في مستند PDF؟

 ج: نعم، يمكنك التحكم برمجيًا في اختيار خيار زر الراديو باستخدام`IsSelected` ممتلكات`RadioButtonOption` تسمح لك هذه الخاصية بتعيين خيار معين كمحدد.