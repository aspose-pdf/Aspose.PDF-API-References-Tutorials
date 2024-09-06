---
title: كتلة نص مخفية في ملف PDF
linktitle: كتلة نص مخفية في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إنشاء كتل نصية مخفية في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 230
url: /ar/net/programming-with-text/hidden-text-block/
---
في هذا البرنامج التعليمي، سنشرح كيفية إنشاء كتلة نص مخفية في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. كتلة النص المخفية هي نص عائم يصبح مرئيًا عند تحريك مؤشر الماوس فوق منطقة معينة. سنتناول عملية إنشاء كتلة النص المخفية خطوة بخطوة باستخدام كود المصدر C# المقدم.

## متطلبات

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت مكتبة Aspose.PDF لـ .NET.
- فهم أساسي لبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه. استبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند نموذجي

في هذه الخطوة، نقوم بإنشاء مستند PDF نموذجي ونضيف إليه جزءًا من النص. سيعمل الجزء النصي كمحفز لعرض كتلة النص المخفية.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## الخطوة 3: افتح المستند

 الآن، نفتح المستند الذي تم إنشاؤه مسبقًا باستخدام`Document` فصل.

```csharp
Document document = new Document(outputFile);
```

## الخطوة 4: ابحث عن جزء النص

 نحن نستخدم`TextFragmentAbsorber`الكائن للعثور على جزء النص الذي سيؤدي إلى عرض كتلة النص المخفية. في هذه الحالة، نبحث عن النص الدقيق "حرك مؤشر الماوس هنا لعرض النص العائم".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## الخطوة 5: إنشاء حقل النص المخفي

 نحن ننشئ`TextBoxField` كائن لتمثيل حقل النص المخفي. سيحتوي هذا الحقل على النص الذي يصبح مرئيًا عند تحريك مؤشر الماوس فوق النص المحفز.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## الخطوة 6: إضافة حقل النص المخفي إلى المستند

نضيف حقل النص المخفي إلى مجموعة نماذج المستند.

```csharp
document.Form.Add(floatingField);
```

## الخطوة 7: إنشاء الزر غير المرئي

نقوم بإنشاء حقل زر غير مرئي سيتم وضعه أعلى جزء النص المحفز. سيحتوي حقل الزر هذا على إجراءات مرتبطة بأحداث دخول وخروج الماوس.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## الخطوة 8: حفظ المستند

وأخيرا، نقوم بحفظ المستند المعدل مع كتلة النص المخفية.

```csharp
document. Save(outputFile);
```

### عينة من كود المصدر لكتلة النص المخفية باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// إنشاء مستند نموذجي يحتوي على نص
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// فتح مستند يحتوي على نص
Document document = new Document(outputFile);
// إنشاء كائن TextAbsorber للعثور على جميع العبارات المطابقة للتعبير العادي
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// قبول الممتص لصفحات الوثيقة
document.Pages.Accept(absorber);
// احصل على أول جزء من النص المستخرج
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//إنشاء حقل نص مخفي للنص العائم في المستطيل المحدد للصفحة
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// تعيين النص الذي سيتم عرضه كقيمة حقل
floatingField.Value = "This is the \"floating text field\".";
// نوصي بجعل الحقل "للقراءة فقط" لهذا السيناريو
floatingField.ReadOnly = true;
// تعيين علامة "مخفي" لجعل الحقل غير مرئي عند فتح المستند
floatingField.Flags |= AnnotationFlags.Hidden;
// ليس من الضروري تعيين اسم فريد للحقل ولكن مسموح به
floatingField.PartialName = "FloatingField_1";
// إن تحديد خصائص مظهر الحقل ليس ضروريًا ولكنه يجعله أفضل
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// إضافة حقل نص إلى المستند
document.Form.Add(floatingField);
// إنشاء زر غير مرئي في موضع جزء النص
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// إنشاء إجراء إخفاء جديد للحقل المحدد (التعليق التوضيحي) وعلم الإخفاء.
// (يمكنك أيضًا الإشارة إلى الحقل العائم بالاسم إذا قمت بتحديده أعلاه.)
// إضافة إجراءات عند دخول/خروج الماوس في حقل الزر غير المرئي
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// إضافة حقل الزر إلى المستند
document.Form.Add(buttonField);
// حفظ المستند
document.Save(outputFile);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إنشاء كتلة نص مخفية باستخدام مكتبة Aspose.PDF for .NET. باتباع الدليل خطوة بخطوة، يمكنك إنشاء مستند PDF بحقل نص مخفي يصبح مرئيًا عند تحريك مؤشر الماوس فوق منطقة معينة. يمكنك تخصيص مظهر وسلوك كتلة النص المخفية وفقًا لمتطلباتك.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "كتلة النص المخفية في ملف PDF"؟

