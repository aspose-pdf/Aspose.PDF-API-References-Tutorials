---
title: إنشاء نهج PDF متعدد الطبقات الثاني
linktitle: إنشاء نهج PDF متعدد الطبقات الثاني
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إنشاء ملف PDF متعدد الطبقات باستخدام Aspose.PDF for .NET. دليل خطوة بخطوة مع الكود المصدري لإنشاء ملفات PDF ديناميكية تحتوي على نصوص وصور.
type: docs
weight: 80
url: /ar/net/programming-with-document/createmultilayerpdfsecondapproach/
---

في هذا البرنامج التعليمي ، سوف نستكشف كيفية إنشاء ملف PDF متعدد الطبقات باستخدام الطريقة الثانية في Aspose.PDF for .NET. سنقدم دليلاً خطوة بخطوة مع شرح مفصل ويتضمن كود المصدر الكامل. باتباع هذا البرنامج التعليمي ، ستتمكن من إنشاء مستندات PDF بطبقات متعددة باستخدام مكتبة Aspose.PDF في تطبيقات .NET الخاصة بك.

الآن ، لنبدأ بالدليل المفصل خطوة بخطوة.

## الخطوة 1: إعداد البيئة

لتبدأ ، افتح Visual Studio وأنشئ مشروع C # جديد. تأكد من الرجوع إلى مكتبة Aspose.PDF في مشروعك. بمجرد قيامك بإعداد البيئة ، فأنت جاهز للمتابعة إلى الخطوة التالية.

## الخطوة 2: تهيئة المتغيرات

في هذه الخطوة ، سنقوم بتهيئة المتغيرات الضرورية. نحتاج إلى تعيين المسار إلى دليل المستند وتحديد متغيرات اللون لطبقات PDF. إليك مقتطف الشفرة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
```

## الخطوة 3: قم بإنشاء مستند PDF

بعد ذلك ، سننشئ نسخة جديدة من فئة Aspose.Pdf.Document ، والتي تمثل مستند PDF. إليك مقتطف الشفرة:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## الخطوة 4: أضف صفحة إلى المستند

في هذه الخطوة ، سنضيف صفحة جديدة إلى مستند PDF. إليك مقتطف الشفرة:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## الخطوة الخامسة: إضافة نص إلى الصفحة

الآن ، سنقوم بإضافة جزء نصي إلى الصفحة. سيتم عرض النص كقطعة فقرة 3 بلون أحمر. إليك مقتطف الشفرة:

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;

Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
```

## الخطوة 6: أضف صورة إلى الصفحة

في هذه الخطوة ، سنضيف صورة إلى الصفحة. سيتم وضع الصورة كمربع عائم بحجم معين. إليك مقتطف الشفرة:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);
ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);
```

## الخطوة 7: احفظ ملف PDF

في هذه الخطوة ، سنحفظ ملف PDF في ملف.

```
doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

### مثال على الكود المصدري لإنشاء طريقة ثانية لملف PDF متعدد الطبقات باستخدام Aspose.PDF for .NET.

```csharp

            
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

Aspose.Pdf.Page page = doc.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;
Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);

ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);

doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
            
        
```

## خاتمة

في هذه المقالة ، تعلمنا كيفية إنشاء ملف PDF متعدد الطبقات باستخدام الطريقة الثانية من Aspose.PDF for .NET. لقد قدمنا لك إرشادات خطوة بخطوة وكود المصدر الكامل المطلوب لإنشاء ملف PDF متعدد الطبقات.