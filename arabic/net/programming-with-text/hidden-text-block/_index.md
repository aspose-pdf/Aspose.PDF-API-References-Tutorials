---
title: كتلة نص مخفية
linktitle: كتلة نص مخفية
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إنشاء كتل نصية مخفية في PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 230
url: /ar/net/programming-with-text/hidden-text-block/
---

في هذا البرنامج التعليمي ، سنشرح كيفية إنشاء كتلة نصية مخفية باستخدام مكتبة Aspose.PDF لـ .NET. كتلة النص المخفية هي نص عائم يصبح مرئيًا عندما يحوم مؤشر الماوس فوق منطقة معينة. سنمر في العملية خطوة بخطوة لإنشاء كتلة النص المخفية باستخدام كود المصدر C # المقدم.

## متطلبات

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- تثبيت Aspose.PDF لمكتبة .NET.
- فهم أساسي لبرمجة C #.

## الخطوة 1: قم بإعداد دليل المستندات

 أولاً ، تحتاج إلى تعيين المسار إلى الدليل حيث تريد حفظ ملف PDF الذي تم إنشاؤه. يستبدل`"YOUR DOCUMENT DIRECTORY"` في ال`dataDir` متغير مع المسار إلى الدليل المطلوب.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بإنشاء نموذج مستند

في هذه الخطوة ، نقوم بإنشاء نموذج مستند PDF وإضافة جزء نصي إليه. سيكون جزء النص بمثابة المشغل لعرض كتلة النص المخفية.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## الخطوة 3: افتح المستند

 الآن ، نفتح المستند الذي تم إنشاؤه مسبقًا باستخدام ملف`Document` فصل.

```csharp
Document document = new Document(outputFile);
```

## الخطوة 4: ابحث عن جزء النص

 نحن نستخدم`TextFragmentAbsorber` للعثور على جزء النص الذي سيؤدي إلى عرض كتلة النص المخفية. في هذه الحالة ، نحن نبحث عن النص الدقيق "حرك مؤشر الماوس هنا لعرض نص عائم".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## الخطوة 5: إنشاء حقل النص المخفي

 نقوم بإنشاء ملف`TextBoxField`كائن لتمثيل حقل النص المخفي. سيحتوي هذا الحقل على النص الذي يصبح مرئيًا عندما يحوم مؤشر الماوس فوق نص المشغل.

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

نقوم بإنشاء حقل زر غير مرئي سيتم وضعه أعلى جزء النص المشغل. سيحتوي حقل الزر هذا على إجراءات مرتبطة بأحداث الدخول والخروج بالماوس.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## الخطوة 8: احفظ المستند

أخيرًا ، نحفظ المستند المعدل مع كتلة النص المخفية.

```csharp
document. Save(outputFile);
```

### نموذج التعليمات البرمجية المصدر لـ Hidden Text Block باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// إنشاء وثيقة مع النص
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// افتح المستند مع النص
Document document = new Document(outputFile);
// قم بإنشاء كائن TextAbsorber للعثور على جميع العبارات المطابقة للتعبير العادي
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// تقبل الممتص لصفحات الوثيقة
document.Pages.Accept(absorber);
// احصل على أول جزء نصي مستخرج
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// قم بإنشاء حقل نص مخفي للنص العائم في مستطيل الصفحة المحدد
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// قم بتعيين النص ليتم عرضه كقيمة للحقل
floatingField.Value = "This is the \"floating text field\".";
// نوصي بجعل الحقل "للقراءة فقط" لهذا السيناريو
floatingField.ReadOnly = true;
// قم بتعيين العلم "المخفي" لجعل الحقل غير مرئي عند فتح المستند
floatingField.Flags |= AnnotationFlags.Hidden;
//تعيين اسم حقل فريد ليس ضروريًا ولكنه مسموح به
floatingField.PartialName = "FloatingField_1";
// تحديد خصائص المظهر الميداني ليس ضروريًا ولكنه يجعله أفضل
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// أضف حقل نص إلى المستند
document.Form.Add(floatingField);
//إنشاء زر غير مرئي في موضع جزء النص
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// قم بإنشاء إجراء إخفاء جديد لحقل محدد (تعليق توضيحي) وعلامة إخفاء.
// (يمكنك أيضًا إعادة تسمية الحقل العائم بالاسم إذا حددته أعلاه.)
// أضف إجراءات عند الدخول / الخروج من الماوس في حقل الزر غير المرئي
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// أضف حقل الزر إلى المستند
document.Form.Add(buttonField);
// احفظ المستند
document.Save(outputFile);
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية إنشاء كتلة نص مخفية باستخدام Aspose.PDF لمكتبة .NET. باتباع الدليل التفصيلي خطوة بخطوة ، يمكنك إنشاء مستند PDF مع حقل نص مخفي يصبح مرئيًا عندما يحوم مؤشر الماوس فوق منطقة معينة. يمكنك تخصيص مظهر وسلوك كتلة النص المخفي وفقًا لمتطلباتك.