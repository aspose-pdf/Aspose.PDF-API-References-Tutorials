---
title: تعيين التسمية التوضيحية لزر الراديو
linktitle: تعيين التسمية التوضيحية لزر الراديو
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF لـ .NET لتعيين التسمية التوضيحية لزر الاختيار في نموذج PDF.
type: docs
weight: 280
url: /ar/net/programming-with-forms/set-radio-button-caption/
---
سنشرح في هذا الدليل خطوة بخطوة كيفية استخدام مكتبة Aspose.PDF لـ .NET لتحديد التسمية التوضيحية لزر الاختيار في نموذج PDF. سنوضح لك كيفية الوصول إلى حقل زر الاختيار، وإنشاء خيار زر اختيار جديد، وتخصيص التسمية التوضيحية للزر.

## الخطوة 1: تكوين دليل المستندات

 الخطوة الأولى هي تكوين دليل المستند حيث يوجد نموذج PDF الذي تريد العمل عليه. يمكنك استخدام ال`dataDir` متغير لتحديد مسار الدليل.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 2: تحميل نموذج PDF المصدر

 في هذه الخطوة، سنقوم بتحميل نموذج PDF المصدر باستخدام ملف`Aspose.Pdf.Facades.Form` فئة Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

تأكد من وجود ملف PDF الذي يحتوي على النموذج في دليل المستندات المحدد.

## الخطوة 3: تحرير التسمية التوضيحية لزر الاختيار

سنقوم بالتنقل خلال أسماء حقول النموذج ونبحث عن حقول زر الاختيار. إذا تم العثور على حقل مطابق، فسنقوم بإنشاء خيار زر اختيار جديد مع تسمية توضيحية مخصصة وإضافته إلى الحقل الموجود.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// إنشاء كائن TextParagraph
TextParagraph par = new TextParagraph();
// ضبط موضع الفقرة
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// تحديد وضع التفاف الكلمات
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// أضف TextFragment الجديد إلى الفقرة
par.AppendLine(updatedFragment);
// أضف TextParagraph باستخدام TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

قم بتخصيص زر اختيار التسمية التوضيحية والإعدادات الأخرى حسب الحاجة.

## الخطوة 4: حفظ ملف PDF الناتج

 الآن بعد أن انتهينا من تعديل التسمية التوضيحية لزر الاختيار، يمكننا حفظ ملف PDF الناتج باستخدام ملف`Save` طريقة`Document` فصل.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

تأكد من تحديد المسار الكامل واسم الملف لملف PDF الناتج.

### نموذج التعليمات البرمجية المصدر لـ Set Radio Button Caption باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تحميل نموذج PDF المصدر
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// إنشاء كائن TextParagraph
		TextParagraph par = new TextParagraph();
		// ضبط موضع الفقرة
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// تحديد وضع التفاف الكلمات
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// إضافة TextFragment جديد إلى الفقرة
		par.AppendLine(updatedFragment);
		// أضف TextParagraph باستخدام TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## خاتمة

في هذا الدليل، تعلمنا كيفية استخدام مكتبة Aspose.PDF لـ .NET لتعيين التسمية التوضيحية لزر الاختيار في نموذج PDF. باتباع الخطوات الموضحة، يمكنك تخصيص خيارات زر الاختيار وتغيير التسمية التوضيحية حسب الحاجة. لا تتردد في استكشاف المزيد من ميزات Aspose.PDF لـ .NET لتوسيع إمكانيات معالجة ملفات PDF.

### الأسئلة الشائعة

#### س: هل يمكنني استخدام Aspose.PDF لـ .NET لتعيين التسميات التوضيحية لأزرار الاختيار في نموذج PDF؟

ج: نعم، يمكنك استخدام Aspose.PDF لـ .NET لتعيين التسميات التوضيحية لأزرار الاختيار في نموذج PDF. يوضح نموذج التعليمات البرمجية المصدر المقدم كيفية الوصول إلى حقل زر الاختيار، وإنشاء خيار زر اختيار جديد مع تسمية توضيحية مخصصة، وتحديث الحقل الحالي.

#### س: كيف يمكنني تخصيص مظهر التسمية التوضيحية لزر الاختيار، مثل حجم الخط ولونه؟

 ج: يمكنك تخصيص مظهر التسمية التوضيحية لزر الاختيار عن طريق ضبط خصائص`TextFragment` تستخدم للتسمية التوضيحية. على سبيل المثال، يمكنك تعيين الخط وحجم الخط واللون وتباعد الأسطر وخيارات تنسيق النص الأخرى.

#### س: هل من الممكن إضافة خيارات متعددة لأزرار الاختيار مع تسميات توضيحية مختلفة لمجموعة أزرار اختيار واحدة؟

ج: نعم، يمكنك إضافة خيارات متعددة لأزرار الاختيار مع تسميات توضيحية مختلفة لمجموعة أزرار اختيار واحدة. سيمثل كل خيار اختيارًا مختلفًا، ويمكن للمستخدمين تحديد خيار واحد فقط من المجموعة.

#### س: هل يمكنني استخدام Aspose.PDF لـ .NET لتعديل حقول النموذج الأخرى في مستند PDF؟

ج: نعم، يوفر Aspose.PDF for .NET مجموعة شاملة من الميزات للتعامل مع حقول النماذج المختلفة في مستند PDF، مثل الحقول النصية ومربعات الاختيار والقوائم المنسدلة والمزيد. يمكنك استخدام المكتبة لتعيين القيم وتعديل المظاهر وإضافة التفاعل إلى حقول النموذج.

#### س: هل يدعم Aspose.PDF for .NET العمل مع ملفات PDF التي تم إنشاؤها من مصادر أخرى، مثل المستندات الممسوحة ضوئيًا؟

ج: نعم، يدعم Aspose.PDF for .NET العمل مع ملفات PDF التي تم إنشاؤها من مصادر مختلفة، بما في ذلك المستندات الممسوحة ضوئيًا. توفر المكتبة إمكانات التعرف الضوئي على الحروف (OCR) لاستخراج النص من ملفات PDF الممسوحة ضوئيًا ومعالجة المحتوى برمجيًا.