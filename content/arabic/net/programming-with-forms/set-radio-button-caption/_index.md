---
title: تعيين تسمية توضيحية لأزرار الاختيار
linktitle: تعيين تسمية توضيحية لأزرار الاختيار
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية تعيين تسميات أزرار الاختيار في ملفات PDF باستخدام Aspose.PDF لـ .NET. يرشدك هذا الدليل خطوة بخطوة خلال تحميل نماذج PDF وتعديلها وحفظها.
type: docs
weight: 280
url: /ar/net/programming-with-forms/set-radio-button-caption/
---
## مقدمة

إذا كنت تتعمق في معالجة ملفات PDF باستخدام Aspose.PDF لـ .NET، فأنت على موعد مع متعة لا تُنسى! اليوم، نركز على ميزة عملية: تعيين تسميات أزرار الاختيار في نماذج PDF الخاصة بك. تعد أزرار الاختيار ضرورية لنماذج المستخدم حيث تحتاج إلى الاختيار من مجموعة من الخيارات. تخيلها على أنها أسئلة متعددة الخيارات حيث يُسمح بإجابة واحدة فقط. سيرشدك هذا البرنامج التعليمي خلال عملية تحديث تسميات أزرار الاختيار في نموذج PDF، بحيث تكون مستنداتك تفاعلية وسهلة الاستخدام. 

## المتطلبات الأساسية

قبل الغوص في الكود، هناك بعض الأشياء التي ستحتاج إلى التأكد من توفرها لديك:

1. Aspose.PDF لـ .NET: تأكد من تثبيت مكتبة Aspose.PDF. ستساعدك هذه المكتبة على التعامل مع ملفات PDF برمجيًا.
2. بيئة التطوير: يجب أن يكون لديك بيئة تطوير .NET مهيأة، مثل Visual Studio.
3. نموذج نموذج PDF: لهذا البرنامج التعليمي، ستحتاج إلى نموذج نموذج PDF يحتوي على أزرار اختيار. يمكنك استخدام أي نموذج PDF موجود أو إنشاء نموذج جديد يحتوي على أزرار اختيار.
4. المعرفة الأساسية بلغة C#: يفترض هذا الدليل أن لديك فهمًا أساسيًا لمفاهيم برمجة C# و.NET.

 إذا لم تقم بتثبيت Aspose.PDF لـ .NET بعد أو كنت بحاجة إلى ترخيص مؤقت، فيمكنك[تحميله هنا](https://releases.aspose.com/pdf/net/) أو[احصل على رخصة مؤقتة](https://purchase.aspose.com/temporary-license/).

## استيراد الحزم

للبدء، تحتاج إلى استيراد الحزم اللازمة في مشروع C# الخاص بك. فيما يلي كيفية تضمين مكتبة Aspose.PDF:

```csharp
using System;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
using Aspose.Pdf.Text;
```

تأكد من إضافة هذه الحزم إلى مشروعك عبر NuGet أو الطريقة المفضلة لديك.

## الخطوة 1: تحميل نموذج PDF

 أولاً، عليك تحميل نموذج PDF الذي يحتوي على أزرار الاختيار.`Aspose.Pdf.Facades.Form`يتم استخدام class لهذا الغرض. إليك كيفية القيام بذلك:

```csharp
// قم بتحديد المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

// تحميل نموذج PDF المصدر
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
```

في مقتطف الكود هذا:
- `dataDir` يحدد المسار الذي يتواجد فيه ملف PDF الخاص بك.
- `Form` يتم استخدام الفئة للتفاعل مع حقول النموذج داخل ملف PDF.
- `Document` توفر الفئة إمكانية الوصول إلى صفحات مستند PDF.

## الخطوة 2: التكرار خلال حقول أزرار الاختيار

بعد ذلك، ستحتاج إلى تكرار الحقول الموجودة في النموذج لتحديد حقول أزرار الاختيار ومعالجتها:

```csharp
foreach (var item in form1.FieldNames)
{
    Console.WriteLine(item.ToString());
    Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
```

في هذه الحلقة:
- `FieldNames` يوفر قائمة بجميع أسماء الحقول في ملف PDF.
- `GetButtonOptionValues(item)` يسترجع الخيارات المتاحة لكل زر اختيار.

## الخطوة 3: تعديل خيارات أزرار الاختيار

 بمجرد تحديد حقول أزرار الاختيار، يمكنك تعديل خياراتها. للقيام بذلك، تحتاج إلى تحويل الحقل إلى`RadioButtonField` وتحديث خياراته:

```csharp
    if (item.Contains("radio1"))
    {
        Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
        Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
        fieldoption.OptionName = "Yes";
        fieldoption.PartialName = "Yesname";
```

هنا:
- نتحقق مما إذا كان اسم الحقل يحتوي على "radio1" لتحديد حقل زر الاختيار المحدد الذي نريد تعديله.
- `RadioButtonField`يتم إرسالها من حقول النموذج لإجراء تعديلات محددة.

## الخطوة 4: تعيين التسمية التوضيحية لزر الاختيار

 لتعيين أو تحديث التسمية التوضيحية لزر الاختيار، ستحتاج إلى إنشاء`TextFragment` و استخدم`TextBuilder` لوضعه في المكان المطلوب:

```csharp
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
```

في هذا الجزء:
- `TextFragment` يتم استخدامه لتحديد النص ومظهره.
- `TextParagraph` يساعد على تحديد موضع النص وتنسيقه.
- `TextBuilder` يضيف النص إلى الصفحة المحددة من ملف PDF.

## الخطوة 5: احفظ ملف PDF المحدث

وأخيرًا، احفظ ملف PDF المحدث في ملف جديد:

```csharp
        field0.DeleteOption("item1");
    }
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

وهذا سيضمن أن:
- يتم تطبيق التغييرات على ملف PDF.
- تم إزالة خيار زر الراديو الأصلي كما هو محدد.

## خاتمة

إن تعديل تسميات أزرار الاختيار في نموذج PDF باستخدام Aspose.PDF لـ .NET يمكن أن يعزز بشكل كبير من التفاعلية وسهولة استخدام مستنداتك. باستخدام الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة تحميل ملف PDF وتحديث خيارات أزرار الاختيار وحفظ التغييرات. هذا النهج مفيد لإدارة النماذج ويضمن أن ملفات PDF الخاصة بك تلبي الاحتياجات الدقيقة للمستخدمين. انغمس في Aspose.PDF واستكشف قدراته لمعالجة ملفات PDF الأخرى!

## الأسئلة الشائعة

### هل يمكنني تحديث حقول أزرار الاختيار المتعددة مرة واحدة؟
نعم، يمكنك تكرار جميع حقول أزرار الاختيار وتطبيق التغييرات حسب الحاجة.

### هل أحتاج إلى ترخيص لاستخدام Aspose.PDF؟
 يمكنك البدء بإصدار تجريبي مجاني، ولكن يلزم الحصول على ترخيص للاستخدام الموسع.[احصل على الترخيص هنا](https://purchase.aspose.com/buy).

### كيف يمكنني اختبار التغييرات قبل حفظ ملف PDF؟
يمكنك معاينة ملف PDF في بيئة التطوير الخاصة بك أو استخدام عارض PDF للتحقق من التعديلات.

### هل Aspose.PDF متوافق مع كافة إصدارات .NET؟
يدعم Aspose.PDF إصدارات مختلفة من .NET. تأكد من التحقق من التوافق مع إصدار .NET الخاص بك.

### هل يمكنني معالجة حقول النماذج الأخرى بنفس الطريقة؟
نعم، يمكن تطبيق تقنيات مماثلة على أنواع أخرى من حقول النموذج في مستندات PDF.