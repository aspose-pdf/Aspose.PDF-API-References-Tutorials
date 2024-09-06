---
title: إضافة حقل نموذج في مستند PDF باستخدام Java
linktitle: إضافة حقل نموذج في مستند PDF باستخدام Java
second_title: واجهة برمجة تطبيقات معالجة PDF الخاصة بـ Aspose.PDF Java
description: تعرف على كيفية إضافة حقول نماذج تفاعلية إلى مستندات PDF باستخدام Java وAspose.PDF for Java. قم بإنشاء نماذج PDF سهلة الاستخدام بكل سهولة.
type: docs
weight: 10
url: /ar/java/pdf-form-fields/add-form-field-in-pdf-document-using-java/
---

## مقدمة

إن إضافة حقول النماذج إلى مستند PDF يعزز من وظائفه من خلال السماح للمستخدمين بإدخال البيانات مباشرة في المستند. يمكن أن يكون هذا مفيدًا بشكل لا يصدق لمجموعة متنوعة من الأغراض، مثل إنشاء نماذج قابلة للملء أو استطلاعات الرأي أو تقارير بمحتوى من إنشاء المستخدم.

سنستخدم Aspose.PDF for Java، وهي مكتبة قوية تبسط معالجة ملفات PDF في تطبيقات Java. باستخدام Aspose.PDF، يمكنك بسهولة إنشاء مستندات PDF وتعديلها ومعالجتها، بما في ذلك إضافة حقول النماذج بشكل ديناميكي.

## إعداد البيئة

قبل أن نتعمق في الكود، عليك إعداد بيئة التطوير الخاصة بك. اتبع الخطوات التالية:

1.  تنزيل Aspose.PDF لـ Java: قم بزيارة موقع Aspose على الويب وقم بتنزيل أحدث إصدار من Aspose.PDF لـ Java. يمكنك العثور عليه[هنا](https://releases.aspose.com/pdf/java/).

2. تثبيت Aspose.PDF: بعد التنزيل، قم بتثبيت Aspose.PDF باتباع تعليمات التثبيت المقدمة على الموقع الإلكتروني.

3. إنشاء مشروع Java: قم بإنشاء مشروع Java جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك وقم بتضمين مكتبة Aspose.PDF في مشروعك.

## إنشاء مستند PDF جديد

لنبدأ بإنشاء مستند PDF جديد. في هذا المثال، سننشئ ملف PDF بسيطًا بعنوان وبعض الإرشادات.

```java
// استيراد مكتبة Aspose.PDF
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

        // أضف التعليمات
        TextFragment instructions = new TextFragment("Please provide your feedback below:");
        instructions.getTextState().setFontSize(12);
        page.getParagraphs().add(instructions);

        // حفظ المستند في ملف
        doc.save("FeedbackForm.pdf");
    }
}
```

في مقتطف التعليمات البرمجية هذا، نقوم بإنشاء مستند PDF جديد، وإضافة صفحة، وإدراج عنوان وبعض التعليمات.

## إضافة حقول النموذج

الآن، دعنا ننتقل إلى إضافة حقول النموذج إلى مستند PDF الخاص بنا. سنقوم بتضمين حقول نصية ومربعات اختيار وأزرار اختيار لإنشاء نموذج ملاحظات تفاعلي.

### حقول النص

تتيح حقول النص للمستخدمين إدخال النص. إليك كيفية إضافة حقل نص:

```java
// إنشاء حقل نص
TextField textField = new TextField(page, new Rectangle(100, 300, 200, 20));
textField.getPdfObject().setBorderStyle(new BorderStyle(1)); // تعيين نمط الحدود
textField.setPartialName("txtName"); // تعيين اسم الحقل
textField.setMultiline(false); // تعطيل تعدد الأسطر
page.getAnnotations().add(textField);
```

### مربعات الاختيار

تُستخدم مربعات الاختيار للخيارات الثنائية (على سبيل المثال، الأسئلة التي تكون الإجابة عليها بنعم/لا). وإليك كيفية إضافة مربع اختيار:

```java
// إنشاء مربع الاختيار
CheckboxField checkboxField = new CheckboxField(page, new Rectangle(100, 250, 20, 20));
checkboxField.setPartialName("chkAgree"); // تعيين اسم الحقل
checkboxField.setChecked(false); // لم يتم التحقق منه في البداية
page.getAnnotations().add(checkboxField);
```

### أزرار الراديو

تُستخدم أزرار الاختيار عندما يحتاج المستخدمون إلى اختيار خيار واحد من مجموعة. كل خيار عبارة عن زر اختيار منفصل، لكنها تنتمي إلى نفس المجموعة. وإليك كيفية إضافة أزرار الاختيار:

```java
// إنشاء أزرار الراديو
RadioButtonOptionField option1 = new RadioButtonOptionField(page, new Rectangle(100, 200, 20, 20));
RadioButtonOptionField option2 = new RadioButtonOptionField(page, new Rectangle(100, 180, 20, 20));
option1.setPartialName("optYes"); // تعيين اسم الحقل للخيار 1
option2.setPartialName("optNo"); // تعيين اسم الحقل للخيار 2

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

### التحقق من صحة الحقل

يمكنك أيضًا تعيين قواعد التحقق من صحة حقول النموذج. على سبيل المثال، يمكنك مطالبة المستخدمين بإدخال عنوان بريد إلكتروني صالح في حقل نصي:

```java
textField.getValidation().add(ValidationType.EMAIL);
```

## تعيين قيم الحقل

لملء حقول النموذج بالبيانات مسبقًا، يمكنك تعيين قيمها الافتراضية برمجيًا. وهذا مفيد لإنشاء قوالب أو ملء معلومات معروفة مسبقًا.

```java
textField.setValue("John Doe"); // تعيين القيمة الافتراضية لحقل النص
checkboxField.setChecked(true); // حدد مربع الاختيار افتراضيًا
```

## إرسال النموذج والتحقق منه

إن إضافة حقول النموذج ليست سوى نصف القصة؛ ستحتاج أيضًا إلى

 لتمكين إرسال النموذج والتحقق من صحته.

### إرسال النموذج

للسماح للمستخدمين بإرسال بيانات النموذج، يتعين عليك تحديد إجراء، مثل إرسال بريد إلكتروني أو الإرسال إلى خادم ويب. فيما يلي مثال لكيفية إعداد زر الإرسال:

```java
ButtonField submitButton = new ButtonField(page, new Rectangle(100, 50, 80, 30));
submitButton.getPdfObject().setBorderStyle(new BorderStyle(1));
submitButton.getActions().getOnPushButton().add(new SubmitFormAction("https://yourserver.com/submit، SubmitFormActionType.URL، "FeedbackForm.pdf");
page.getAnnotations().add(submitButton);
```

### التحقق من صحة النموذج

تضمن عملية التحقق أن إدخال المستخدم يفي بمعايير محددة. على سبيل المثال، يمكنك التحقق من صحة حقل رقم الهاتف لقبول الأرقام فقط:

```java
textField.getValidation().add(ValidationType.NUMBER);
```

## الحفظ والتصدير

بمجرد إنشاء مستند PDF وتخصيصه باستخدام حقول النماذج، حان الوقت لحفظه أو تصديره. يوفر Aspose.PDF خيارات متنوعة لهذا الغرض.

### حفظ في ملف محلي

لحفظ مستند PDF في ملف محلي، استخدم الكود التالي:

```java
doc.save("FeedbackForm.pdf");
```

### حفظ في تيار

 لحفظ مستند PDF في تيار، يمكنك استخدام`OutputStream` فصل:

```java
OutputStream outputStream = new FileOutputStream("FeedbackForm.pdf");
doc.save(outputStream);
outputStream.close();
```

## خاتمة

في هذا الدليل الشامل، استكشفنا كيفية إضافة حقول النماذج إلى مستند PDF باستخدام Java وAspose.PDF for Java. لقد تعلمت كيفية إنشاء حقول نصية ومربعات اختيار وأزرار اختيار وتخصيص خصائصها وتعيين القيم الافتراضية وتمكين إرسال النماذج والتحقق منها وحفظ/تصدير مستند PDF.

## الأسئلة الشائعة

### كيف يمكنني إعداد قائمة منسدلة في نموذج PDF؟

 لإنشاء قائمة منسدلة (مربع مجمع) في نموذج PDF، يمكنك استخدام`ComboBoxField` الفئة التي يوفرها Aspose.PDF لـ Java. اتبع نهجًا مشابهًا لما هو موضح لحقول النماذج الأخرى، وقم بتخصيص الخيارات باستخدام`AddItem` الطريقة. يمكنك العثور على وثائق مفصلة حول هذا الموضوع على موقع Aspose.

### هل Aspose.PDF for Java متوافق مع مكتبات Java وأطر العمل الأخرى؟

نعم، برنامج Aspose.PDF for Java متوافق مع العديد من مكتبات Java وأطر العمل. يمكنك دمجه في تطبيقات Java، سواء كنت تستخدم Spring أو JavaFX أو أطر عمل شائعة أخرى. تأكد من مراجعة الوثائق والموارد للحصول على إرشادات تكامل محددة.

### هل يمكنني حماية نموذج PDF تم إنشاؤه باستخدام Aspose.PDF لـ Java بكلمة مرور؟

بالتأكيد! يتيح لك برنامج Aspose.PDF for Java إضافة حماية بكلمة مرور إلى مستندات PDF، بما في ذلك النماذج. يمكنك تعيين كلمات مرور على مستوى المستخدم ومستوى المالك لتقييد الوصول والأذونات. راجع الوثائق للحصول على تعليمات مفصلة حول كيفية تنفيذ ميزة الأمان هذه.

### كيف يمكنني استخراج البيانات المرسلة من خلال نموذج PDF؟

لاستخراج البيانات المرسلة من خلال نموذج PDF، ستحتاج إلى التعامل مع إرسال النموذج على الخادم أو الواجهة الخلفية للتطبيق. عندما يرسل المستخدم النموذج، يمكنك تلقي البيانات ومعالجتها حسب الحاجة. يوفر Aspose.PDF الأدوات اللازمة لاستخراج بيانات النموذج برمجيًا من مستند PDF على جانب الخادم.

### هل يمكنني إنشاء نماذج PDF بشكل ديناميكي استنادًا إلى إدخال المستخدم؟

نعم، يمكنك إنشاء نماذج PDF بشكل ديناميكي استنادًا إلى إدخال المستخدم باستخدام Aspose.PDF for Java. بناءً على إدخال المستخدم أو منطق التطبيق، يمكنك إنشاء مستندات PDF بحقول وتخطيطات نماذج مختلفة. تتيح لك هذه المرونة إنشاء نماذج مخصصة مصممة خصيصًا لتلبية احتياجات المستخدم أو السيناريوهات المحددة.