ج: يوضح البرنامج التعليمي "كتلة نص مخفية في ملف PDF" كيفية إنشاء كتلة نص مخفية في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. كتلة النص المخفية هي نص عائم يصبح مرئيًا عند تحريك مؤشر الماوس فوق منطقة معينة. يوفر هذا البرنامج التعليمي دليلًا خطوة بخطوة باستخدام كود المصدر C#.

#### س: لماذا أرغب في إنشاء كتلة نص مخفية في ملف PDF؟

أ: قد يكون إنشاء كتلة نصية مخفية مفيدًا لمستندات PDF التفاعلية حيث تريد تقديم معلومات إضافية أو سياق لا يصبح مرئيًا إلا عندما يحرك المستخدم مؤشر الماوس فوق منطقة محددة.

#### س: كيف أقوم بإعداد دليل المستندات؟

أ: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في`dataDir` متغير يحتوي على المسار إلى الدليل الذي تريد حفظ ملف PDF الناتج فيه.

#### س: كيف أقوم بإنشاء مستند نموذجي وإضافة جزء نصي إليه؟

 أ: في البرنامج التعليمي، يمكنك استخدام`Document` فئة لإنشاء مستند PDF نموذجي وإضافة جزء نصي. يعمل هذا الجزء النصي كمحفز لعرض كتلة النص المخفية.

#### س: كيف يمكنني العثور على جزء النص الذي يؤدي إلى تشغيل كتلة النص المخفية؟

 أ: يوضح البرنامج التعليمي كيفية استخدام`TextFragmentAbsorber` كائن للعثور على جزء النص الذي يؤدي إلى عرض كتلة النص المخفية. يبحث عن سلسلة نصية محددة داخل مستند PDF.

#### س: كيف أقوم بإنشاء حقل النص المخفي وتخصيصه؟

 أ: أنت تقوم بإنشاء`TextBoxField`كائن لتمثيل حقل النص المخفي. يوفر البرنامج التعليمي التعليمات البرمجية لتعيين خصائص مختلفة مثل الموضع والقيمة والمظهر وسلوك حقل النص المخفي.

#### س: كيف أقوم بإنشاء زر غير مرئي مرتبط بكتلة النص المخفية؟

 أ: يتم إنشاء حقل زر غير مرئي باستخدام`ButtonField` يقع حقل الزر هذا أعلى جزء النص المحفز وله إجراءات مرتبطة بأحداث دخول وخروج الماوس. تتحكم هذه الإجراءات في رؤية كتلة النص المخفية.

#### س: هل يمكنني تخصيص مظهر كتلة النص المخفية ومنطقة التشغيل؟

ج: نعم، يمكنك تخصيص خصائص مختلفة لكل من حقل النص المخفي والزر غير المرئي، بما في ذلك الخط واللون والحجم والموضع.

#### س: كيف أحفظ المستند المعدل مع كتلة النص المخفية؟

 أ: يوضح البرنامج التعليمي كيفية حفظ المستند المعدل باستخدام`Save` طريقة`Document` فصل.