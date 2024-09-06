---
title: องค์ประกอบโครงสร้างบล็อกข้อความ
linktitle: องค์ประกอบโครงสร้างบล็อกข้อความ
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: เรียนรู้วิธีการใช้ Aspose.PDF สำหรับ .NET เพื่อเพิ่มองค์ประกอบโครงสร้างบล็อกข้อความ เช่น หัวเรื่องและย่อหน้าที่มีแท็ก ลงในเอกสาร PDF ที่มีอยู่
type: docs
weight: 220
url: /th/net/programming-with-tagged-pdf/text-block-structure-elements/
---
ในบทช่วยสอนโดยละเอียดนี้ เราจะแนะนำคุณทีละขั้นตอนเกี่ยวกับโค้ดต้นฉบับ C# ที่ให้มาเพื่อสร้างองค์ประกอบโครงสร้างบล็อกข้อความในเอกสาร PDF ที่มีแท็กโดยใช้ Aspose.PDF สำหรับ .NET ปฏิบัติตามคำแนะนำด้านล่างเพื่อทำความเข้าใจวิธีการเพิ่มหัวเรื่องหลายระดับและย่อหน้าที่มีแท็กในเอกสาร PDF ของคุณ

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนเริ่มต้น โปรดแน่ใจว่าคุณได้กำหนดค่าสภาพแวดล้อมการพัฒนาของคุณให้ใช้ Aspose.PDF สำหรับ .NET แล้ว ซึ่งรวมถึงการติดตั้งไลบรารี Aspose.PDF และกำหนดค่าโปรเจ็กต์ของคุณเพื่ออ้างอิงไลบรารีดังกล่าว

## ขั้นตอนที่ 2: การสร้างเอกสาร PDF

ในขั้นตอนนี้เราจะสร้างอ็อบเจ็กต์เอกสาร PDF ใหม่ด้วย Aspose.PDF

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างเอกสาร PDF
Document document = new Document();
```

เราได้สร้างเอกสาร PDF ใหม่ด้วย Aspose.PDF

## ขั้นตอนที่ 3: รับเนื้อหาที่แท็กและตั้งชื่อเรื่องและภาษา

ต่อไปเรามารับเนื้อหาที่แท็กของเอกสาร PDF และตั้งชื่อเอกสารและภาษากัน

```csharp
// รับเนื้อหาที่ถูกแท็ก
ITaggedContent taggedContent = document.TaggedContent;

// กำหนดชื่อเอกสารและภาษา
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

เราได้ตั้งชื่อเรื่องและภาษาของเอกสาร PDF ที่ถูกแท็กแล้ว

## ขั้นตอนที่ 4: การได้รับองค์ประกอบโครงสร้างราก

ต่อไปเรามาดูองค์ประกอบโครงสร้างรากของเอกสาร PDF กัน

```csharp
//รับองค์ประกอบโครงสร้างราก
StructureElement rootElement = taggedContent.RootElement;
```

เราได้รับองค์ประกอบโครงสร้างรากของเอกสาร PDF แล้ว

## ขั้นตอนที่ 5: เพิ่มหัวข้อและย่อหน้า

ตอนนี้เรากำลังจะเพิ่มหัวข้อระดับต่างๆ และย่อหน้าที่แท็กลงในเอกสาร PDF ของเรา

```csharp
// สร้างส่วนหัวของระดับที่แตกต่างกัน
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

// เพิ่มส่วนหัวลงในองค์ประกอบโครงสร้างราก
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// สร้างย่อหน้า
ParagraphElement p = taggedContent.CreateParagraphElement();

//ความหมายของข้อความในย่อหน้า
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet Nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");

// เพิ่มย่อหน้าลงในองค์ประกอบโครงสร้างราก
rootElement.AppendChild(p);
```

เราได้เพิ่มหัวเรื่องระดับต่างๆ และย่อหน้าที่มีแท็กลงในองค์ประกอบโครงสร้างรากของเอกสาร PDF

