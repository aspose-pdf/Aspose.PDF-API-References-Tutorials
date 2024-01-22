---
title: องค์ประกอบโครงสร้างบล็อกข้อความ
linktitle: องค์ประกอบโครงสร้างบล็อกข้อความ
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อเพิ่มองค์ประกอบโครงสร้างบล็อกข้อความ เช่น ส่วนหัวและย่อหน้าที่แท็ก ลงในเอกสาร PDF ที่มีอยู่
type: docs
weight: 220
url: /th/net/programming-with-tagged-pdf/text-block-structure-elements/
---
ในบทช่วยสอนโดยละเอียดนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# ที่ให้มาทีละขั้นตอนเพื่อสร้างองค์ประกอบโครงสร้างบล็อกข้อความในเอกสาร PDF ที่แท็กโดยใช้ Aspose.PDF สำหรับ .NET ทำตามคำแนะนำด้านล่างเพื่อทำความเข้าใจวิธีเพิ่มส่วนหัวหลายระดับและย่อหน้าที่แท็กลงในเอกสาร PDF ของคุณ

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้กำหนดค่าสภาพแวดล้อมการพัฒนาของคุณเพื่อใช้ Aspose.PDF สำหรับ .NET ซึ่งรวมถึงการติดตั้งไลบรารี Aspose.PDF และการกำหนดค่าโปรเจ็กต์ของคุณเพื่ออ้างอิง

## ขั้นตอนที่ 2: การสร้างเอกสาร PDF

ในขั้นตอนนี้ เราจะสร้างออบเจ็กต์เอกสาร PDF ใหม่ด้วย Aspose.PDF

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างเอกสาร PDF
Document document = new Document();
```

เราได้สร้างเอกสาร PDF ใหม่ด้วย Aspose.PDF

## ขั้นตอนที่ 3: รับเนื้อหาที่แท็กและตั้งชื่อและภาษา

ตอนนี้เรามาดูเนื้อหาที่แท็กของเอกสาร PDF และตั้งชื่อเอกสารและภาษา

```csharp
// รับเนื้อหาที่แท็ก
ITaggedContent taggedContent = document.TaggedContent;

// กำหนดชื่อเอกสารและภาษา
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

เราได้ตั้งชื่อและภาษาของเอกสาร PDF ที่แท็กแล้ว

## ขั้นตอนที่ 4: การได้รับองค์ประกอบโครงสร้างรูท

ตอนนี้เรามาดูองค์ประกอบโครงสร้างรูทของเอกสาร PDF กันดีกว่า

```csharp
//รับองค์ประกอบโครงสร้างรูท
StructureElement rootElement = taggedContent.RootElement;
```

เราได้รับองค์ประกอบโครงสร้างรากของเอกสาร PDF แล้ว

## ขั้นตอนที่ 5: เพิ่มหัวเรื่องและย่อหน้า

ตอนนี้เรากำลังจะเพิ่มส่วนหัวของระดับต่างๆ และย่อหน้าแท็กลงในเอกสาร PDF ของเรา

```csharp
// สร้างส่วนหัวในระดับต่างๆ
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);

// คำจำกัดความของข้อความส่วนหัว
h1.SetText("H1. Level 1 header");
h2.SetText("H2. Level 2 header");
h3.SetText("H3. Level 3 header");
h4.SetText("H4. Level 4 header");
h5.SetText("H5. Heading level 5");
h6.SetText("H6. Level 6 header");

// เพิ่มส่วนหัวให้กับองค์ประกอบโครงสร้างราก
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// สร้างย่อหน้า
ParagraphElement p = taggedContent.CreateParagraphElement();

//คำจำกัดความของข้อความในย่อหน้า
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet Nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");

// เพิ่มย่อหน้าให้กับองค์ประกอบโครงสร้างราก
rootElement.AppendChild(p);
```

เราได้เพิ่มส่วนหัวของระดับต่างๆ และย่อหน้าที่ติดแท็กให้กับองค์ประกอบโครงสร้างรากของเอกสาร PDF

