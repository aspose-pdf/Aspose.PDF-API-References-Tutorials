---
title: บล็อกข้อความที่ซ่อนอยู่ในไฟล์ PDF
linktitle: บล็อกข้อความที่ซ่อนอยู่ในไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีสร้างบล็อกข้อความที่ซ่อนอยู่ในไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET
type: docs
weight: 230
url: /th/net/programming-with-text/hidden-text-block/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีสร้างบล็อกข้อความที่ซ่อนอยู่ในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET บล็อกข้อความที่ซ่อนอยู่คือข้อความลอยที่จะปรากฏให้เห็นเมื่อเคอร์เซอร์ของเมาส์เลื่อนไปเหนือพื้นที่เฉพาะ เราจะดำเนินการสร้างบล็อกข้อความที่ซ่อนอยู่ทีละขั้นตอนโดยใช้ซอร์สโค้ด C# ที่ให้มา

## ความต้องการ

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งไลบรารี Aspose.PDF สำหรับ .NET แล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร

 ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir`ตัวแปรพร้อมเส้นทางไปยังไดเร็กทอรีที่คุณต้องการ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารตัวอย่าง

ในขั้นตอนนี้ เราสร้างเอกสาร PDF ตัวอย่างและเพิ่มส่วนของข้อความลงไป ส่วนของข้อความจะทำหน้าที่เป็นตัวกระตุ้นในการแสดงบล็อกข้อความที่ซ่อนอยู่

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

## ขั้นตอนที่ 4: ค้นหาส่วนของข้อความ

 เราใช้ก`TextFragmentAbsorber` วัตถุเพื่อค้นหาส่วนของข้อความที่จะทริกเกอร์การแสดงบล็อกข้อความที่ซ่อนอยู่ ในกรณีนี้ เรากำลังค้นหาข้อความ "เลื่อนเคอร์เซอร์ของเมาส์มาที่นี่เพื่อแสดงข้อความแบบลอย"

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## ขั้นตอนที่ 5: สร้างฟิลด์ข้อความที่ซ่อนอยู่

 เราสร้างก`TextBoxField` วัตถุเพื่อแสดงฟิลด์ข้อความที่ซ่อนอยู่ ฟิลด์นี้จะมีข้อความที่มองเห็นได้เมื่อเคอร์เซอร์ของเมาส์วางเหนือข้อความทริกเกอร์

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

## ขั้นตอนที่ 6: เพิ่มฟิลด์ข้อความที่ซ่อนอยู่ลงในเอกสาร

เราเพิ่มฟิลด์ข้อความที่ซ่อนอยู่ในคอลเลกชันแบบฟอร์มของเอกสาร

```csharp
document.Form.Add(floatingField);
```

## ขั้นตอนที่ 7: สร้างปุ่มที่มองไม่เห็น

เราสร้างฟิลด์ปุ่มที่มองไม่เห็นซึ่งจะถูกวางตำแหน่งไว้ด้านบนของส่วนข้อความทริกเกอร์ ฟิลด์ปุ่มนี้จะมีการดำเนินการที่เกี่ยวข้องกับการเข้าและออกจากเหตุการณ์ของเมาส์

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## ขั้นตอนที่ 8: บันทึกเอกสาร

สุดท้าย เราจะบันทึกเอกสารที่แก้ไขด้วยบล็อกข้อความที่ซ่อนอยู่

```csharp
document. Save(outputFile);
```

### ตัวอย่างซอร์สโค้ดสำหรับบล็อกข้อความที่ซ่อนอยู่โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// สร้างเอกสารตัวอย่างพร้อมข้อความ
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// เปิดเอกสารพร้อมข้อความ
Document document = new Document(outputFile);
// สร้างวัตถุ TextAbsorber เพื่อค้นหาวลีทั้งหมดที่ตรงกับนิพจน์ทั่วไป
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// ยอมรับตัวดูดซับสำหรับหน้าเอกสาร
document.Pages.Accept(absorber);
// รับส่วนข้อความแรกที่แยกออกมา
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// สร้างฟิลด์ข้อความที่ซ่อนอยู่สำหรับข้อความลอยอยู่ในสี่เหลี่ยมที่ระบุของหน้า
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// ตั้งค่าข้อความที่จะแสดงเป็นค่าฟิลด์
floatingField.Value = "This is the \"floating text field\".";
// เราขอแนะนำให้สร้างฟิลด์ 'อ่านอย่างเดียว' สำหรับสถานการณ์นี้
floatingField.ReadOnly = true;
// ตั้งค่าสถานะ 'ซ่อน' เพื่อทำให้ช่องมองไม่เห็นเมื่อเปิดเอกสาร
floatingField.Flags |= AnnotationFlags.Hidden;
// ไม่จำเป็นต้องตั้งชื่อฟิลด์ที่ไม่ซ้ำกันแต่ได้รับอนุญาต
floatingField.PartialName = "FloatingField_1";
// ไม่จำเป็นต้องตั้งค่าลักษณะที่ปรากฏของฟิลด์แต่จะทำให้ดีขึ้น
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// เพิ่มช่องข้อความลงในเอกสาร
document.Form.Add(floatingField);
// สร้างปุ่มที่มองไม่เห็นในตำแหน่งส่วนของข้อความ
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// สร้างการดำเนินการซ่อนใหม่สำหรับฟิลด์ที่ระบุ (คำอธิบายประกอบ) และธงการมองไม่เห็น
//(คุณอาจเรียกฟิลด์ลอยตามชื่อได้หากคุณระบุไว้ข้างต้น)
// เพิ่มการดำเนินการบนเมาส์เข้า/ออกที่ช่องปุ่มที่มองไม่เห็น
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// เพิ่มช่องปุ่มลงในเอกสาร
document.Form.Add(buttonField);
// บันทึกเอกสาร
document.Save(outputFile);
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีสร้างบล็อกข้อความที่ซ่อนอยู่โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถสร้างเอกสาร PDF พร้อมฟิลด์ข้อความที่ซ่อนอยู่ซึ่งจะปรากฏให้เห็นเมื่อเคอร์เซอร์ของเมาส์เลื่อนเมาส์ไปเหนือพื้นที่เฉพาะ คุณสามารถปรับแต่งลักษณะที่ปรากฏและการทำงานของบล็อกข้อความที่ซ่อนอยู่ได้ตามความต้องการของคุณ

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของบทช่วยสอน "บล็อกข้อความที่ซ่อนอยู่ในไฟล์ PDF" คืออะไร

ตอบ: บทช่วยสอน "บล็อกข้อความที่ซ่อนอยู่ในไฟล์ PDF" อธิบายวิธีสร้างบล็อกข้อความที่ซ่อนอยู่ในไฟล์ PDF โดยใช้ไลบรารี Aspose.PDF สำหรับ .NET บล็อกข้อความที่ซ่อนอยู่คือข้อความลอยที่จะปรากฏให้เห็นเมื่อเคอร์เซอร์ของเมาส์เลื่อนไปเหนือพื้นที่เฉพาะ บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนโดยใช้ซอร์สโค้ด C#

#### ถาม: เหตุใดฉันจึงต้องการสร้างบล็อกข้อความที่ซ่อนอยู่ในไฟล์ PDF

ตอบ: การสร้างบล็อกข้อความที่ซ่อนอยู่จะมีประโยชน์สำหรับเอกสาร PDF แบบโต้ตอบที่คุณต้องการให้ข้อมูลเพิ่มเติมหรือบริบทที่จะมองเห็นได้ก็ต่อเมื่อผู้ใช้เลื่อนเคอร์เซอร์เมาส์ไปเหนือพื้นที่ที่กำหนด

#### ถาม: ฉันจะตั้งค่าไดเร็กทอรีเอกสารได้อย่างไร

ตอบ: หากต้องการตั้งค่าไดเร็กทอรีเอกสาร:

1.  แทนที่`"YOUR DOCUMENT DIRECTORY"` ใน`dataDir` ตัวแปรพร้อมพาธไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่สร้างขึ้น

#### ถาม: ฉันจะสร้างเอกสารตัวอย่างและเพิ่มส่วนข้อความได้อย่างไร

ตอบ: ในบทช่วยสอน คุณใช้ไฟล์`Document` คลาสเพื่อสร้างตัวอย่างเอกสาร PDF และเพิ่มส่วนของข้อความ ส่วนของข้อความนี้ทำหน้าที่เป็นตัวกระตุ้นสำหรับการแสดงบล็อกข้อความที่ซ่อนอยู่

#### ถาม: ฉันจะค้นหาส่วนของข้อความที่ทริกเกอร์บล็อกข้อความที่ซ่อนอยู่ได้อย่างไร

 ตอบ: บทช่วยสอนสาธิตวิธีการใช้งาน`TextFragmentAbsorber` วัตถุเพื่อค้นหาส่วนของข้อความที่ทริกเกอร์การแสดงบล็อกข้อความที่ซ่อนอยู่ ค้นหาสตริงข้อความเฉพาะภายในเอกสาร PDF

#### ถาม: ฉันจะสร้างและปรับแต่งช่องข้อความที่ซ่อนอยู่ได้อย่างไร

 ตอบ: คุณสร้าง`TextBoxField` วัตถุเพื่อแสดงฟิลด์ข้อความที่ซ่อนอยู่ บทช่วยสอนให้โค้ดเพื่อตั้งค่าคุณสมบัติต่างๆ เช่น ตำแหน่ง ค่า ลักษณะ และลักษณะการทำงานของฟิลด์ข้อความที่ซ่อนอยู่

#### ถาม: ฉันจะสร้างปุ่มที่มองไม่เห็นซึ่งเชื่อมโยงกับบล็อกข้อความที่ซ่อนอยู่ได้อย่างไร

 ตอบ: ฟิลด์ปุ่มที่มองไม่เห็นถูกสร้างขึ้นโดยใช้`ButtonField` ระดับ. ฟิลด์ปุ่มนี้วางตำแหน่งที่ด้านบนของส่วนข้อความทริกเกอร์และมีการดำเนินการที่เกี่ยวข้องกับเหตุการณ์การเข้าและออกของเมาส์ การดำเนินการเหล่านี้จะควบคุมการมองเห็นบล็อกข้อความที่ซ่อนอยู่

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของบล็อกข้อความที่ซ่อนอยู่และพื้นที่ทริกเกอร์ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งคุณสมบัติต่างๆ ของทั้งช่องข้อความที่ซ่อนอยู่และปุ่มที่มองไม่เห็นได้ รวมถึงแบบอักษร สี ขนาด และตำแหน่ง

#### ถาม: ฉันจะบันทึกเอกสารที่แก้ไขด้วยบล็อกข้อความที่ซ่อนอยู่ได้อย่างไร

 ตอบ: บทช่วยสอนสาธิตวิธีการบันทึกเอกสารที่แก้ไขโดยใช้`Save` วิธีการของ`Document` ระดับ.