---
title: كتلة النص المخفية في ملف PDF
linktitle: كتلة النص المخفية في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إنشاء كتل نصية مخفية في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 230
url: /ar/net/programming-with-text/hidden-text-block/
---
سنشرح في هذا البرنامج التعليمي كيفية إنشاء كتلة نصية مخفية في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. كتلة النص المخفية هي نص عائم يصبح مرئيًا عندما يمرر مؤشر الماوس فوق منطقة معينة. سنتابع عملية إنشاء كتلة النص المخفية خطوة بخطوة باستخدام كود مصدر C# المقدم.

## متطلبات

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي للبرمجة C#.

## الخطوة 1: إعداد دليل المستندات

 أولاً، تحتاج إلى تعيين المسار إلى الدليل الذي تريد حفظ ملف PDF الذي تم إنشاؤه فيه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir`متغير مع المسار إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند نموذجي

في هذه الخطوة، نقوم بإنشاء نموذج مستند PDF وإضافة جزء نص إليه. سيكون جزء النص بمثابة المشغل لعرض كتلة النص المخفية.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## الخطوة 3: افتح المستند

 الآن، نفتح المستند الذي تم إنشاؤه مسبقًا باستخدام الملف`Document` فصل.

```csharp
Document document = new Document(outputFile);
```

## الخطوة 4: ابحث عن جزء النص

 نحن نستخدم`TextFragmentAbsorber` كائن للعثور على جزء النص الذي سيؤدي إلى عرض كتلة النص المخفية. في هذه الحالة، نحن نبحث عن النص الدقيق "حرك مؤشر الماوس هنا لعرض النص العائم".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## الخطوة 5: إنشاء حقل النص المخفي

 نقوم بإنشاء أ`TextBoxField` كائن لتمثيل حقل النص المخفي. سيحتوي هذا الحقل على النص الذي يصبح مرئيًا عند تمرير مؤشر الماوس فوق نص التشغيل.

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

## الخطوة 6: أضف حقل النص المخفي إلى المستند

نضيف حقل النص المخفي إلى مجموعة نماذج المستند.

```csharp
document.Form.Add(floatingField);
```

## الخطوة 7: إنشاء الزر غير المرئي

نقوم بإنشاء حقل زر غير مرئي سيتم وضعه أعلى جزء نص التشغيل. سيحتوي حقل الزر هذا على إجراءات مرتبطة بأحداث الدخول والخروج بالماوس.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## الخطوة 8: احفظ المستند

وأخيرا، نقوم بحفظ المستند المعدل مع كتلة النص المخفية.

```csharp
document. Save(outputFile);
```

### نموذج التعليمات البرمجية المصدر لكتلة النص المخفية باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// إنشاء وثيقة نموذجية مع النص
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// فتح المستند مع النص
Document document = new Document(outputFile);
// قم بإنشاء كائن TextAbsorter للعثور على جميع العبارات المطابقة للتعبير العادي
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// قبول الممتص لصفحات الوثيقة
document.Pages.Accept(absorber);
// احصل على أول جزء من النص المستخرج
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// قم بإنشاء حقل نص مخفي للنص العائم في المستطيل المحدد للصفحة
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// قم بتعيين النص ليتم عرضه كقيمة حقل
floatingField.Value = "This is the \"floating text field\".";
// نوصي بجعل الحقل "للقراءة فقط" لهذا السيناريو
floatingField.ReadOnly = true;
// قم بتعيين علامة "مخفية" لجعل الحقل غير مرئي عند فتح المستند
floatingField.Flags |= AnnotationFlags.Hidden;
// ليس من الضروري تعيين اسم حقل فريد ولكنه مسموح به
floatingField.PartialName = "FloatingField_1";
// ليس من الضروري تحديد خصائص المظهر الميداني ولكنه يجعله أفضل
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// إضافة حقل نصي إلى المستند
document.Form.Add(floatingField);
// إنشاء زر غير مرئي في موضع جزء النص
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// قم بإنشاء إجراء إخفاء جديد للحقل المحدد (التعليق التوضيحي) وعلامة الاختفاء.
//(يمكنك أيضًا إعادة الإشارة إلى الحقل العائم بالاسم إذا حددته أعلاه.)
// أضف إجراءات عند الدخول/الخروج بالماوس في حقل الزر غير المرئي
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// إضافة حقل زر إلى المستند
document.Form.Add(buttonField);
// حفظ المستند
document.Save(outputFile);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إنشاء كتلة نصية مخفية باستخدام مكتبة Aspose.PDF لـ .NET. باتباع الدليل الموضح خطوة بخطوة، يمكنك إنشاء مستند PDF يحتوي على حقل نصي مخفي يصبح مرئيًا عندما يمرر مؤشر الماوس فوق منطقة معينة. يمكنك تخصيص مظهر وسلوك كتلة النص المخفية وفقًا لمتطلباتك.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "Hidden Text Block In PDF File"؟

ج: يشرح البرنامج التعليمي "Hidden Text Block In PDF File" كيفية إنشاء كتلة نص مخفية في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. كتلة النص المخفية هي نص عائم يصبح مرئيًا عندما يمرر مؤشر الماوس فوق منطقة معينة. يوفر هذا البرنامج التعليمي دليلاً خطوة بخطوة باستخدام كود مصدر C#.

#### س: لماذا أرغب في إنشاء كتلة نصية مخفية في ملف PDF؟

ج: يمكن أن يكون إنشاء كتلة نصية مخفية مفيدًا لمستندات PDF التفاعلية حيث تريد توفير معلومات إضافية أو سياق يصبح مرئيًا فقط عندما يقوم المستخدم بتمرير مؤشر الماوس فوق منطقة معينة.

#### س: كيف أقوم بإعداد دليل المستندات؟

ج: لإعداد دليل المستندات:

1.  يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى الدليل الذي تريد حفظ ملف PDF الذي تم إنشاؤه فيه.

#### س: كيف يمكنني إنشاء مستند نموذجي وإضافة جزء نص إليه؟

ج: في البرنامج التعليمي، يمكنك استخدام`Document` لإنشاء مستند PDF نموذجي وإضافة جزء نصي. يعمل جزء النص هذا كمشغل لعرض كتلة النص المخفية.

#### س: كيف يمكنني العثور على جزء النص الذي يقوم بتشغيل كتلة النص المخفية؟

 ج: يوضح البرنامج التعليمي كيفية استخدام`TextFragmentAbsorber` كائن للعثور على جزء النص الذي يؤدي إلى عرض كتلة النص المخفية. يبحث عن سلسلة نصية محددة داخل مستند PDF.

#### س: كيف يمكنني إنشاء حقل النص المخفي وتخصيصه؟

 ج: تقوم بإنشاء`TextBoxField` كائن لتمثيل حقل النص المخفي. يوفر البرنامج التعليمي تعليمات برمجية لتعيين خصائص مختلفة مثل الموضع والقيمة والمظهر وسلوك حقل النص المخفي.

#### س: كيف أقوم بإنشاء زر غير مرئي مرتبط بكتلة النص المخفية؟

 ج: يتم إنشاء حقل زر غير مرئي باستخدام`ButtonField` فصل. يتم وضع حقل الزر هذا أعلى جزء نص التشغيل ويحتوي على إجراءات مرتبطة بأحداث الدخول والخروج بالماوس. تتحكم هذه الإجراءات في رؤية كتلة النص المخفية.

#### س: هل يمكنني تخصيص مظهر كتلة النص المخفية ومنطقة التشغيل؟

ج: نعم، يمكنك تخصيص خصائص مختلفة لكل من حقل النص المخفي والزر غير المرئي، بما في ذلك الخط واللون والحجم والموضع.

#### س: كيف يمكنني حفظ المستند المعدل مع كتلة النص المخفية؟

 ج: يوضح البرنامج التعليمي كيفية حفظ المستند المعدل باستخدام ملف`Save` طريقة`Document` فصل.