## ขั้นตอนที่ 6: บันทึกเอกสาร PDF

ตอนนี้เราแก้ไขเอกสาร PDF เสร็จแล้ว มาบันทึกเป็นไฟล์กันดีกว่า

```csharp
// บันทึกเอกสาร PDF ที่แท็ก
document.Save(dataDir + "ElementsDeStructureDeBlocsDeTexte.pdf");
```

เราบันทึกเอกสาร PDF ที่แท็กด้วยองค์ประกอบโครงสร้างบล็อกข้อความในไดเร็กทอรีที่ระบุ

### ตัวอย่างซอร์สโค้ดสำหรับองค์ประกอบโครงสร้างบล็อกข้อความโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร PDF
Document document = new Document();

// รับเนื้อหาสำหรับการทำงานกับ TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// ตั้งชื่อและภาษาสำหรับ Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// รับองค์ประกอบโครงสร้างรูท
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
h1.SetText("H1. Header of Level 1");
h2.SetText("H2. Header of Level 2");
h3.SetText("H3. Header of Level 3");
h4.SetText("H4. Header of Level 4");
h5.SetText("H5. Header of Level 5");
h6.SetText("H6. Header of Level 6");
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
rootElement.AppendChild(p);

// บันทึกเอกสาร PDF ที่ติดแท็ก
document.Save(dataDir + "TextBlockStructureElements.pdf");
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อเพิ่มองค์ประกอบโครงสร้างบล็อกข้อความ เช่น ส่วนหัวและย่อหน้าที่แท็ก ลงในเอกสาร PDF ตอนนี้คุณสามารถใช้คุณสมบัติเหล่านี้เพื่อปรับปรุงโครงสร้างและการเข้าถึงเอกสาร PDF ของคุณได้

### คำถามที่พบบ่อย

#### ถาม: อะไรคือจุดสนใจหลักของบทช่วยสอนนี้เกี่ยวกับการสร้างองค์ประกอบโครงสร้างบล็อกข้อความในเอกสาร PDF ที่แท็กโดยใช้ Aspose.PDF สำหรับ .NET

ตอบ: บทช่วยสอนนี้เน้นที่การแนะนำคุณตลอดกระบวนการเพิ่มองค์ประกอบโครงสร้างบล็อกข้อความ รวมถึงส่วนหัวหลายระดับและย่อหน้าที่แท็ก ลงในเอกสาร PDF ที่แท็กโดยใช้ Aspose.PDF สำหรับ .NET บทช่วยสอนให้คำแนะนำทีละขั้นตอนและตัวอย่างซอร์สโค้ด C# เพื่อช่วยคุณปรับปรุงโครงสร้างและการเข้าถึงเอกสาร PDF ของคุณ

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการติดตามบทช่วยสอนนี้เกี่ยวกับองค์ประกอบโครงสร้างบล็อกข้อความด้วย Aspose.PDF สำหรับ .NET มีอะไรบ้าง

ตอบ: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณเพื่อใช้ Aspose.PDF สำหรับ .NET สิ่งนี้เกี่ยวข้องกับการติดตั้งไลบรารี Aspose.PDF และการกำหนดค่าโปรเจ็กต์ของคุณเพื่ออ้างอิง

#### ถาม: ฉันจะสร้างเอกสาร PDF ใหม่และเพิ่มองค์ประกอบโครงสร้างบล็อกข้อความโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: บทช่วยสอนนี้มีตัวอย่างซอร์สโค้ด C# ที่สาธิตวิธีสร้างเอกสาร PDF ใหม่และเพิ่มส่วนหัวหลายระดับและย่อหน้าที่ติดแท็กโดยใช้ Aspose.PDF สำหรับ .NET

#### ถาม: การเพิ่มองค์ประกอบโครงสร้างบล็อกข้อความลงในเอกสาร PDF มีความสำคัญอย่างไร