## ขั้นตอนที่ 6: บันทึกเอกสาร PDF

ตอนนี้เราแก้ไขเอกสาร PDF เสร็จแล้ว มาบันทึกลงในไฟล์กัน

```csharp
// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "ElementsDeStructureDeBlocsDeTexte.pdf");
```

เราบันทึกเอกสาร PDF ที่ถูกแท็กโดยมีองค์ประกอบโครงสร้างบล็อกข้อความในไดเร็กทอรีที่ระบุ

### ตัวอย่างโค้ดต้นฉบับสำหรับ Text Block Structure Elements โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสาร PDF
Document document = new Document();

// รับเนื้อหาสำหรับงานด้วย TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// ตั้งชื่อเรื่องและภาษาสำหรับ Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// รับองค์ประกอบโครงสร้างราก
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

// บันทึกเอกสาร PDF ที่ถูกแท็ก
document.Save(dataDir + "TextBlockStructureElements.pdf");
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อเพิ่มองค์ประกอบโครงสร้างบล็อกข้อความ เช่น หัวเรื่องและย่อหน้าที่มีแท็ก ลงในเอกสาร PDF ตอนนี้คุณสามารถใช้คุณลักษณะเหล่านี้เพื่อปรับปรุงโครงสร้างและการเข้าถึงเอกสาร PDF ของคุณได้แล้ว

### คำถามที่พบบ่อย

#### ถาม: จุดเน้นหลักของบทช่วยสอนนี้เกี่ยวกับการสร้างองค์ประกอบโครงสร้างบล็อกข้อความในเอกสาร PDF ที่มีแท็กโดยใช้ Aspose.PDF สำหรับ .NET คืออะไร

A: บทช่วยสอนนี้มุ่งเน้นที่การแนะนำคุณตลอดกระบวนการเพิ่มองค์ประกอบโครงสร้างบล็อกข้อความ รวมถึงหัวเรื่องหลายระดับและย่อหน้าที่มีแท็ก ลงในเอกสาร PDF ที่มีแท็กโดยใช้ Aspose.PDF สำหรับ .NET บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนและตัวอย่างโค้ดต้นฉบับ C# เพื่อช่วยคุณปรับปรุงโครงสร้างและการเข้าถึงเอกสาร PDF ของคุณ

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการปฏิบัติตามบทช่วยสอนนี้เกี่ยวกับองค์ประกอบโครงสร้างบล็อกข้อความด้วย Aspose.PDF สำหรับ .NET มีอะไรบ้าง

ก: ก่อนเริ่มต้น ให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณเพื่อใช้ Aspose.PDF สำหรับ .NET แล้ว ซึ่งเกี่ยวข้องกับการติดตั้งไลบรารี Aspose.PDF และกำหนดค่าโปรเจ็กต์ของคุณเพื่ออ้างอิงไลบรารีดังกล่าว

#### ถาม: ฉันจะสร้างเอกสาร PDF ใหม่และเพิ่มองค์ประกอบโครงสร้างบล็อกข้อความโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

A: บทช่วยสอนนี้มีตัวอย่างโค้ดต้นฉบับ C# ที่สาธิตวิธีการสร้างเอกสาร PDF ใหม่ และเพิ่มหัวเรื่องหลายระดับและย่อหน้าที่มีแท็กโดยใช้ Aspose.PDF สำหรับ .NET

#### ถาม: ความสำคัญของการเพิ่มองค์ประกอบโครงสร้างบล็อกข้อความลงในเอกสาร PDF คืออะไร

A: การเพิ่มองค์ประกอบโครงสร้างบล็อกข้อความ เช่น หัวเรื่องและย่อหน้าที่มีแท็ก จะช่วยปรับปรุงโครงสร้างความหมายของเอกสาร PDF ให้ดีขึ้น ซึ่งจะช่วยให้โปรแกรมอ่านหน้าจอและเทคโนโลยีช่วยเหลืออื่นๆ เข้าถึงได้ง่ายขึ้น ทำให้ผู้ใช้สามารถนำทางและทำความเข้าใจเนื้อหาได้ง่ายขึ้น

