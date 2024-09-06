---
title: บล็อกข้อความที่ซ่อนอยู่ในไฟล์ PDF
linktitle: บล็อกข้อความที่ซ่อนอยู่ในไฟล์ PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการสร้างบล็อกข้อความที่ซ่อนอยู่ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 230
url: /th/net/programming-with-text/hidden-text-block/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีสร้างบล็อกข้อความที่ซ่อนอยู่ในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET บล็อกข้อความที่ซ่อนอยู่คือข้อความลอยที่ปรากฏขึ้นเมื่อเคอร์เซอร์เมาส์วางอยู่เหนือพื้นที่เฉพาะ เราจะอธิบายกระบวนการทีละขั้นตอนในการสร้างบล็อกข้อความที่ซ่อนอยู่โดยใช้โค้ดต้นฉบับ C# ที่ให้มา

## ความต้องการ

ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

 ขั้นแรก คุณต้องตั้งค่าเส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไดเร็กทอรีที่คุณต้องการ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารตัวอย่าง

ในขั้นตอนนี้ เราจะสร้างเอกสาร PDF ตัวอย่างและเพิ่มข้อความบางส่วนลงไป ข้อความบางส่วนจะทำหน้าที่เป็นตัวกระตุ้นให้แสดงบล็อกข้อความที่ซ่อนอยู่

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## ขั้นตอนที่ 3: เปิดเอกสาร

 ตอนนี้เราเปิดเอกสารที่สร้างไว้ก่อนหน้านี้โดยใช้`Document` ระดับ.

```csharp
Document document = new Document(outputFile);
```

## ขั้นตอนที่ 4: ค้นหาชิ้นส่วนข้อความ

 เราใช้`TextFragmentAbsorber`วัตถุเพื่อค้นหาส่วนของข้อความที่จะทริกเกอร์การแสดงบล็อกข้อความที่ซ่อนอยู่ ในกรณีนี้ เรากำลังค้นหาข้อความที่แน่นอน "เลื่อนเคอร์เซอร์เมาส์มาที่นี่เพื่อแสดงข้อความลอย"

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## ขั้นตอนที่ 5: สร้างช่องข้อความที่ซ่อนไว้

 เราสร้าง`TextBoxField` วัตถุที่จะแสดงฟิลด์ข้อความที่ซ่อนอยู่ ฟิลด์นี้จะมีข้อความที่มองเห็นได้เมื่อเคอร์เซอร์เมาส์วางอยู่เหนือข้อความทริกเกอร์

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

## ขั้นตอนที่ 6: เพิ่มช่องข้อความที่ซ่อนไว้ในเอกสาร

เราเพิ่มฟิลด์ข้อความที่ซ่อนอยู่ลงในคอลเล็กชั่นฟอร์มของเอกสาร

```csharp
document.Form.Add(floatingField);
```

## ขั้นตอนที่ 7: สร้างปุ่มที่มองไม่เห็น

เราสร้างฟิลด์ปุ่มที่มองไม่เห็นซึ่งจะวางอยู่ด้านบนของส่วนข้อความทริกเกอร์ ฟิลด์ปุ่มนี้จะมีการดำเนินการที่เกี่ยวข้องกับเหตุการณ์เข้าและออกของเมาส์

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## ขั้นตอนที่ 8: บันทึกเอกสาร

สุดท้ายเราบันทึกเอกสารที่แก้ไขด้วยบล็อกข้อความที่ซ่อนอยู่

```csharp
document. Save(outputFile);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับ Hidden Text Block โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// สร้างเอกสารตัวอย่างด้วยข้อความ
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// เปิดเอกสารที่มีข้อความ
Document document = new Document(outputFile);
// สร้างวัตถุ TextAbsorber เพื่อค้นหาวลีทั้งหมดที่ตรงกับนิพจน์ทั่วไป
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// รับตัวดูดซับหน้าเอกสาร
document.Pages.Accept(absorber);
// รับชิ้นส่วนข้อความที่แยกออกมาชิ้นแรก
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//สร้างฟิลด์ข้อความที่ซ่อนอยู่สำหรับข้อความลอยในสี่เหลี่ยมผืนผ้าที่ระบุของหน้า
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// ตั้งค่าข้อความที่จะแสดงเป็นค่าฟิลด์
floatingField.Value = "This is the \"floating text field\".";
// เราขอแนะนำให้สร้างฟิลด์ 'อ่านอย่างเดียว' สำหรับสถานการณ์นี้
floatingField.ReadOnly = true;
// ตั้งค่าแฟล็ก 'ซ่อน' เพื่อทำให้ฟิลด์ไม่ปรากฏเมื่อเปิดเอกสาร
floatingField.Flags |= AnnotationFlags.Hidden;
// การตั้งชื่อฟิลด์ที่ไม่ซ้ำกันไม่จำเป็นแต่ได้รับอนุญาต
floatingField.PartialName = "FloatingField_1";
// การตั้งค่าลักษณะของลักษณะสนามไม่จำเป็นแต่จะทำให้ดีขึ้น
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// เพิ่มช่องข้อความลงในเอกสาร
document.Form.Add(floatingField);
// สร้างปุ่มที่มองไม่เห็นบนตำแหน่งของชิ้นส่วนข้อความ
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// สร้างการดำเนินการซ่อนใหม่สำหรับฟิลด์ที่ระบุ (คำอธิบายประกอบ) และแฟล็กการมองไม่เห็น
// (คุณสามารถอ้างอิงฟิลด์ลอยตัวโดยใช้ชื่อได้เช่นกัน หากคุณระบุไว้ข้างต้น)
// เพิ่มการกระทำเมื่อกดเข้า/ออกด้วยเมาส์ที่ช่องปุ่มที่มองไม่เห็น
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// เพิ่มช่องปุ่มลงในเอกสาร
document.Form.Add(buttonField);
// บันทึกเอกสาร
document.Save(outputFile);
```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีสร้างบล็อกข้อความที่ซ่อนอยู่โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET โดยปฏิบัติตามคำแนะนำทีละขั้นตอน คุณสามารถสร้างเอกสาร PDF ที่มีฟิลด์ข้อความที่ซ่อนอยู่ ซึ่งจะมองเห็นได้เมื่อเคอร์เซอร์เมาส์วางอยู่เหนือพื้นที่เฉพาะ คุณสามารถปรับแต่งลักษณะและการทำงานของบล็อกข้อความที่ซ่อนอยู่ตามความต้องการของคุณได้

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "บล็อกข้อความที่ซ่อนอยู่ในไฟล์ PDF" คืออะไร

