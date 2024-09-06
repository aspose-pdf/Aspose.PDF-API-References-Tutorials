---
title: تعيين تسمية توضيحية لأزرار الاختيار
linktitle: تعيين تسمية توضيحية لأزرار الاختيار
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخدام Aspose.PDF لـ .NET لتعيين التسمية التوضيحية لزر الاختيار في نموذج PDF.
type: docs
weight: 280
url: /ar/net/programming-with-forms/set-radio-button-caption/
---
في هذا الدليل، سنشرح خطوة بخطوة كيفية استخدام مكتبة Aspose.PDF لـ .NET لتحديد تسمية توضيحية لزر الاختيار في نموذج PDF. وسنوضح لك كيفية الوصول إلى حقل زر الاختيار وإنشاء خيار زر اختيار جديد وتخصيص تسمية توضيحية للزر.

## الخطوة 1: تكوين دليل المستندات

 الخطوة الأولى هي تكوين دليل المستندات الذي يوجد به نموذج PDF الذي تريد العمل عليه. يمكنك استخدام`dataDir` متغير لتحديد مسار الدليل.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 تأكد من الاستبدال`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 2: تحميل نموذج PDF المصدر

 في هذه الخطوة، سنقوم بتحميل نموذج PDF المصدر باستخدام`Aspose.Pdf.Facades.Form` فئة Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

تأكد من أن ملف PDF الذي يحتوي على النموذج موجود في دليل المستندات المحدد.

## الخطوة 3: تحرير تسمية زر الاختيار

سنبحث في أسماء حقول النموذج عن حقول أزرار الاختيار. إذا تم العثور على حقل مطابق، فسنقوم بإنشاء خيار زر اختيار جديد مع تسمية توضيحية مخصصة وإضافته إلى الحقل الموجود.

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
// تعيين موضع الفقرة
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

قم بتخصيص زر الاختيار الخاص بالتسمية التوضيحية والإعدادات الأخرى حسب الحاجة.

## الخطوة 4: حفظ ملف PDF الناتج

 الآن بعد أن انتهينا من تعديل تسمية زر الاختيار، يمكننا حفظ ملف PDF الناتج باستخدام`Save` طريقة`Document` فصل.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

تأكد من تحديد المسار الكامل واسم الملف لملف PDF الناتج.

### عينة من كود المصدر لتعيين تسمية توضيحية لأزرار الراديو باستخدام Aspose.PDF لـ .NET 
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
		// تعيين موضع الفقرة
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// تحديد وضع التفاف الكلمات
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// إضافة جزء نصي جديد إلى الفقرة
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

في هذا الدليل، تعلمنا كيفية استخدام مكتبة Aspose.PDF لـ .NET لتعيين التسمية التوضيحية لزر الاختيار في نموذج PDF. باتباع الخطوات الموضحة، يمكنك تخصيص خيارات زر الاختيار وتغيير التسمية التوضيحية حسب الحاجة. لا تتردد في استكشاف ميزات Aspose.PDF لـ .NET بشكل أكبر لتوسيع إمكانيات التعامل مع ملفات PDF.

### الأسئلة الشائعة

#### س: هل يمكنني استخدام Aspose.PDF لـ .NET لتعيين تسميات توضيحية لأزرار الاختيار في نموذج PDF؟

ج: نعم، يمكنك استخدام Aspose.PDF لـ .NET لتعيين تسميات توضيحية لأزرار الاختيار في نموذج PDF. يوضح كود المصدر المقدم كيفية الوصول إلى حقل زر الاختيار وإنشاء خيار زر اختيار جديد مع تسمية توضيحية مخصصة وتحديث الحقل الحالي.

#### س: كيف يمكنني تخصيص مظهر تسمية زر الاختيار، مثل حجم الخط ولونه؟

 أ: يمكنك تخصيص مظهر تسمية زر الاختيار عن طريق ضبط خصائص`TextFragment` تُستخدم للتسمية التوضيحية. على سبيل المثال، يمكنك ضبط الخط وحجمه ولونه ومسافة السطور وخيارات تنسيق النص الأخرى.

#### س: هل من الممكن إضافة خيارات أزرار الاختيار المتعددة مع تسميات توضيحية مختلفة لمجموعة أزرار الاختيار الواحدة؟

ج: نعم، يمكنك إضافة خيارات متعددة لأزرار الاختيار مع تسميات توضيحية مختلفة إلى مجموعة أزرار اختيار واحدة. سيمثل كل خيار خيارًا مختلفًا، ويمكن للمستخدمين تحديد خيار واحد فقط من المجموعة.

#### س: هل يمكنني استخدام Aspose.PDF لـ .NET لتعديل حقول النموذج الأخرى في مستند PDF؟

ج: نعم، توفر Aspose.PDF for .NET مجموعة شاملة من الميزات للتعامل مع حقول النماذج المختلفة في مستند PDF، مثل حقول النص ومربعات الاختيار والقوائم المنسدلة والمزيد. يمكنك استخدام المكتبة لتعيين القيم وتعديل المظاهر وإضافة التفاعل إلى حقول النماذج.

#### س: هل يدعم Aspose.PDF لـ .NET العمل مع ملفات PDF التي تم إنشاؤها من مصادر أخرى، مثل المستندات الممسوحة ضوئيًا؟

ج: نعم، يدعم Aspose.PDF for .NET العمل مع ملفات PDF التي تم إنشاؤها من مصادر مختلفة، بما في ذلك المستندات الممسوحة ضوئيًا. توفر المكتبة إمكانيات التعرف الضوئي على الحروف (OCR) لاستخراج النص من ملفات PDF الممسوحة ضوئيًا ومعالجة المحتوى برمجيًا.