#### ถาม: ฉันจะตั้งชื่อเรื่องและภาษาของเอกสาร PDF ที่ถูกแท็กโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

A: บทช่วยสอนนี้ประกอบด้วยตัวอย่างโค้ดต้นฉบับ C# ที่แสดงวิธีการตั้งค่าชื่อและภาษาของเอกสาร PDF ที่มีแท็กโดยใช้ Aspose.PDF สำหรับ .NET

#### ถาม: ฉันจะสร้างหัวเรื่องหลายระดับในเอกสาร PDF ที่มีแท็กโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 A: บทช่วยสอนนี้มีตัวอย่างโค้ดต้นฉบับ C# ที่แสดงวิธีการสร้างหัวเรื่องในระดับต่างๆ โดยใช้`CreateHeaderElement()` วิธีการและผนวกเข้าในองค์ประกอบโครงสร้างรากของเอกสาร PDF ที่ถูกแท็ก

#### ถาม: ฉันจะเพิ่มย่อหน้าที่มีแท็กลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

A: บทช่วยสอนนี้ประกอบด้วยตัวอย่างโค้ดต้นฉบับ C# ที่แสดงวิธีการสร้างย่อหน้าโดยใช้`CreateParagraphElement()` วิธีการและเพิ่มข้อความแท็กลงไปโดยใช้`SetText()` วิธีการ จากนั้นย่อหน้าจะถูกผนวกเข้ากับองค์ประกอบโครงสร้างรากของเอกสาร PDF ที่ถูกแท็ก

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏและการจัดรูปแบบขององค์ประกอบโครงสร้างบล็อกข้อความที่ฉันเพิ่มลงในเอกสาร PDF ได้หรือไม่

A: ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏและการจัดรูปแบบขององค์ประกอบโครงสร้างบล็อกข้อความได้โดยใช้คุณสมบัติและวิธีการต่างๆ ที่ Aspose.PDF สำหรับ .NET จัดเตรียมไว้ คุณสามารถปรับเปลี่ยนรูปแบบแบบอักษร ขนาด สี การจัดตำแหน่ง และคุณลักษณะการจัดรูปแบบอื่นๆ เพื่อให้ตรงตามความต้องการเฉพาะของคุณได้

#### ถาม: โค้ดตัวอย่างที่ให้ไว้ในบทช่วยสอนช่วยในการเพิ่มองค์ประกอบโครงสร้างบล็อกข้อความลงในเอกสาร PDF ได้อย่างไร

A: โค้ดตัวอย่างที่ให้มานี้ทำหน้าที่เป็นข้อมูลอ้างอิงในทางปฏิบัติสำหรับการนำการสร้างองค์ประกอบโครงสร้างบล็อกข้อความไปใช้งานในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET คุณสามารถใช้โค้ดนี้เป็นจุดเริ่มต้นและปรับเปลี่ยนได้ตามความต้องการของคุณ

#### ถาม: ฉันจะปรับปรุงและปรับแต่งเอกสาร PDF เพิ่มเติมนอกเหนือจากองค์ประกอบโครงสร้างบล็อกข้อความโดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

A: Aspose.PDF สำหรับ .NET นำเสนอฟีเจอร์มากมายสำหรับการจัดการเอกสาร PDF รวมถึงการเพิ่มรูปภาพ ตาราง ไฮเปอร์ลิงก์ คำอธิบายประกอบ ฟิลด์ฟอร์ม ลายน้ำ ลายเซ็นดิจิทัล และอื่นๆ คุณสามารถสำรวจเอกสารและทรัพยากรอย่างเป็นทางการเพื่อทำความเข้าใจความสามารถของไลบรารีอย่างครอบคลุม