A: บทช่วยสอน "Hidden Text Block In PDF File" อธิบายวิธีการสร้าง Hidden Text Block ในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET Hidden Text Block คือข้อความลอยที่ปรากฏขึ้นเมื่อเคอร์เซอร์เมาส์วางอยู่เหนือพื้นที่เฉพาะ บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนโดยใช้โค้ดต้นฉบับของ C#

#### ถาม: ทำไมฉันจึงต้องการสร้างบล็อกข้อความที่ซ่อนอยู่ในไฟล์ PDF

A: การสร้างบล็อกข้อความที่ซ่อนอยู่สามารถเป็นประโยชน์สำหรับเอกสาร PDF แบบโต้ตอบที่คุณต้องการใส่ข้อมูลหรือบริบทเพิ่มเติมที่จะมองเห็นได้เฉพาะเมื่อผู้ใช้เลื่อนเคอร์เซอร์ของเมาส์ไปเหนือพื้นที่ที่กำหนด

#### ถาม: ฉันจะตั้งค่าไดเรกทอรีเอกสารได้อย่างไร?

ก: การตั้งค่าไดเรกทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรที่มีเส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น

#### ถาม: ฉันจะสร้างเอกสารตัวอย่างและเพิ่มส่วนข้อความลงไปได้อย่างไร

 A: ในบทช่วยสอน คุณจะใช้`Document` คลาสสำหรับสร้างเอกสาร PDF ตัวอย่างและเพิ่มส่วนข้อความ ส่วนข้อความนี้ทำหน้าที่เป็นตัวกระตุ้นสำหรับการแสดงบล็อกข้อความที่ซ่อนอยู่

#### ถาม: ฉันจะค้นหาชิ้นส่วนข้อความที่ทำให้เกิดบล็อกข้อความที่ซ่อนอยู่ได้อย่างไร

 A: บทช่วยสอนนี้สาธิตวิธีใช้`TextFragmentAbsorber` วัตถุเพื่อค้นหาส่วนของข้อความที่ทำให้เกิดการแสดงบล็อกข้อความที่ซ่อนอยู่ โดยจะค้นหาสตริงข้อความเฉพาะภายในเอกสาร PDF

#### ถาม: ฉันจะสร้างและปรับแต่งช่องข้อความที่ซ่อนอยู่ได้อย่างไร

 ก: คุณสร้าง`TextBoxField`วัตถุที่จะแสดงฟิลด์ข้อความที่ซ่อนอยู่ บทช่วยสอนนี้ให้โค้ดสำหรับตั้งค่าคุณสมบัติต่างๆ เช่น ตำแหน่ง ค่า รูปลักษณ์ และพฤติกรรมของฟิลด์ข้อความที่ซ่อนอยู่

#### ถาม: ฉันจะสร้างปุ่มที่มองไม่เห็นซึ่งเชื่อมโยงกับบล็อกข้อความที่ซ่อนอยู่ได้อย่างไร

 A: สร้างช่องปุ่มที่มองไม่เห็นโดยใช้`ButtonField` คลาส ปุ่มฟิลด์นี้จะวางอยู่ด้านบนของข้อความทริกเกอร์ และมีการดำเนินการที่เกี่ยวข้องกับเหตุการณ์เข้าและออกจากเมาส์ การดำเนินการเหล่านี้จะควบคุมการมองเห็นของบล็อกข้อความที่ซ่อนอยู่

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของบล็อกข้อความที่ซ่อนอยู่และพื้นที่ทริกเกอร์ได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งคุณสมบัติต่างๆ ของทั้งช่องข้อความที่ซ่อนและปุ่มที่มองไม่เห็นได้ รวมถึงแบบอักษร สี ขนาด และตำแหน่ง

#### ถาม: ฉันจะบันทึกเอกสารที่แก้ไขโดยมีบล็อกข้อความที่ซ่อนอยู่ได้อย่างไร

 A: บทช่วยสอนสาธิตวิธีการบันทึกเอกสารที่แก้ไขโดยใช้`Save` วิธีการของ`Document` ระดับ.