---
title: أزرار الراديو أفقيًا وعموديًا
linktitle: أزرار الراديو أفقيًا وعموديًا
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: قم بإنشاء أزرار راديو أفقية ورأسية بسهولة في مستندات PDF الخاصة بك باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 180
url: /ar/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
في هذا البرنامج التعليمي، سنوضح لك كيفية إنشاء أزرار اختيار مرتبة أفقيًا ورأسيًا في مستند PDF باستخدام Aspose.PDF لـ .NET. وسنشرح لك التعليمات البرمجية المصدرية بلغة C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقمت بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: تحميل المستند

قم بتحميل مستند PDF الموجود:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## الخطوة 3: تخصيص خيارات أزرار الاختيار

تخصيص خيارات أزرار الاختيار عن طريق تعيين الخصائص التالية:

```csharp
formEditor. RadioGap = 4; // المسافة بين خياري زر الاختيار
formEditor. RadioHoriz = true; //التخطيط الأفقي لأزرار الراديو
formEditor.RadioButtonItemSize = 20; // حجم أزرار الراديو
formEditor.Facade.BorderWidth = 1; // عرض حدود زر الاختيار
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // لون حدود زر الاختيار
```

## الخطوة 4: إضافة أزرار الاختيار الأفقية

إضافة أزرار الاختيار مرتبة أفقياً عن طريق تحديد الخيارات وموضع الحقل:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## الخطوة 5: إضافة أزرار الراديو العمودية

أضف أزرار الاختيار مرتبة عموديا عن طريق تحديد الخيارات وموضع الحقل:

```csharp
formEditor. RadioHoriz = false; // التخطيط العمودي لأزرار الراديو
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## الخطوة 6: احفظ المستند

حفظ مستند PDF المعدل:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### عينة من كود المصدر لأزرار الراديو الأفقية والرأسية باستخدام Aspose.PDF لـ .NET 
```csharp
try
{
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// تحميل المستند المحفوظ مسبقًا
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap هي المسافة بين خيارين لزر الاختيار.
	formEditor.RadioGap = 4;
	// إضافة زر اختيار أفقي
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize إذا كان حجم عنصر زر الراديو.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// إضافة زر اختيار آخر يقع عموديًا
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// حفظ مستند PDF
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء أزرار اختيار مرتبة أفقيًا ورأسيًا في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة تخصيص تخطيط أزرار الاختيار وإضافتها إلى مستندات PDF الخاصة بك باستخدام Aspose.PDF.

### الأسئلة الشائعة

#### س: ما هي أزرار الاختيار المرتبة أفقيًا ورأسيًا في مستند PDF؟

أ: تشير أزرار الاختيار المرتبة أفقيًا ورأسيًا في مستند PDF إلى اتجاه تخطيط خيارات أزرار الاختيار. يضع التخطيط الأفقي خيارات أزرار الاختيار جنبًا إلى جنب، مما يسمح للمستخدمين بإجراء تحديد من اليسار إلى اليمين. من ناحية أخرى، يضع التخطيط الرأسي خيارات أزرار الاختيار فوق بعضها البعض، مما يتيح للمستخدمين إجراء تحديد من أعلى إلى أسفل.

#### س: كيف يمكنني تخصيص مظهر خيارات أزرار الاختيار في Aspose.PDF لـ .NET؟

ج: يمكنك تخصيص مظهر خيارات أزرار الاختيار في Aspose.PDF لـ .NET من خلال ضبط العديد من الخصائص. توفر واجهة برمجة التطبيقات خيارات لتعيين المسافة بين خياري أزرار الاختيار (`RadioGap`), اتجاه التخطيط (`RadioHoriz`)، حجم عناصر أزرار الاختيار (`RadioButtonItemSize`)، وعرض الحدود ولون أزرار الاختيار، والمزيد.

#### س: هل يمكنني إضافة أزرار الاختيار الأفقية والرأسية إلى نفس مستند PDF؟

ج: نعم، يمكنك إضافة أزرار اختيار أفقية ورأسية إلى نفس مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر النموذجي المقدم في البرنامج التعليمي كيفية إضافة أزرار اختيار مرتبة أفقيًا أولاً ثم إضافة مجموعة أخرى من أزرار الاختيار مرتبة رأسيًا إلى نفس مستند PDF.

#### س: هل يمكنني تعيين خيارات أزرار الاختيار المختلفة لكل مجموعة من أزرار الاختيار؟

 ج: نعم، يمكنك تعيين خيارات أزرار الراديو المختلفة لكل مجموعة من أزرار الراديو. يجب أن يكون لكل مجموعة خيار فريد.`RadioButtonField` الكائن، و`RadioButtonOptionField` يجب أن تتشارك الكائنات الموجودة داخل كل مجموعة في نفس الصفحة والأسماء الفريدة لخياراتها. وهذا يضمن أن أزرار الاختيار داخل كل مجموعة تعمل بشكل صحيح، وأن الاختيارات متبادلة الاستبعاد.

#### س: هل يتم دعم إعدادات تخطيط ومظهر أزرار الاختيار في جميع برامج عرض PDF والتطبيقات؟

ج: نعم، يتم دعم إعدادات تخطيط ومظهر أزرار الاختيار في جميع برامج عرض ملفات PDF والتطبيقات المتوافقة مع المعايير. تحدد مواصفات PDF أزرار الاختيار وسماتها المختلفة، مما يجعلها معروفة عالميًا بتنسيق PDF. ومع ذلك، من الضروري اختبار مظهر وسلوك أزرار الاختيار في برامج عرض ملفات PDF المختلفة لضمان عرض متسق عبر منصات مختلفة.