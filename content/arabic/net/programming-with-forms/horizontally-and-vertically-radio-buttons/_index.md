---
title: أزرار الراديو أفقيًا وعموديًا
linktitle: أزرار الراديو أفقيًا وعموديًا
second_title: Aspose.PDF لمرجع .NET API
description: قم بإنشاء أزرار اختيار أفقية ورأسية بسهولة في مستندات PDF الخاصة بك باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 180
url: /ar/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
سنوضح لك في هذا البرنامج التعليمي كيفية إنشاء أزرار اختيار مرتبة أفقيًا وعموديًا في مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح لك كود مصدر C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

قم بتحميل مستند PDF الموجود:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## الخطوة 3: تخصيص خيارات زر الاختيار

قم بتخصيص خيارات زر الاختيار عن طريق تعيين الخصائص التالية:

```csharp
formEditor. RadioGap = 4; // المسافة بين خيارين لزر الاختيار
formEditor. RadioHoriz = true; //التخطيط الأفقي لأزرار الاختيار
formEditor.RadioButtonItemSize = 20; // حجم أزرار الراديو
formEditor.Facade.BorderWidth = 1; // عرض حدود زر الاختيار
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // لون حدود زر الاختيار
```

## الخطوة 4: إضافة أزرار الراديو الأفقية

أضف أزرار الاختيار مرتبة أفقيًا من خلال تحديد الخيارات وموضع الحقل:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## الخطوة 5: إضافة أزرار الاختيار العمودية

أضف أزرار الاختيار مرتبة عموديًا من خلال تحديد الخيارات وموضع الحقل:

```csharp
formEditor. RadioHoriz = false; // التخطيط الرأسي لأزرار الاختيار
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## الخطوة 6: احفظ المستند

احفظ مستند PDF المعدل:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لأزرار الاختيار الأفقية والعمودية باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// قم بتحميل المستند المحفوظ مسبقًا
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap هي المسافة بين خيارين لزر الاختيار.
	formEditor.RadioGap = 4;
	// إضافة زر الاختيار الأفقي
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize إذا كان حجم عنصر زر الاختيار.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// أضف زر اختيار آخر يقع عموديًا
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// احفظ مستند PDF
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء أزرار اختيار مرتبة أفقيًا وعموديًا في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة تخصيص تخطيط أزرار الاختيار وإضافتها إلى مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### الأسئلة الشائعة

#### س: ما هي أزرار الاختيار المرتبة أفقيًا وعموديًا في مستند PDF؟

ج: تشير أزرار الاختيار المرتبة أفقيًا وعموديًا في مستند PDF إلى اتجاه تخطيط خيارات زر الاختيار. يضع التخطيط الأفقي خيارات زر الاختيار جنبًا إلى جنب، مما يسمح للمستخدمين بالاختيار من اليسار إلى اليمين. من ناحية أخرى، يعمل التخطيط الرأسي على تكديس خيارات زر الاختيار فوق بعضها البعض، مما يمكّن المستخدمين من الاختيار من الأعلى إلى الأسفل.

#### س: كيف يمكنني تخصيص مظهر خيارات زر الاختيار في Aspose.PDF لـ .NET؟

ج: يمكنك تخصيص مظهر خيارات زر الاختيار في Aspose.PDF لـ .NET عن طريق ضبط العديد من الخصائص. توفر واجهة برمجة التطبيقات (API) خيارات لتعيين المسافة بين خيارين لزر الاختيار (`RadioGap`)، اتجاه التخطيط (`RadioHoriz`)، وحجم عناصر زر الاختيار (`RadioButtonItemSize`)، وعرض الحدود ولون أزرار الاختيار، والمزيد.

#### س: هل يمكنني إضافة أزرار الاختيار الأفقية والرأسية إلى نفس مستند PDF؟

ج: نعم، يمكنك إضافة أزرار الاختيار الأفقية والرأسية إلى نفس مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح نموذج التعليمات البرمجية المصدر الموجود في البرنامج التعليمي كيفية إضافة أزرار الاختيار مرتبة أفقيًا أولاً ثم إضافة مجموعة أخرى من أزرار الاختيار مرتبة رأسيًا إلى نفس مستند PDF.

#### س: هل يمكنني تعيين خيارات مختلفة لأزرار الاختيار لكل مجموعة من أزرار الاختيار؟

 ج: نعم، يمكنك تعيين خيارات مختلفة لأزرار الاختيار لكل مجموعة من أزرار الاختيار. يجب أن يكون لكل مجموعة فريدة من نوعها`RadioButtonField` الكائن، و`RadioButtonOptionField` يجب أن تشترك الكائنات الموجودة داخل كل مجموعة في نفس الصفحة والأسماء الفريدة لخياراتها. وهذا يضمن أن أزرار الاختيار الموجودة داخل كل مجموعة تعمل بشكل صحيح، وأن التحديدات حصرية بشكل متبادل.

#### س: هل يتم دعم إعدادات التخطيط والمظهر لأزرار الاختيار في جميع برامج عرض وتطبيقات PDF؟

ج: نعم، يتم دعم إعدادات التخطيط والمظهر لأزرار الاختيار في جميع برامج عرض وتطبيقات PDF المتوافقة مع المعايير. تحدد مواصفات PDF أزرار الاختيار وخصائصها المختلفة، مما يجعلها معترف بها عالميًا بتنسيق PDF. ومع ذلك، من الضروري اختبار مظهر وسلوك أزرار الاختيار في برامج عرض PDF المختلفة لضمان العرض المتسق عبر الأنظمة الأساسية المختلفة.