ตอบ: การเพิ่มองค์ประกอบโครงสร้างบล็อกข้อความ เช่น ส่วนหัวและย่อหน้าที่แท็ก จะช่วยปรับปรุงโครงสร้างความหมายของเอกสาร PDF สิ่งนี้จะปรับปรุงการเข้าถึงสำหรับโปรแกรมอ่านหน้าจอและเทคโนโลยีช่วยเหลืออื่น ๆ ทำให้ผู้ใช้สามารถนำทางและทำความเข้าใจเนื้อหาได้ง่ายขึ้น

#### ถาม: ฉันจะตั้งชื่อและภาษาของเอกสาร PDF ที่แท็กโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: บทช่วยสอนประกอบด้วยตัวอย่างซอร์สโค้ด C# ที่แสดงวิธีตั้งชื่อและภาษาของเอกสาร PDF ที่แท็กโดยใช้ Aspose.PDF สำหรับ .NET

#### ถาม: ฉันจะสร้างส่วนหัวหลายระดับในเอกสาร PDF ที่แท็กโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 ตอบ: บทช่วยสอนนี้ให้ตัวอย่างซอร์สโค้ด C# ที่สาธิตวิธีการสร้างส่วนหัวของระดับต่างๆ โดยใช้`CreateHeaderElement()` และผนวกเข้ากับองค์ประกอบโครงสร้างรากของเอกสาร PDF ที่แท็ก

#### ถาม: ฉันจะเพิ่มย่อหน้าที่แท็กลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: บทช่วยสอนประกอบด้วยตัวอย่างซอร์สโค้ด C# ที่แสดงวิธีสร้างย่อหน้าโดยใช้`CreateParagraphElement()` วิธีการและเพิ่มข้อความที่แท็กลงไปโดยใช้`SetText()` วิธี. จากนั้นย่อหน้าจะถูกผนวกเข้ากับองค์ประกอบโครงสร้างรากของเอกสาร PDF ที่แท็ก

#### ถาม: ฉันสามารถปรับแต่งรูปลักษณ์และการจัดรูปแบบขององค์ประกอบโครงสร้างบล็อกข้อความที่ฉันเพิ่มลงในเอกสาร PDF ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏและการจัดรูปแบบขององค์ประกอบโครงสร้างบล็อกข้อความได้โดยใช้คุณสมบัติและวิธีการต่างๆ ที่ Aspose.PDF สำหรับ .NET มอบให้ คุณสามารถปรับลักษณะแบบอักษร ขนาด สี การจัดตำแหน่ง และคุณลักษณะการจัดรูปแบบอื่นๆ เพื่อให้ตรงตามความต้องการเฉพาะของคุณได้

#### ถาม: ตัวอย่างซอร์สโค้ดที่ให้ไว้ในบทช่วยสอนช่วยในการเพิ่มองค์ประกอบโครงสร้างบล็อกข้อความลงในเอกสาร PDF ได้อย่างไร

ตอบ: ซอร์สโค้ดตัวอย่างที่ให้มาทำหน้าที่เป็นข้อมูลอ้างอิงที่เป็นประโยชน์สำหรับการนำการสร้างองค์ประกอบโครงสร้างบล็อกข้อความในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้โค้ดนี้เป็นจุดเริ่มต้นและแก้ไขได้ตามความต้องการ

#### ถาม: ฉันจะปรับปรุงและปรับแต่งเอกสาร PDF ของฉันเพิ่มเติมนอกเหนือจากองค์ประกอบโครงสร้างบล็อกข้อความโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

ตอบ: Aspose.PDF สำหรับ .NET นำเสนอคุณสมบัติที่หลากหลายสำหรับการจัดการเอกสาร PDF รวมถึงการเพิ่มรูปภาพ ตาราง ไฮเปอร์ลิงก์ คำอธิบายประกอบ ฟิลด์แบบฟอร์ม ลายน้ำ ลายเซ็นดิจิทัล และอื่นๆ คุณสามารถสำรวจเอกสารและแหล่งข้อมูลอย่างเป็นทางการเพื่อทำความเข้าใจความสามารถของห้องสมุดอย่างครอบคลุม