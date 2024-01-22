---
title: إضافة حقل نموذج في مستند PDF باستخدام Java
linktitle: إضافة حقل نموذج في مستند PDF باستخدام Java
second_title: Aspose.PDF جافا واجهة برمجة تطبيقات معالجة PDF
description: تعرف على كيفية إضافة حقول نموذج تفاعلية إلى مستندات PDF الخاصة بك باستخدام Java وAspose.PDF لـ Java. قم بإنشاء نماذج PDF سهلة الاستخدام بسهولة.
type: docs
weight: 10
url: /ar/java/pdf-form-fields/add-form-field-in-pdf-document-using-java/
---

## مقدمة

تعمل إضافة حقول النموذج إلى مستند PDF على تحسين وظائفه من خلال السماح للمستخدمين بإدخال البيانات مباشرة في المستند. يمكن أن يكون هذا مفيدًا بشكل لا يصدق لمجموعة متنوعة من الأغراض، مثل إنشاء نماذج أو استطلاعات أو تقارير قابلة للملء تحتوي على محتوى من إنشاء المستخدم.

سنستخدم Aspose.PDF لـ Java، وهي مكتبة قوية تعمل على تبسيط معالجة ملفات PDF في تطبيقات Java. باستخدام Aspose.PDF، يمكنك بسهولة إنشاء مستندات PDF وتعديلها ومعالجتها، بما في ذلك إضافة حقول النماذج ديناميكيًا.

## تهيئة البيئة

قبل أن نتعمق في التعليمات البرمجية، تحتاج إلى إعداد بيئة التطوير الخاصة بك. اتبع الخطوات التالية:

1.  تنزيل Aspose.PDF لـ Java: قم بزيارة موقع Aspose على الويب وقم بتنزيل أحدث إصدار من Aspose.PDF لـ Java. يمكن ان تجدها[هنا](https://releases.aspose.com/pdf/java/).

2. تثبيت Aspose.PDF: بعد التنزيل، قم بتثبيت Aspose.PDF باتباع تعليمات التثبيت المتوفرة على موقع الويب.

3. إنشاء مشروع Java: قم بإنشاء مشروع Java جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك وقم بتضمين مكتبة Aspose.PDF في مشروعك.

## إنشاء مستند PDF جديد

لنبدأ بإنشاء مستند PDF جديد. في هذا المثال، سنقوم بإنشاء ملف PDF بسيط بعنوان وبعض التعليمات.

```java
// قم باستيراد مكتبة Aspose.PDF
import com.aspose.pdf.*;

public class AddFormFieldPDF {
    public static void main(String[] args) {
        // إنشاء مستند PDF جديد
        Document doc = new Document();

        // إضافة صفحة إلى المستند
        Page page = doc.getPages().add();

        // أضف عنوانًا
        TextFragment title = new TextFragment("Feedback Form");
        title.getTextState().setFontSize(18);
        title.getTextState().setFont(FontRepository.findFont("Arial"));
        page.getParagraphs().add(title);

        // أضف تعليمات
        TextFragment instructions = new TextFragment("Please provide your feedback below:");
        instructions.getTextState().setFontSize(12);
        page.getParagraphs().add(instructions);

        // احفظ المستند في ملف
        doc.save("FeedbackForm.pdf");
    }
}
```

في مقتطف الكود هذا، نقوم بإنشاء مستند PDF جديد، وإضافة صفحة، وإدراج عنوان وبعض التعليمات.

## إضافة حقول النموذج

الآن، دعنا ننتقل إلى إضافة حقول النموذج إلى مستند PDF الخاص بنا. سنقوم بتضمين حقول نصية ومربعات اختيار وأزرار اختيار لإنشاء نموذج تعليقات تفاعلي.

### حقول النص

تسمح حقول النص للمستخدمين بإدخال النص. إليك كيفية إضافة حقل نصي:

```java
// إنشاء حقل نص
TextField textField = new TextField(page, new Rectangle(100, 300, 200, 20));
textField.getPdfObject().setBorderStyle(new BorderStyle(1)); // ضبط نمط الحدود
textField.setPartialName("txtName"); // تعيين اسم الحقل
textField.setMultiline(false); // تعطيل الخطوط المتعددة
page.getAnnotations().add(textField);
```

### خانات الاختيار

يتم استخدام مربعات الاختيار للخيارات الثنائية (على سبيل المثال، أسئلة نعم/لا). إليك كيفية إضافة مربع اختيار:

```java
// قم بإنشاء خانة اختيار
CheckboxField checkboxField = new CheckboxField(page, new Rectangle(100, 250, 20, 20));
checkboxField.setPartialName("chkAgree"); // تعيين اسم الحقل
checkboxField.setChecked(false); // في البداية لم يتم التحقق منها
page.getAnnotations().add(checkboxField);
```

### أزرار الراديو

تُستخدم أزرار الاختيار عندما يحتاج المستخدمون إلى اختيار خيار واحد من مجموعة. كل خيار هو زر اختيار منفصل، لكنهم ينتمون إلى نفس المجموعة. إليك كيفية إضافة أزرار الاختيار:

```java
// إنشاء أزرار الراديو
RadioButtonOptionField option1 = new RadioButtonOptionField(page, new Rectangle(100, 200, 20, 20));
RadioButtonOptionField option2 = new RadioButtonOptionField(page, new Rectangle(100, 180, 20, 20));
option1.setPartialName("optYes"); // قم بتعيين اسم الحقل للخيار 1
option2.setPartialName("optNo"); // قم بتعيين اسم الحقل للخيار 2

//إضافة خيارات إلى مجموعة أزرار الاختيار
RadioButtonOptionField[] options = {option1, option2};
RadioButtonField radioButtonField = new RadioButtonField(page, options);
page.getAnnotations().add(radioButtonField);
```

باستخدام أمثلة التعليمات البرمجية هذه، يمكنك إضافة حقول نصية ومربعات اختيار وأزرار اختيار إلى مستند PDF الخاص بك. تأكد من تخصيص خصائصها حسب الحاجة، مثل أسماء الحقول والقيم الافتراضية.

## تخصيص حقول النموذج

يتيح لك تخصيص حقول النموذج التحكم في مظهرها وسلوكها. يمكنك تغيير خصائص مثل حجم الخط ولون النص ونمط الحدود والمزيد.

### تغيير خصائص الحقل

لنفترض أنك تريد تغيير حجم الخط ولون النص في حقل النص:

```java
textField.getTextState().setFontSize(14);
textField.getTextState().setForegroundColor(Color.getGreen());
```

### التحقق من صحة المجال

يمكنك أيضًا تعيين قواعد التحقق من صحة حقول النموذج. على سبيل المثال، يمكنك أن تطلب من المستخدمين إدخال عنوان بريد إلكتروني صالح في حقل النص:

```java
textField.getValidation().add(ValidationType.EMAIL);
```

## تحديد قيم الحقول

لملء حقول النموذج بالبيانات مسبقًا، يمكنك تعيين قيمها الافتراضية برمجيًا. يعد هذا مفيدًا لإنشاء القوالب أو التعبئة المسبقة للمعلومات المعروفة.

```java
textField.setValue("John Doe"); // تعيين القيمة الافتراضية لحقل النص
checkboxField.setChecked(true); // حدد خانة الاختيار بشكل افتراضي
```

## تقديم النموذج والتحقق من صحته

إن إضافة حقول النموذج هو نصف القصة فقط؛ سوف تريد أيضا

 لتمكين تقديم النموذج والتحقق من صحته.

### تقديم النموذج

للسماح للمستخدمين بإرسال بيانات النموذج، يتعين عليك تحديد إجراء، مثل إرسال بريد إلكتروني أو الإرسال إلى خادم الويب. فيما يلي مثال لكيفية إعداد زر إرسال:

```java
ButtonField submitButton = new ButtonField(page, new Rectangle(100, 50, 80, 30));
submitButton.getPdfObject().setBorderStyle(new BorderStyle(1));
submitButton.getActions().getOnPushButton().add(new SubmitFormAction("https://yourserver.com/submit"، SubmitFormActionType.URL، "FeedbackForm.pdf"))؛
page.getAnnotations().add(submitButton);
```

### التحقق من صحة النموذج

يضمن التحقق من الصحة أن مدخلات المستخدم تلبي معايير محددة. على سبيل المثال، يمكنك التحقق من صحة حقل رقم الهاتف لقبول الأرقام فقط:

```java
textField.getValidation().add(ValidationType.NUMBER);
```

## الحفظ والتصدير

بمجرد إنشاء مستند PDF الخاص بك وتخصيصه باستخدام حقول النموذج، فقد حان الوقت لحفظه أو تصديره. يوفر Aspose.PDF خيارات متنوعة لهذا الغرض.

### حفظ إلى ملف محلي

لحفظ مستند PDF إلى ملف محلي، استخدم الكود التالي:

```java
doc.save("FeedbackForm.pdf");
```

### حفظ إلى دفق

 لحفظ مستند PDF في دفق، يمكنك استخدام`OutputStream` فصل:

```java
OutputStream outputStream = new FileOutputStream("FeedbackForm.pdf");
doc.save(outputStream);
outputStream.close();
```

## خاتمة

في هذا الدليل الشامل، اكتشفنا كيفية إضافة حقول النموذج إلى مستند PDF باستخدام Java وAspose.PDF لـ Java. لقد تعلمت كيفية إنشاء حقول نصية ومربعات اختيار وأزرار اختيار وتخصيص خصائصها وتعيين القيم الافتراضية وتمكين إرسال النموذج والتحقق من صحته وحفظ/تصدير مستند PDF.

## الأسئلة الشائعة

### كيف يمكنني إعداد قائمة منسدلة في نموذج PDF؟

 لإنشاء قائمة منسدلة (مربع التحرير والسرد) في نموذج PDF، يمكنك استخدام`ComboBoxField` فئة مقدمة من Aspose.PDF لجافا. اتبع أسلوبًا مشابهًا كما هو موضح في حقول النموذج الأخرى، وقم بتخصيص الخيارات باستخدام`AddItem` طريقة. يمكنك العثور على وثائق مفصلة حول هذا الأمر على موقع Aspose.

### هل Aspose.PDF لـ Java متوافق مع مكتبات وأطر عمل Java الأخرى؟

نعم، Aspose.PDF for Java متوافق مع العديد من مكتبات وأطر عمل Java. يمكنك دمجها في تطبيقات Java الخاصة بك، سواء كنت تستخدم Spring أو JavaFX أو أطر العمل الشائعة الأخرى. تأكد من مراجعة الوثائق والموارد للحصول على إرشادات التكامل المحددة.

### هل يمكنني حماية نموذج PDF تم إنشاؤه باستخدام Aspose.PDF لـ Java بكلمة مرور؟

قطعاً! يتيح لك Aspose.PDF for Java إضافة حماية بكلمة مرور إلى مستندات PDF الخاصة بك، بما في ذلك النماذج. يمكنك تعيين كلمات المرور على مستوى المستخدم وعلى مستوى المالك لتقييد الوصول والأذونات. راجع الوثائق للحصول على إرشادات مفصلة حول كيفية تنفيذ ميزة الأمان هذه.

### كيف يمكنني استخراج البيانات المقدمة عبر نموذج PDF؟

لاستخراج البيانات المقدمة من خلال نموذج PDF، ستحتاج إلى التعامل مع إرسال النموذج على الخادم الخاص بك أو الواجهة الخلفية للتطبيق. عندما يرسل المستخدم النموذج، يمكنك تلقي البيانات ومعالجتها حسب الحاجة. يوفر Aspose.PDF الأدوات اللازمة لاستخراج بيانات النموذج برمجيًا من مستند PDF الموجود على جانب الخادم.

### هل يمكنني إنشاء نماذج PDF ديناميكيًا بناءً على إدخال المستخدم؟

نعم، يمكنك إنشاء نماذج PDF ديناميكيًا بناءً على إدخال المستخدم باستخدام Aspose.PDF لـ Java. اعتمادًا على إدخال المستخدم أو منطق التطبيق، يمكنك إنشاء مستندات PDF مع حقول نماذج وتخطيطات مختلفة. تتيح هذه المرونة إنشاء نماذج مخصصة مصممة خصيصًا لتلبية احتياجات أو سيناريوهات المستخدم المحددة.